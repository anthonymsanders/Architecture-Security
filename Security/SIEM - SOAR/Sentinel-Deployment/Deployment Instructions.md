# Microsoft Sentinel Deployment — Azure DevOps Pipeline

> **Version:** 1.0
> **Last Updated:** February 2026
> **Pipeline:** `azure-pipelines.yml`
> **ARM Template:** `sentinel-deployment.json`

---

## Table of Contents

1. [Overview](#1-overview)
2. [What Gets Deployed](#2-what-gets-deployed)
3. [Prerequisites](#3-prerequisites)
4. [Repository Structure](#4-repository-structure)
5. [Variable Reference](#5-variable-reference)
6. [Setup Instructions](#6-setup-instructions)
7. [Pipeline Stages Explained](#7-pipeline-stages-explained)
8. [Customisation Guide](#8-customisation-guide)
9. [Post-Deployment Steps](#9-post-deployment-steps)
10. [Troubleshooting](#10-troubleshooting)
11. [Cost Considerations](#11-cost-considerations)

---

## 1. Overview

This pipeline automates the deployment of a Microsoft Sentinel SIEM instance on Azure using an ARM template and Azure DevOps YAML pipeline. Every configurable setting is exposed as a pipeline variable so the same pipeline can be reused across environments (dev, staging, production) by changing variable values.

### Design Principles

- **Reusable** — all settings are variables; no hardcoded values in templates
- **Idempotent** — safe to run multiple times; creates or updates resources
- **Validated** — template is validated and a what-if analysis runs before deployment
- **Verified** — post-deployment stage confirms configuration matches expectations

---

## 2. What Gets Deployed

| Resource | Details |
|---|---|
| **Resource Group** | Created if it does not exist |
| **Log Analytics Workspace** | Pay-As-You-Go (PerGB2018) pricing tier |
| **Microsoft Sentinel** | Enabled on the workspace via SecurityInsights solution |
| **Daily Ingestion Cap** | 5 MB/day (0.005 GB) — configurable via `dailyQuotaGb` |
| **Table Retention** | 90 days default — configurable via `retentionInDays` |
| **UEBA** | Enabled with AuditLogs, AzureActivity, SecurityEvent, SigninLogs sources |

### Free Data Connectors Enabled

| Connector | Data Tables | Cost |
|---|---|---|
| **Azure Activity** | AzureActivity | Free |
| **Microsoft Entra ID (Azure AD)** | SigninLogs, AuditLogs | Free (with P1/P2 licence) |
| **Microsoft 365 Defender** | SecurityAlert (MDATP) | Free |
| **Microsoft Threat Intelligence** | ThreatIntelligenceIndicator | Free |

---

## 3. Prerequisites

### Azure Requirements

| Requirement | Details |
|---|---|
| **Azure Subscription** | Active subscription with billing enabled |
| **Azure Permissions** | Contributor + Microsoft Sentinel Contributor on the subscription or resource group |
| **Microsoft Entra ID** | P1 or P2 licence required for Sign-In and Audit Log connectors |
| **Microsoft 365 Defender** | Active M365 Defender licence for the Defender connector |
| **Resource Providers** | `Microsoft.OperationalInsights`, `Microsoft.OperationsManagement`, `Microsoft.SecurityInsights` must be registered |

### Azure DevOps Requirements

| Requirement | Details |
|---|---|
| **Azure DevOps Project** | An existing Azure DevOps project |
| **Service Connection** | Managed Identity service connection to the target Azure subscription |
| **Self-Hosted Agent** (for MI) | If using Managed Identity, the agent VM must have the identity assigned with the required roles |
| **Pipeline Environment** | Create an environment called `sentinel-production` in Azure DevOps (Pipelines > Environments) |

### Register Required Resource Providers

If not already registered, run the following in Azure CLI or Cloud Shell:

```bash
az provider register --namespace Microsoft.OperationalInsights
az provider register --namespace Microsoft.OperationsManagement
az provider register --namespace Microsoft.SecurityInsights
```

---

## 4. Repository Structure

```
Security/SIEM - SOAR/Sentinel-Deployment/
├── azure-pipelines.yml           # Azure DevOps pipeline definition
├── sentinel-deployment.json      # ARM template for all resources
└── Deployment Instructions.md    # This file
```

---

## 5. Variable Reference

All configurable settings are defined in the `variables` block of `azure-pipelines.yml`.

### Core Infrastructure Variables

| Variable | Default | Description |
|---|---|---|
| `azureSubscriptionId` | `YOUR_SUBSCRIPTION_ID` | Azure subscription ID or service connection name |
| `resourceGroupName` | `rg-sentinel-prod` | Target resource group name |
| `location` | `uksouth` | Azure region for deployment |

### Workspace Variables

| Variable | Default | Description |
|---|---|---|
| `workspaceName` | `law-sentinel-prod` | Log Analytics workspace name |
| `skuName` | `PerGB2018` | Pricing tier (Pay-As-You-Go) |
| `dailyQuotaGb` | `0.005` | Daily ingestion cap in GB (0.005 GB = 5 MB) |
| `retentionInDays` | `90` | Default retention for workspace tables (30-730 days) |

### Data Connector Variables

| Variable | Default | Description |
|---|---|---|
| `enableAzureActivityConnector` | `true` | Enable Azure Activity connector |
| `enableEntraIDConnector` | `true` | Enable Entra ID Sign-In/Audit connector |
| `enableM365DefenderConnector` | `true` | Enable M365 Defender connector |
| `enableThreatIntelConnector` | `true` | Enable Microsoft Threat Intelligence connector |

### UEBA Variables

| Variable | Default | Description |
|---|---|---|
| `enableUEBA` | `true` | Enable User and Entity Behavior Analytics |

### Tag Variables

| Variable | Default | Description |
|---|---|---|
| `tagEnvironment` | `Production` | Environment tag value |
| `tagManagedBy` | `AzureDevOps` | Managed-by tag value |
| `tagSolution` | `MicrosoftSentinel` | Solution tag value |

---

## 6. Setup Instructions

### Step 1: Configure the Service Connection

Since you are using **Managed Identity** authentication:

1. Ensure your self-hosted Azure DevOps agent VM has a **System-Assigned** or **User-Assigned Managed Identity**
2. Assign the following roles to the Managed Identity on the target subscription:
   - `Contributor` (for resource deployment)
   - `Microsoft Sentinel Contributor` (for Sentinel configuration)
3. In Azure DevOps, go to **Project Settings > Service connections**
4. Create a new **Azure Resource Manager** service connection using **Managed Identity**
5. Note the service connection name — this replaces `YOUR_SUBSCRIPTION_ID` in the pipeline

### Step 2: Update Pipeline Variables

Edit `azure-pipelines.yml` and update the variables section:

```yaml
variables:
  azureSubscriptionId: 'my-sentinel-service-connection'    # your service connection name
  resourceGroupName: 'rg-sentinel-prod'                     # your resource group
  location: 'uksouth'                                       # your region
  workspaceName: 'law-sentinel-prod'                        # your workspace name
  dailyQuotaGb: '0.005'                                     # 5 MB daily cap
  retentionInDays: 90                                        # 90 day retention
```

### Step 3: Create the Pipeline Environment

1. In Azure DevOps, go to **Pipelines > Environments**
2. Click **New environment**
3. Name it `sentinel-production`
4. Optionally add **approval checks** so deployments require manual sign-off

### Step 4: Create the Pipeline

1. In Azure DevOps, go to **Pipelines > New Pipeline**
2. Select your repository source (Azure Repos Git, GitHub, etc.)
3. Choose **Existing Azure Pipelines YAML file**
4. Set the path to `Security/SIEM - SOAR/Sentinel-Deployment/azure-pipelines.yml`
5. Click **Run** to execute the pipeline

### Step 5: Approve and Monitor

1. The **Validate** stage runs automatically — check the what-if output to preview changes
2. The **Deploy** stage requires the pipeline to be running on the `main` branch
3. If you added approval checks on the `sentinel-production` environment, approve the deployment
4. The **Verify** stage confirms the workspace settings match your variables

---

## 7. Pipeline Stages Explained

### Stage 1: Validate

| Step | Action |
|---|---|
| Create Resource Group | Creates the RG if it doesn't exist (idempotent) |
| Validate ARM Template | Runs `az deployment group validate` to check for syntax and parameter errors |
| What-If Analysis | Shows a preview of what resources will be created, modified, or deleted |

The validate stage runs on **all branches and PRs** so you can review changes before merging.

### Stage 2: Deploy

| Step | Action |
|---|---|
| Create Resource Group | Ensures RG exists (idempotent) |
| Deploy ARM Template | Runs `az deployment group create` with all parameters |
| Verify Outputs | Displays the deployment outputs (workspace ID, customer ID, retention, daily cap) |

The deploy stage only runs on the `main` branch (`refs/heads/main`) and uses a **deployment job** with the `sentinel-production` environment for approval gates.

### Stage 3: Verify

| Step | Action |
|---|---|
| Verify Sentinel | Confirms the SecurityInsights solution is installed |
| Verify Workspace | Checks retention and daily cap match expected values |

---

## 8. Customisation Guide

### Using Variable Groups (Recommended for Multiple Environments)

Instead of hardcoding variables in the YAML, use **Azure DevOps Variable Groups** to manage environment-specific values:

1. Go to **Pipelines > Library > + Variable group**
2. Create groups like `sentinel-dev`, `sentinel-staging`, `sentinel-prod`
3. Reference them in the pipeline:

```yaml
variables:
  - group: sentinel-prod    # swap for sentinel-dev, sentinel-staging, etc.
```

### Example: Dev Environment Overrides

| Variable | Production | Development |
|---|---|---|
| `resourceGroupName` | `rg-sentinel-prod` | `rg-sentinel-dev` |
| `workspaceName` | `law-sentinel-prod` | `law-sentinel-dev` |
| `retentionInDays` | `90` | `30` |
| `dailyQuotaGb` | `0.005` | `0.001` |
| `tagEnvironment` | `Production` | `Development` |

### Changing the Daily Ingestion Cap

The `dailyQuotaGb` variable controls the daily data cap. Common values:

| Setting | Value | Use Case |
|---|---|---|
| 5 MB/day | `0.005` | Lab / learning / minimal testing |
| 100 MB/day | `0.1` | Small pilot deployment |
| 1 GB/day | `1` | Small production environment |
| 5 GB/day | `5` | Mid-size production |
| 10 GB/day | `10` | Larger production |
| No cap | `-1` | Unlimited (not recommended without budget controls) |

### Changing Retention

The `retentionInDays` variable controls default table retention:

| Setting | Details |
|---|---|
| `30` | Minimum retention (free tier included) |
| `90` | Default in this pipeline — covers most compliance baselines |
| `180` | Common for security operations |
| `365` | Regulatory (HIPAA, PCI-DSS annual retention) |
| `730` | Maximum supported retention |

> **Cost note:** The first 31 days of retention are included free. Days 32-90 are included free with Sentinel. Retention beyond 90 days is charged at ~$0.12/GB/month.

### Disabling Specific Connectors

Set any connector variable to `false` to skip it:

```yaml
enableM365DefenderConnector: false    # skip if no M365 Defender licence
enableEntraIDConnector: false         # skip if no Entra ID P1/P2
```

### Adding Additional Free Connectors

To add more connectors, add new resource blocks to `sentinel-deployment.json` following the existing pattern. Other free connectors include:

| Connector | Kind Value | Licence Needed |
|---|---|---|
| Microsoft Defender for Cloud | `AzureSecurityCenter` | Defender for Cloud |
| Microsoft Defender for IoT | `IOT` | Defender for IoT |
| Microsoft Cloud App Security | `MicrosoftCloudAppSecurity` | MCAS licence |
| Office 365 | `Office365` | Office 365 licence |

---

## 9. Post-Deployment Steps

After the pipeline completes successfully, perform these manual steps in the Azure Portal:

### 9.1 Verify UEBA Configuration

1. Navigate to **Microsoft Sentinel > Entity behavior (UEBA)**
2. Confirm that UEBA is enabled and the configured data sources are active
3. Verify entity pages are populating (may take 24-48 hours for initial data)

### 9.2 Enable Analytics Rules

The pipeline deploys connectors but does not enable analytics (detection) rules. To enable:

1. Go to **Microsoft Sentinel > Analytics > Rule templates**
2. Filter by data source to see rules available for your enabled connectors
3. Enable the recommended rules — start with:
   - Fusion detection (ML-based multi-stage attack detection)
   - Microsoft Security incident creation rules (auto-creates incidents from Defender alerts)
   - Built-in Scheduled rules for high-fidelity detections

### 9.3 Configure Diagnostic Settings

Route Azure Activity logs to the workspace:

1. Go to **Azure Monitor > Activity Log > Diagnostic settings**
2. Add a diagnostic setting to send logs to the Log Analytics workspace
3. Select all log categories

### 9.4 Set Up Automation (Optional)

1. Go to **Microsoft Sentinel > Automation**
2. Create automation rules for common actions:
   - Auto-assign incidents to analysts
   - Auto-close known false positives
   - Run playbooks (Logic Apps) for enrichment or response

### 9.5 Review Workbooks

1. Go to **Microsoft Sentinel > Workbooks > Templates**
2. Save key workbooks to your workspace:
   - Azure Activity
   - Microsoft Entra ID Sign-In Logs
   - UEBA Insights
   - Security Operations Efficiency

---

## 10. Troubleshooting

### Common Issues

| Issue | Cause | Resolution |
|---|---|---|
| `ResourceProviderNotRegistered` | Required provider not registered | Run `az provider register --namespace Microsoft.SecurityInsights` |
| `AuthorizationFailed` | Managed Identity lacks permissions | Assign `Contributor` + `Microsoft Sentinel Contributor` roles |
| `WorkspaceNotFound` during connector deployment | Timing issue — workspace not yet ready | The template uses `dependsOn` to handle this; if persistent, re-run the pipeline |
| `InvalidTemplateDeployment` | Parameter type mismatch | Check that `retentionInDays` is an integer and `dailyQuotaGb` is a string |
| Entra ID connector shows "No data" | Missing P1/P2 licence or diagnostic settings | Verify Entra ID licence tier and enable diagnostic settings in Entra admin centre |
| UEBA not populating entities | Data needs time to process | Allow 24-48 hours after deployment for initial entity data |
| `DailyQuotaReached` in workspace | Ingestion exceeded the 5 MB cap | Increase `dailyQuotaGb` or wait for the next UTC day reset |
| Pipeline fails on deploy stage | Branch is not `main` | Deploy stage has a branch condition; merge to main or remove the condition for testing |

### Useful Azure CLI Commands for Debugging

```bash
# Check resource group exists
az group show --name rg-sentinel-prod

# Check workspace configuration
az monitor log-analytics workspace show \
  --workspace-name law-sentinel-prod \
  --resource-group rg-sentinel-prod \
  --output jsonc

# List Sentinel solutions
az monitor log-analytics solution list \
  --resource-group rg-sentinel-prod \
  --query "[?contains(name, 'SecurityInsights')]" \
  --output table

# Check deployment status
az deployment group show \
  --name sentinel-BUILDNUMBER \
  --resource-group rg-sentinel-prod \
  --query "properties.provisioningState"

# List registered providers
az provider show --namespace Microsoft.SecurityInsights \
  --query "registrationState"
```

---

## 11. Cost Considerations

### Pay-As-You-Go (PerGB2018) Pricing

| Component | Cost | Notes |
|---|---|---|
| **Log Analytics ingestion** | ~$2.76/GB (UK South) | First 5 GB/month may be free on some subscriptions |
| **Sentinel charge** | ~$2.46/GB | On top of Log Analytics cost |
| **Total per GB** | ~$5.22/GB | Combined ingestion cost |
| **Retention (first 90 days)** | Free | 31 days free for LA + 59 days free for Sentinel |
| **Retention (beyond 90 days)** | ~$0.12/GB/month | Per GB of retained data |
| **UEBA** | Free | No additional charge |
| **Free connectors** | Free | Azure Activity, Entra ID, Defender, Threat Intelligence |

### Monthly Cost Estimate at 5 MB/Day

| Metric | Value |
|---|---|
| Daily ingestion | 5 MB (0.005 GB) |
| Monthly ingestion | ~150 MB (0.15 GB) |
| Monthly cost (LA + Sentinel) | ~$0.78/month |
| Annual cost | ~$9.40/year |

> With a 5 MB daily cap, this deployment is effectively a lab/learning environment with minimal cost. Increase `dailyQuotaGb` for production workloads.

### Cost Optimisation Tips

- Use **Commitment Tiers** if ingesting 100+ GB/day for significant discounts
- Set the `dailyQuotaGb` cap to prevent unexpected cost spikes
- Use **Basic Logs** for high-volume, low-value tables (cheaper ingestion, limited query)
- Archive data beyond 90 days to **Archive tier** at ~$0.02/GB/month
- Review the **Sentinel Free Trial** — 10 GB/day free for the first 31 days on new workspaces

---

*For questions or issues with this pipeline, raise an issue in the repository or contact the security engineering team.*
