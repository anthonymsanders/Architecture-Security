# Privileged Access Management (PAM) — Vendor Research

> **Last Updated:** February 2026
> **Purpose:** High-level comparison of leading PAM vendors covering products, costs, implementation complexity, timelines, and free/developer/community options.

---

## Table of Contents

1. [BeyondTrust](#1-beyondtrust)
2. [CyberArk](#2-cyberark)
3. [Delinea](#3-delinea)
4. [Microsoft Entra PIM](#4-microsoft-entra-pim)
5. [HashiCorp Vault](#5-hashicorp-vault)
6. [One Identity Safeguard](#6-one-identity-safeguard)
7. [Vendor Comparison Summary](#7-vendor-comparison-summary)

---

## 1. BeyondTrust

**Focus:** Unified PAM platform — endpoint privilege management, secure remote access, password management, and cloud security

### Products

| Product | Description |
|---|---|
| **Password Safe** | Automated privileged password and session management — discover, vault, rotate, and audit credentials |
| **Privileged Remote Access (PRA)** | Secure, audited remote access for vendors and internal users without VPN |
| **Remote Support** | Enterprise remote support with full session recording and audit |
| **Endpoint Privilege Management (EPM)** | Least-privilege enforcement and application control on Windows, Mac, Linux, and Unix |
| **Cloud Privilege Broker** | Multi-cloud entitlements management (AWS, Azure, GCP) |
| **AD Bridge** | Centralise Unix/Linux authentication through Active Directory |
| **Identity Security Insights** | Unified analytics across all BeyondTrust products |

### Pricing

| Model | Details |
|---|---|
| **Pricing Approach** | Subscription-based; per-user, per-endpoint, or per-asset depending on module |
| **EPM** | Starting ~$4/endpoint/month (SaaS) |
| **Password Safe** | Custom quote; typically $15,000 - $100,000+/year depending on managed accounts |
| **PRA** | Custom quote; priced per concurrent session or named user |
| **Typical Enterprise** | $50,000 - $300,000+/year for multi-module deployment |

### Implementation Complexity & Timeline

| Factor | Rating | Details |
|---|---|---|
| **Overall Complexity** | Medium-High | Multiple modules require phased rollout |
| **EPM Deployment** | 4 - 8 weeks | Agent-based; requires policy tuning per application |
| **Password Safe** | 6 - 12 weeks | Discovery, onboarding, rotation policy configuration |
| **PRA** | 2 - 4 weeks | Cloud-delivered; simpler than on-prem alternatives |
| **Full Platform** | 3 - 6 months | Complete deployment across all modules |
| **Professional Services** | Recommended | BeyondTrust or partner-led implementation available |

### Free / Trial / Developer Options

| Option | Details | Cost |
|---|---|---|
| Free Trial | Available on request through sales | Free |
| Product Demo | Guided demo of any module | Free |
| Community | BeyondTrust Community forums | Free |

> See [BeyondTrust.md](BeyondTrust.md) for full capabilities, training, and certification details.

---

## 2. CyberArk

**Focus:** Market leader in enterprise PAM — privileged credential vaulting, session management, secrets management, and identity security

### Products

| Product | Description |
|---|---|
| **Privilege Cloud** | SaaS-delivered PAM — credential vaulting, session isolation, JIT access |
| **PAM Self-Hosted** | On-premises PAM with Digital Vault, PSM, CPM, and PVWA |
| **Endpoint Privilege Manager (EPM)** | Least-privilege and application control for Windows, Mac, Linux |
| **Secrets Manager (Conjur)** | Secrets management for DevOps, CI/CD, and cloud-native workloads |
| **Vendor Privileged Access Manager** | Secure third-party/vendor access without VPN |
| **Cloud Entitlements Manager** | CIEM for multi-cloud privilege right-sizing |
| **Identity** | Workforce and customer identity (SSO, MFA, lifecycle) |
| **Secure Browser** | Isolated browser for secure access to sensitive web applications |

### Pricing

| Model | Details |
|---|---|
| **Pricing Approach** | Per-user subscription; tiered by module and deployment model |
| **Privilege Cloud** | Starting ~$2/user/month for basic; premium tiers significantly higher |
| **PAM Self-Hosted** | Perpetual or subscription; typically $30,000 - $200,000+/year |
| **Conjur Open Source** | Free (open-source; BSL licence) |
| **Conjur Enterprise** | Custom quote |
| **Median Contract** | ~$30,000/year (varies widely with scope) |

### Implementation Complexity & Timeline

| Factor | Rating | Details |
|---|---|---|
| **Overall Complexity** | High | Most feature-rich; requires skilled implementation |
| **Privilege Cloud (SaaS)** | 4 - 8 weeks | Faster than self-hosted; CyberArk manages infrastructure |
| **PAM Self-Hosted** | 3 - 6 months | Vault hardening, CPM/PSM setup, HA configuration |
| **EPM** | 4 - 8 weeks | Agent deployment and policy tuning |
| **Full Platform** | 6 - 12 months | Enterprise-wide across all modules |
| **Professional Services** | Strongly Recommended | CyberArk Jump Start or partner-led implementation |

### Free / Trial / Developer Options

| Option | Details | Cost |
|---|---|---|
| Conjur Open Source | Secrets management engine (BSL licence) | Free |
| Privilege Cloud Trial | Available through CyberArk sales | Free |
| CyberArk Blueprint | Prescriptive guidance for phased PAM rollout | Free |
| CyberArk Marketplace | Pre-built integrations and plugins | Free |

> See [CyberArk.md](CyberArk.md) for full capabilities, training, and certification details.

---

## 3. Delinea

**Focus:** Simplified, cloud-ready PAM — secret vaulting, privilege elevation, and least-privilege enforcement

### Products

| Product | Description |
|---|---|
| **Secret Server** | Enterprise password vault — discover, store, rotate, and audit privileged credentials |
| **Secret Server Cloud** | SaaS-delivered password vault |
| **Privilege Manager** | Endpoint least-privilege and application control for Windows and Mac |
| **Server PAM** | Lightweight privilege elevation and session management for Unix/Linux servers |
| **Account Lifecycle Manager** | Automated service account governance and lifecycle management |
| **Connection Manager** | Centralised session launcher for RDP and SSH with credential injection |
| **DevOps Secrets Vault** | Cloud-native secrets management for CI/CD and DevOps pipelines |
| **Delinea Platform** | Unified SaaS platform combining all products |

### Pricing

| Model | Details |
|---|---|
| **Pricing Approach** | Per-user subscription; tiered bundles |
| **Secret Server Free** | Free perpetual licence — 10 users, 250 secrets |
| **Secret Server Professional** | Custom quote; starting ~$10,000/year |
| **Secret Server Platinum** | Custom quote; includes advanced features |
| **Privilege Manager** | Custom quote; per-endpoint pricing |
| **Delinea Platform Bundles** | Essentials, Standard, Enterprise tiers |

### Implementation Complexity & Timeline

| Factor | Rating | Details |
|---|---|---|
| **Overall Complexity** | Low-Medium | Designed for rapid deployment; simplest in this comparison |
| **Secret Server Cloud** | 1 - 2 weeks | SaaS; minimal infrastructure requirements |
| **Secret Server On-Prem** | 2 - 4 weeks | Windows-based; straightforward installation |
| **Privilege Manager** | 4 - 6 weeks | Agent-based; requires policy definition |
| **Full Platform** | 2 - 3 months | All modules across the organisation |
| **Professional Services** | Optional | Self-deployment is feasible for experienced teams |

### Free / Trial / Developer Options

| Option | Details | Cost |
|---|---|---|
| Secret Server Free | Perpetual licence — 10 users, 250 secrets, AD integration, encryption | Free (forever) |
| Secret Server 30-Day Trial | Full-featured trial, 10 users, on-prem or cloud | Free |
| Privilege Manager 30-Day Trial | Full-featured endpoint privilege management trial | Free |
| DevOps Secrets Vault Trial | Cloud-native secrets management trial | Free |

> See [Delinea.md](Delinea.md) for full capabilities, training, and certification details.

---

## 4. Microsoft Entra PIM

**Focus:** Cloud-native privileged identity management for Azure, Entra ID, and Microsoft 365 roles

### Products

| Product | Description |
|---|---|
| **Privileged Identity Management (PIM)** | Just-in-time (JIT) role activation, approval workflows, and audit for Entra ID and Azure roles |
| **Entra ID Governance** | Access reviews, entitlement management, lifecycle workflows |
| **Conditional Access** | Risk-based, context-aware access policies for privileged sessions |
| **Entra Permissions Management** | Multi-cloud CIEM (AWS, Azure, GCP) entitlements right-sizing |

### Pricing

| Model | Details |
|---|---|
| **Entra ID P2** | ~$9/user/month (includes PIM + Identity Protection) |
| **Included in M365 E5** | Bundled at ~$57/user/month |
| **Entra ID Governance Add-on** | ~$7/user/month (adds lifecycle workflows, access reviews) |
| **Permissions Management** | ~$10.40/resource/month (multi-cloud CIEM) |

### Implementation Complexity & Timeline

| Factor | Rating | Details |
|---|---|---|
| **Overall Complexity** | Low | Native to Azure/Entra ID; no infrastructure to deploy |
| **PIM Activation** | 1 - 2 days | Enable in Entra ID portal; configure role settings |
| **Policy Configuration** | 1 - 2 weeks | Define approval workflows, activation duration, MFA requirements |
| **Full Governance** | 2 - 4 weeks | Access reviews, entitlement management, lifecycle workflows |
| **Professional Services** | Not required | Self-service deployment; extensive Microsoft Learn documentation |

### Free / Trial / Developer Options

| Option | Details | Cost |
|---|---|---|
| M365 E5 Trial | 30-day trial with 25 users (includes P2/PIM) | Free |
| Entra ID P2 Trial | 30-day trial | Free |
| M365 Developer Program | Renewable 90-day E5 sandbox with PIM | Free |
| Microsoft Learn Sandboxes | Temporary lab environments for hands-on PIM exercises | Free |

> See [Microsoft Entra PIM.md](Microsoft%20Entra%20PIM.md) for full capabilities, training, and certification details.

---

## 5. HashiCorp Vault

**Focus:** Secrets management, dynamic credentials, encryption-as-a-service, and identity-based access for DevOps and cloud-native environments

### Products

| Product | Description |
|---|---|
| **Vault Community Edition** | Self-hosted secrets management (BSL licence) |
| **HCP Vault Dedicated** | Fully managed single-tenant Vault clusters on HashiCorp Cloud Platform |
| **HCP Vault Secrets** | SaaS-delivered secrets management with sync to cloud providers |
| **Vault Enterprise** | Self-hosted with enterprise features (namespaces, replication, HSM support) |

### Pricing

| Model | Details |
|---|---|
| **HCP Vault Secrets Free Tier** | 25 secrets, 5 versions, 5 sync destinations |
| **HCP Vault Secrets Plus** | $0.50/secret/month (up to 2,500 secrets) |
| **HCP Vault Secrets Enterprise** | $0.95/secret/month (up to 25,000 secrets; dynamic secrets) |
| **HCP Vault Dedicated** | Starting ~$1.58/hour (development cluster) |
| **Vault Enterprise** | Custom quote; typically $50,000 - $200,000+/year |
| **Community Edition** | Free (BSL 1.1 licence) |

### Implementation Complexity & Timeline

| Factor | Rating | Details |
|---|---|---|
| **Overall Complexity** | Medium-High | Powerful but requires strong DevOps/infrastructure skills |
| **HCP Vault Secrets** | 1 - 2 days | SaaS; connect and sync secrets immediately |
| **HCP Vault Dedicated** | 1 - 2 weeks | Managed clusters; HashiCorp handles infrastructure |
| **Vault Community (self-hosted)** | 2 - 4 weeks | Requires HA setup, storage backend, unsealing strategy |
| **Enterprise (full deployment)** | 2 - 3 months | Multi-namespace, replication, HSM integration |
| **Professional Services** | Recommended for Enterprise | HashiCorp or partner-led implementation |

### Free / Trial / Developer Options

| Option | Details | Cost |
|---|---|---|
| Community Edition | Full Vault engine, self-hosted (BSL 1.1 licence) | Free |
| HCP Vault Secrets Free Tier | 25 secrets, 5 versions, 5 sync destinations | Free |
| HCP Vault Dedicated Dev Cluster | Low-cost development cluster | ~$1.58/hour |
| Vault Tutorials | Hands-on tutorials on developer.hashicorp.com | Free |

> See [HashiCorp Vault.md](HashiCorp%20Vault.md) for full capabilities, training, and certification details.

---

## 6. One Identity Safeguard

**Focus:** Appliance-based PAM with integrated privileged password management, session recording, and behavioural analytics

### Products

| Product | Description |
|---|---|
| **Safeguard for Privileged Passwords** | Automated credential vaulting, rotation, and access request workflows |
| **Safeguard for Privileged Sessions** | Full session recording, indexing, real-time monitoring, and keystroke logging |
| **Safeguard for Privileged Analytics** | User behaviour analytics (UBA) for detecting anomalous privileged activity |
| **Safeguard On Demand** | SaaS-delivered PAM |
| **Cloud PAM Essentials** | Streamlined cloud-native PAM for simpler environments |

### Pricing

| Model | Details |
|---|---|
| **Pricing Approach** | Appliance + per-user licence; concurrent user model |
| **Appliance Cost** | Physical or virtual appliance licensing |
| **Per-User Licence** | Based on concurrent privileged sessions |
| **Typical Enterprise** | $30,000 - $150,000+/year depending on scale |

### Implementation Complexity & Timeline

| Factor | Rating | Details |
|---|---|---|
| **Overall Complexity** | Medium | Appliance model simplifies some infrastructure decisions |
| **Cloud PAM Essentials** | 1 - 2 weeks | Lightweight SaaS option |
| **Safeguard On Demand** | 2 - 4 weeks | SaaS-delivered; faster than on-prem |
| **Safeguard On-Premises** | 4 - 8 weeks | Appliance deployment, connector config, HA setup |
| **Full Suite (all modules)** | 2 - 4 months | Passwords + Sessions + Analytics |
| **Professional Services** | Recommended | One Identity or partner-led implementation |

### Free / Trial / Developer Options

| Option | Details | Cost |
|---|---|---|
| Free Trial | Available for download through One Identity | Free |
| Product Demo | Guided demo through sales | Free |
| One Identity Community | Forums, knowledge base, and product documentation | Free |

> See [One Identity Safeguard.md](One%20Identity%20Safeguard.md) for full capabilities, training, and certification details.

---

## 7. Vendor Comparison Summary

### Cost Comparison

| Vendor | Starting Cost | Typical Enterprise | Free Edition |
|---|---|---|---|
| **BeyondTrust** | ~$4/endpoint/month (EPM) | $50K - $300K+/year | No (trial only) |
| **CyberArk** | ~$2/user/month (basic cloud) | $30K - $200K+/year | Conjur OSS |
| **Delinea** | Free (10 users, 250 secrets) | $10K - $150K+/year | Secret Server Free |
| **Microsoft Entra PIM** | ~$9/user/month (P2) | Included in M365 E5 | 30-day P2 trial |
| **HashiCorp Vault** | Free (Community Edition) | $50K - $200K+/year | CE + HCP Free Tier |
| **One Identity** | Custom quote | $30K - $150K+/year | Trial download |

### Implementation Complexity & Timeline

| Vendor | Complexity | Basic Deployment | Full Production |
|---|---|---|---|
| **BeyondTrust** | Medium-High | 2 - 4 weeks (PRA) | 3 - 6 months |
| **CyberArk** | High | 4 - 8 weeks (Cloud) | 6 - 12 months |
| **Delinea** | Low-Medium | 1 - 2 weeks (Cloud) | 2 - 3 months |
| **Microsoft Entra PIM** | Low | 1 - 2 days | 2 - 4 weeks |
| **HashiCorp Vault** | Medium-High | 1 - 2 days (HCP SaaS) | 2 - 3 months |
| **One Identity** | Medium | 1 - 2 weeks (Cloud) | 2 - 4 months |

### Capability Matrix

| Capability | BeyondTrust | CyberArk | Delinea | Entra PIM | Vault | One Identity |
|---|---|---|---|---|---|---|
| Password Vaulting | Yes | Yes | Yes | No | Yes | Yes |
| Session Recording | Yes | Yes | Limited | No | No | Yes |
| Session Isolation | Yes | Yes | No | No | No | Yes |
| JIT Access | Yes | Yes | Yes | Yes | No | Yes |
| Endpoint Privilege Mgmt | Yes | Yes | Yes | No | No | No |
| Secrets Management | Limited | Yes (Conjur) | Yes (DSV) | No | Yes | No |
| Cloud Entitlements (CIEM) | Yes | Yes | No | Yes | No | No |
| Multi-Cloud Support | Yes | Yes | Limited | Yes (CIEM) | Yes | Limited |
| Vendor Remote Access | Yes | Yes | No | No | No | No |
| Behavioural Analytics | Limited | Yes | No | Yes (Identity Protection) | No | Yes |
| AD Bridging | Yes | No | No | No | No | Yes |

### Best Free / Developer Options

| Vendor | Best Free Option | Limitations |
|---|---|---|
| **BeyondTrust** | Trial (via sales) | Time-limited |
| **CyberArk** | Conjur Open Source | Secrets management only; no PAM GUI |
| **Delinea** | Secret Server Free (perpetual) | 10 users, 250 secrets |
| **Microsoft Entra PIM** | M365 Developer Program (90-day E5) | Renewable but limited to dev/test |
| **HashiCorp Vault** | Community Edition (self-hosted) | No enterprise features (namespaces, HSM, replication) |
| **One Identity** | Trial download | Time-limited |

### Best Fit by Use Case

| Use Case | Recommended Vendor(s) |
|---|---|
| **Enterprise PAM (full suite)** | CyberArk, BeyondTrust |
| **Fastest time to value** | Microsoft Entra PIM, Delinea |
| **Microsoft-centric environment** | Microsoft Entra PIM + Delinea or CyberArk |
| **DevOps / secrets management** | HashiCorp Vault, CyberArk Conjur |
| **SMB / limited budget** | Delinea (free edition), HashiCorp Vault (CE) |
| **Vendor / third-party access** | BeyondTrust PRA, CyberArk Vendor PAM |
| **Endpoint privilege management** | BeyondTrust EPM, CyberArk EPM, Delinea Privilege Manager |
| **Multi-cloud entitlements** | Microsoft Entra Permissions Management, CyberArk CEM |
| **Session recording / forensics** | CyberArk, BeyondTrust, One Identity |
| **Easiest to learn / evaluate** | Delinea (free edition), Vault (CE), Entra PIM (dev program) |

---

*Disclaimer: All pricing is approximate and subject to change. Enterprise pricing is heavily dependent on organisation size, modules selected, and negotiated terms. Contact vendors directly for current quotes.*
