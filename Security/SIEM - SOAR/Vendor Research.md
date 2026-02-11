# SIEM Vendor Research

> **Last Updated:** February 2026
> **Purpose:** High-level comparison of leading SIEM services across cost, deployment timelines, free/community editions, developer options, and learning resources.

---

## Table of Contents

1. [Microsoft Sentinel](#1-microsoft-sentinel)
2. [AWS Security Lake & Security Hub](#2-aws-security-lake--security-hub)
3. [Google Chronicle Security Operations](#3-google-chronicle-security-operations)
4. [IBM QRadar SIEM](#4-ibm-qradar-siem)
5. [Oracle Cloud Guard & Logging Analytics](#5-oracle-cloud-guard--logging-analytics)
6. [Splunk Enterprise Security](#6-splunk-enterprise-security)
7. [Vendor Comparison Summary](#7-vendor-comparison-summary)

---

## 1. Microsoft Sentinel

**Product:** Microsoft Sentinel (cloud-native SIEM + SOAR on Azure)

### High-Level Costs

| Pricing Model | Cost | Notes |
|---|---|---|
| Pay-As-You-Go | ~$4.30/GB ingested | Varies by region |
| Commitment Tier (100 GB/day) | ~$296/day ($2.96/GB) | Discounted rate for committed volume |
| Commitment Tier (50 GB/day) | Available Oct 2025 - Mar 2026 (preview) | New lower-entry commitment tier |
| Free Trial | 10 GB/day for 31 days | Both Log Analytics and Sentinel charges waived |

- Additional costs apply for Log Analytics workspace, automation rules, and data retention beyond defaults.
- Microsoft 365 E5/A5 customers get 5 MB/user/day of specific data at no extra charge.

### Deployment & Learning Timeline

| Phase | Estimated Timeline |
|---|---|
| Initial deployment (basic connectors) | 1 - 2 weeks |
| Full production deployment | 4 - 8 weeks |
| Analyst proficiency | 2 - 4 weeks (with prior SIEM experience) |
| Advanced customization (KQL, workbooks, playbooks) | 2 - 3 months |

### Product Links

| Resource | Link |
|---|---|
| Product Page | https://azure.microsoft.com/en-us/products/microsoft-sentinel |
| Pricing | https://www.microsoft.com/en-us/security/pricing/microsoft-sentinel |
| Azure Pricing Calculator | https://azure.microsoft.com/en-us/pricing/calculator/ |
| Documentation | https://learn.microsoft.com/en-us/azure/sentinel/ |

### Free / Community / Developer Options

| Option | Details | Cost |
|---|---|---|
| Free Trial | 10 GB/day for 31 days on new workspaces | Free |
| Azure Free Account | $200 credit for 30 days + 12 months of free services | Free |
| Microsoft 365 E5 Trial | 30-day trial includes Sentinel-eligible data | Free |

### Learning Resources

| Resource | Link | Cost |
|---|---|---|
| Microsoft Learn - Intro to Sentinel | https://learn.microsoft.com/en-us/training/modules/intro-to-azure-sentinel/ | Free |
| SC-200 Learning Path | https://learn.microsoft.com/en-us/training/paths/sc-200-configure-azure-sentinel-environment/ | Free |
| Sentinel Ninja Training (Level 400) | https://techcommunity.microsoft.com/blog/microsoftsentinelblog/become-a-microsoft-sentinel-ninja-the-complete-level-400-training/1246310 | Free |
| Threat Hunting Learning Path | https://learn.microsoft.com/en-us/training/paths/sc-200-perform-threat-hunting-azure-sentinel/ | Free |
| Sentinel Skill-Up Resources Hub | https://learn.microsoft.com/en-us/azure/sentinel/skill-up-resources | Free |
| SC-200 Certification Exam | https://learn.microsoft.com/en-us/credentials/certifications/security-operations-analyst/ | ~$165 |

---

## 2. AWS Security Lake & Security Hub

**Product:** Amazon Security Lake (centralized security data lake) + AWS Security Hub (aggregated findings & compliance)

### High-Level Costs

| Component | Cost | Notes |
|---|---|---|
| Security Lake - Log normalization | $0.035/GB | OCSF normalization + Parquet conversion |
| Security Lake - CloudTrail ingestion | $0.75/GB | CloudTrail management events |
| Security Lake - Other AWS logs | $0.25/GB | VPC Flow Logs, Route 53, etc. |
| Security Lake - S3 storage | Standard S3 rates | For stored normalized data |
| Security Hub | $0.0010/finding (first 10K/month/region) | Tiered pricing; decreases at volume |
| Security Hub - Compliance checks | $0.0010/check/account/region | Per config rule evaluation |
| Free Trial - Security Lake | 15 days | Per account, per region |
| Free Trial - Security Hub | 30 days | Full feature access |

- Additional costs for Glue, Lambda, EventBridge, SQS, SNS as part of the data pipeline.
- Third-party data ingestion into Security Lake has no Security Lake charge (standard S3 rates apply).

### Deployment & Learning Timeline

| Phase | Estimated Timeline |
|---|---|
| Security Hub activation | 1 - 2 days |
| Security Lake setup (basic) | 1 - 2 weeks |
| Full multi-account/multi-region deployment | 4 - 8 weeks |
| Analyst proficiency | 2 - 4 weeks |
| Advanced custom insights & automation | 2 - 3 months |

### Product Links

| Resource | Link |
|---|---|
| Security Lake Product Page | https://aws.amazon.com/security-lake/ |
| Security Lake Pricing | https://aws.amazon.com/security-lake/pricing/ |
| Security Hub Product Page | https://aws.amazon.com/security-hub/ |
| Security Hub Pricing | https://aws.amazon.com/security-hub/pricing/ |
| Documentation - Security Lake | https://docs.aws.amazon.com/security-lake/ |
| Documentation - Security Hub | https://docs.aws.amazon.com/securityhub/ |

### Free / Community / Developer Options

| Option | Details | Cost |
|---|---|---|
| Security Lake Free Trial | 15 days per account per region | Free |
| Security Hub Free Trial | 30 days full access | Free |
| AWS Free Tier | 12 months of free-tier services + always-free services | Free |
| GuardDuty Free Trial | 30 days (feeds into Security Hub) | Free |

### Learning Resources

| Resource | Link | Cost |
|---|---|---|
| AWS Security Hub Primer | https://www.classcentral.com/course/aws-security-hub-primer-73455 | Free |
| AWS Skill Builder (600+ free courses) | https://skillbuilder.aws/ | Free |
| AWS Security Learning Path | https://aws.amazon.com/training/learn-about/security/ | Free |
| AWS Workshop Studio (hands-on labs) | https://workshops.aws/ | Free |
| AWS Cloud Quest - Security | https://skillbuilder.aws/ | Subscription (~$29/month) |
| AWS Certified Security Specialty (SCS-C03) | https://aws.amazon.com/certification/certified-security-specialty/ | ~$300 exam |

---

## 3. Google Chronicle Security Operations

**Product:** Google Security Operations (Chronicle SIEM + SOAR, built on Google infrastructure)

### High-Level Costs

| Pricing Model | Cost | Notes |
|---|---|---|
| Per-employee pricing | Custom quote required | Flat rate per employee; unlimited data ingestion |
| Average annual cost | ~$315,000/year (reported avg.) | Varies significantly by org size |
| Data ingestion | Unlimited (included in license) | Major differentiator vs. per-GB models |

- Pricing is not publicly listed; requires contacting Google Cloud sales.
- The per-employee model provides cost predictability regardless of log volume growth.
- Bundled with Google Threat Intelligence and Mandiant expertise.

### Deployment & Learning Timeline

| Phase | Estimated Timeline |
|---|---|
| Initial setup (cloud-native) | 1 - 2 weeks |
| Full production with log sources | 4 - 6 weeks |
| Analyst proficiency | 2 - 4 weeks |
| Advanced YARA-L rule writing & playbooks | 2 - 3 months |

### Product Links

| Resource | Link |
|---|---|
| Product Page | https://chronicle.security/ |
| Chronicle SIEM | https://cloud.google.com/chronicle-siem |
| Google Security Operations Suite | https://chronicle.security/suite/siem/ |
| Documentation | https://cloud.google.com/chronicle/docs |

### Free / Community / Developer Options

| Option | Details | Cost |
|---|---|---|
| Google Cloud Free Trial | $300 credit for 90 days | Free |
| Chronicle Demo / POC | Available through Google Cloud sales | Free (by arrangement) |

- No publicly available community or free-tier edition of Chronicle.

### Learning Resources

| Resource | Link | Cost |
|---|---|---|
| Google SecOps Learning Path | https://learn.chronicle.security/ | Free |
| Google Skills - SIEM & SOAR Path | https://www.skills.google/paths/187 | Free |
| Cloud Skills Boost - Security Practices with Chronicle | https://www.cloudskillsboost.google/course_templates/442 | Free |
| Coursera - Chronicle SIEM Guided Projects | https://www.coursera.org/projects/googlecloud-chronicle-siem-introduction-single-event-rules-dwafp | Free (audit) |
| Google Cloud Security Certification | https://cloud.google.com/learn/certification/cloud-security-engineer | ~$200 exam |

---

## 4. IBM QRadar SIEM

**Product:** IBM Security QRadar SIEM (on-premises, cloud, or SaaS)

### High-Level Costs

| Pricing Model | Cost | Notes |
|---|---|---|
| EPS-based (Events Per Second) | Custom quote | Based on log events ingested per second |
| FPM-based (Flows Per Minute) | Custom quote | Based on network flows per minute |
| MVS-based (Managed Virtual Servers) | Custom quote | Enterprise model based on server count |
| AWS Marketplace (BYOL) | Custom quote | Bring Your Own License on AWS |

- IBM does not publicly list pricing; all quotes are custom.
- Historically ranges from ~$800/month for small deployments to $50,000+/month for enterprise.
- On-premises deployments carry additional hardware and maintenance costs.

### Deployment & Learning Timeline

| Phase | Estimated Timeline |
|---|---|
| Community Edition setup | 1 - 2 days |
| Cloud/SaaS deployment (basic) | 2 - 4 weeks |
| On-premises full deployment | 6 - 12 weeks |
| Analyst proficiency | 3 - 6 weeks |
| Advanced rule tuning & app integration | 3 - 6 months |

### Product Links

| Resource | Link |
|---|---|
| Product Page | https://www.ibm.com/products/qradar-siem |
| Pricing Info | https://www.ibm.com/products/qradar-siem/pricing |
| Community Edition | https://www.ibm.com/community/101/qradar/ce/ |
| AWS Marketplace | https://aws.amazon.com/marketplace/pp/prodview-4nvxmksgtznfs |
| Documentation | https://www.ibm.com/docs/en/qsip |
| IBM TechXchange Community | https://community.ibm.com/community/user/security/home |

### Free / Community / Developer Options

| Option | Details | Cost |
|---|---|---|
| QRadar Community Edition | Full-featured, limited to 50 EPS & 5,000 FPM. Perpetual license, no expiration. | Free |
| Community Edition Renewal | 3-month license, renewable each quarter | Free |
| Academic Initiative | Access for students and educators via IBM Academic Initiative | Free |

### Learning Resources

| Resource | Link | Cost |
|---|---|---|
| IBM Security Learning Academy | https://www.ibm.com/training/security | Free |
| QRadar Community & Forums | https://community.ibm.com/community/user/security/home | Free |
| Class Central - QRadar Courses | https://www.classcentral.com/subject/ibm-security-qradar | Free |
| Udemy - QRadar Courses | https://www.udemy.com/topic/qradar/ | Paid (~$15-50) |
| IBM Certified Analyst - QRadar SIEM V7.5 | https://www.ibm.com/training/certification | ~$200 exam |
| IBM Certified Administrator - QRadar SIEM V7.5 | https://www.ibm.com/training/certification | ~$200 exam |
| CyberNomadTV - QRadar Analyst Resources | https://cybernomadtv.com/ibm-qradar-siem-analyst/ | Free |

---

## 5. Oracle Cloud Guard & Logging Analytics

**Product:** Oracle Cloud Guard (threat detection & security posture) + OCI Logging Analytics (log-based SIEM capabilities)

> **Note:** Oracle does not offer a standalone branded SIEM product. Instead, OCI Cloud Guard and Logging Analytics provide SIEM-like capabilities, and Oracle recommends integration with third-party SIEMs (Splunk, QRadar, etc.) for full SIEM functionality.

### High-Level Costs

| Component | Cost | Notes |
|---|---|---|
| Cloud Guard | Included with OCI tenancy | No additional charge for OCI resources |
| Logging Analytics - Active Storage | ~$0.50/GB | For actively queryable log data |
| Logging Analytics - Archive Storage | ~$0.02/GB | For long-term retention |
| OCI Free Tier | Always Free services included | Cloud Guard included |
| Free Credits | $300 for 30 days | For trial of paid services |

- Cloud Guard is enabled at no cost for all OCI tenancies.
- Logging Analytics pricing is usage-based on data ingested and stored.
- For full SIEM, Oracle's guidance is to export Cloud Guard findings to an external SIEM.

### Deployment & Learning Timeline

| Phase | Estimated Timeline |
|---|---|
| Cloud Guard activation | 1 day (built into OCI) |
| Logging Analytics basic setup | 1 - 2 weeks |
| SIEM integration (export to Splunk/QRadar) | 2 - 4 weeks |
| Analyst proficiency | 2 - 4 weeks |
| Advanced recipes & custom detectors | 2 - 3 months |

### Product Links

| Resource | Link |
|---|---|
| Cloud Guard Product Page | https://www.oracle.com/security/cloud-security/cloud-guard/ |
| Cloud Guard FAQ | https://www.oracle.com/security/cloud-security/cloud-guard/faq/ |
| Logging Analytics | https://www.oracle.com/manageability/log-analytics/ |
| Cloud Security Pricing | https://www.oracle.com/security/cloud-security/pricing/ |
| OCI Free Tier | https://www.oracle.com/cloud/free/ |
| SIEM Integration Guide | https://docs.oracle.com/en-us/iaas/Content/cloud-adoption-framework/siem-integration.htm |

### Free / Community / Developer Options

| Option | Details | Cost |
|---|---|---|
| OCI Always Free Tier | Cloud Guard, 2 VMs, 200 GB storage, and more with no time limit | Free |
| OCI Free Trial | $300 in credits for 30 days | Free |
| OCI Developer Resources | SDKs, CLI, Terraform provider | Free |

### Learning Resources

| Resource | Link | Cost |
|---|---|---|
| OCI Training & Certification | https://www.oracle.com/education/training/oracle-cloud-infrastructure/ | Free & paid options |
| OCI Foundations (free cert) | https://www.oracle.com/cloud/free/training/ | Free |
| Oracle LiveLabs (hands-on) | https://apexapps.oracle.com/pls/apex/r/dbpm/livelabs/home | Free |
| Cloud Guard Documentation | https://docs.oracle.com/en-us/iaas/cloud-guard/ | Free |
| OCI Security Architect Certification | https://www.oracle.com/education/training/oracle-cloud-infrastructure/ | ~$245 exam |

---

## 6. Splunk Enterprise Security

**Product:** Splunk Enterprise Security (ES) - on-premises, cloud (Splunk Cloud), or hybrid

### High-Level Costs

| Pricing Model | Cost | Notes |
|---|---|---|
| Workload Pricing | Custom quote | Based on compute resources (SVCs) |
| Ingest Pricing (1 GB/day) | ~$1,800/year | Entry-level |
| Ingest Pricing (10 GB/day) | ~$18,000/year | Mid-range |
| Entity Pricing | Custom quote | Per monitored entity |
| Splunk Cloud | Custom quote | Fully managed SaaS |
| Splunk Free | 500 MB/day limit | No auth, alerting, or clustering |

- Enterprise Security (ES) is an add-on to Splunk Enterprise or Splunk Cloud and carries additional licensing costs.
- Pricing scales significantly with data volume; large enterprises can spend $100K - $1M+ annually.
- Now owned by Cisco (acquired 2024), which may impact future pricing models.

### Deployment & Learning Timeline

| Phase | Estimated Timeline |
|---|---|
| Splunk Free / Dev setup | 1 day |
| Splunk Enterprise (basic) | 1 - 2 weeks |
| Enterprise Security (ES) full deployment | 6 - 12 weeks |
| Splunk Cloud deployment | 2 - 4 weeks |
| Analyst proficiency (SPL basics) | 2 - 4 weeks |
| Advanced SPL, dashboards & apps | 3 - 6 months |

### Product Links

| Resource | Link |
|---|---|
| Product Page | https://www.splunk.com/en_us/products/enterprise-security.html |
| Pricing | https://www.splunk.com/en_us/products/pricing.html |
| Pricing Calculator | https://www.splunk.com/en_us/products/pricing/pricing-calculator.html |
| Security Pricing FAQ | https://www.splunk.com/en_us/products/pricing/faqs/cyber-security.html |
| Splunk Free Download | https://www.splunk.com/en_us/download/splunk-enterprise.html |
| Splunkbase (Apps & Add-ons) | https://splunkbase.splunk.com/ |
| Documentation | https://docs.splunk.com/ |

### Free / Community / Developer Options

| Option | Details | Cost |
|---|---|---|
| Splunk Free | 500 MB/day indexing, no auth/alerting/clustering | Free (perpetual) |
| Developer License | 10 GB/day, full features, non-production only | Free |
| Academic Alliance | 10 GB/year license + ES & SOAR Community Edition for qualifying institutions | Free |
| Splunk SOAR Community Edition | Up to 100 actions/day | Free |
| 60-Day Enterprise Trial | Full features for 60 days | Free |

### Learning Resources

| Resource | Link | Cost |
|---|---|---|
| Splunk Free Training Courses | https://www.splunk.com/en_us/training/free-courses/overview.html | Free |
| Splunk Fundamentals 1, 2 & 3 | https://www.splunk.com/en_us/training/splunk-fundamentals.html | Free (Fund. 1) / Paid |
| Course Catalog | https://www.splunk.com/en_us/training/course-catalog.html | Free & paid |
| Academic Alliance Program | https://www.splunk.com/en_us/resources/splunk-academic-alliance.html | Free for students |
| Splunk University Program | https://workplus.splunk.com/universities | Free |
| Coursera - Splunk Courses | https://www.coursera.org/courses?query=splunk | Free (audit) |
| Splunk Core Certified User Exam | https://www.splunk.com/en_us/training/certification.html | ~$130 exam |
| Splunk Enterprise Security Certified Admin | https://www.splunk.com/en_us/training/certification.html | ~$130 exam |

---

## 7. Vendor Comparison Summary

### Cost Comparison at a Glance

| Vendor | Pricing Model | Entry Cost | Free Tier / Trial |
|---|---|---|---|
| **Microsoft Sentinel** | Per-GB ingested | ~$4.30/GB (PAYG) | 10 GB/day for 31 days |
| **AWS Security Lake + Hub** | Per-GB + per-finding | ~$0.25-$0.75/GB + $0.001/finding | 15-30 day trials |
| **Google Chronicle** | Per-employee (unlimited data) | Custom (~$315K avg/yr) | $300 GCP credit / 90 days |
| **IBM QRadar** | Per-EPS / per-FPM / per-MVS | Custom quote | Community Edition (perpetual) |
| **Oracle Cloud Guard** | Included with OCI + per-GB (Logging Analytics) | Free (Cloud Guard) / ~$0.50/GB (logs) | Always Free Tier + $300 credit |
| **Splunk ES** | Per-GB ingest or workload | ~$1,800/yr (1 GB/day) | 500 MB/day free; 60-day trial |

### Deployment Speed Comparison

| Vendor | Basic Deployment | Full Production |
|---|---|---|
| **Microsoft Sentinel** | 1 - 2 weeks | 4 - 8 weeks |
| **AWS Security Lake + Hub** | 1 - 2 days (Hub) / 1-2 weeks (Lake) | 4 - 8 weeks |
| **Google Chronicle** | 1 - 2 weeks | 4 - 6 weeks |
| **IBM QRadar** | 1 - 2 days (CE) / 2-4 weeks (cloud) | 6 - 12 weeks |
| **Oracle Cloud Guard** | 1 day | 2 - 4 weeks |
| **Splunk** | 1 day (free) / 1-2 weeks (enterprise) | 6 - 12 weeks (ES) |

### Best Free / Developer Options

| Vendor | Best Free Option | Limitations |
|---|---|---|
| **Microsoft Sentinel** | 31-day trial (10 GB/day) | Time-limited |
| **AWS** | Free tier + 30-day Security Hub trial | Time-limited |
| **Google Chronicle** | $300 GCP credit | No free Chronicle edition |
| **IBM QRadar** | Community Edition (perpetual, no expiration) | 50 EPS / 5,000 FPM |
| **Oracle** | Always Free Tier (Cloud Guard included) | No standalone SIEM product |
| **Splunk** | Free edition (perpetual) + Developer license (10 GB) | 500 MB/day (free); no production use (dev) |

### Learning Resource Quality

| Vendor | Free Training Breadth | Certification Path | Hands-On Lab Access |
|---|---|---|---|
| **Microsoft Sentinel** | Extensive (Microsoft Learn) | SC-200 | Azure sandbox labs |
| **AWS** | Extensive (Skill Builder) | Security Specialty (SCS-C03) | Workshop Studio |
| **Google Chronicle** | Moderate (Cloud Skills Boost) | Cloud Security Engineer | Qwiklabs |
| **IBM QRadar** | Good (Security Learning Academy) | QRadar Analyst / Admin V7.5 | Community Edition |
| **Oracle** | Moderate (LiveLabs) | OCI Security Architect | LiveLabs |
| **Splunk** | Extensive (50+ free courses) | Core User / ES Admin | Free / Dev license |

---

## Key Takeaways

1. **Best for Microsoft-centric environments:** Microsoft Sentinel integrates natively with M365, Azure AD, and Defender suite.
2. **Best for AWS-native workloads:** AWS Security Lake + Security Hub provide seamless integration with AWS services.
3. **Best for unlimited data ingestion:** Google Chronicle's per-employee pricing eliminates concerns about data volume costs.
4. **Best free community edition:** IBM QRadar Community Edition offers a perpetual, full-featured free version ideal for learning.
5. **Best for OCI environments:** Oracle Cloud Guard comes free with any OCI tenancy and integrates with third-party SIEMs.
6. **Best free learning ecosystem:** Splunk offers the most comprehensive free training program with academic alliances, free courses, and accessible developer licenses.
7. **Most mature / widely adopted:** Splunk remains the most widely deployed commercial SIEM, though its acquisition by Cisco may shift its strategic direction.

---

*Disclaimer: All pricing is approximate and subject to change. Costs vary by region, data volume, and negotiated enterprise agreements. Contact vendors directly for current quotes.*
