# CyberArk — PAM Capabilities & Learning Guide

> **Last Updated:** February 2026
> **Vendor:** CyberArk | **Website:** https://www.cyberark.com

---

## 1. Product Capabilities

### Privilege Cloud (SaaS PAM)

| Capability | Details |
|---|---|
| Credential Vaulting | Securely store and manage privileged passwords, SSH keys, and API keys |
| Session Isolation | Proxy-based session management — users never directly touch target systems |
| Session Recording | Full video recording of RDP, SSH, and web sessions with searchable metadata |
| Just-in-Time Access | Time-limited, approval-based privilege elevation |
| Automated Password Rotation | Policy-driven rotation across Windows, Linux, databases, cloud, and network devices |
| Privileged Threat Analytics | ML-based anomaly detection on privileged session behaviour |
| Cloud Deployment | CyberArk manages infrastructure; customer manages policies |
| Platforms | Windows, Linux, Unix, databases, SaaS apps, network devices, cloud consoles |

### PAM Self-Hosted

| Component | Capability |
|---|---|
| **Digital Vault** | Hardened, encrypted credential store with tamper-proof audit logging |
| **Central Policy Manager (CPM)** | Automated password rotation and verification |
| **Privileged Session Manager (PSM)** | Session isolation, recording, and monitoring |
| **Password Vault Web Access (PVWA)** | Web-based management console for administrators and end users |
| **HA / DR** | Active-passive vault replication for high availability |

### Endpoint Privilege Manager (EPM)

| Capability | Details |
|---|---|
| Least Privilege | Remove local admin rights from all endpoints |
| Application Control | Granular allowlisting/blocklisting with elevation policies |
| Credential Theft Protection | Prevent credential harvesting from endpoints |
| Ransomware Protection | Block unauthorised encryption operations |
| Platforms | Windows, macOS, Linux |

### Conjur (Secrets Management)

| Capability | Details |
|---|---|
| Secrets Vaulting | Centralised secrets storage for DevOps and cloud-native workloads |
| Dynamic Secrets | Generate short-lived credentials on demand |
| API-Driven | RESTful API and native integrations with CI/CD tools |
| Platform Support | Kubernetes, Ansible, Terraform, Jenkins, Docker, OpenShift |
| Open Source | Conjur OSS available under BSL licence |

### Additional Products

| Product | Capability |
|---|---|
| **Vendor Privileged Access Manager** | Secure, audited access for third-party vendors without VPN |
| **Cloud Entitlements Manager** | Multi-cloud CIEM for AWS, Azure, GCP — right-size permissions |
| **Identity** | Workforce SSO, adaptive MFA, lifecycle management |
| **Secure Browser** | Isolated browsing for accessing sensitive web applications |

---

## 2. Architecture & Deployment

| Option | Details |
|---|---|
| **Privilege Cloud (SaaS)** | CyberArk-managed cloud; fastest deployment |
| **Self-Hosted** | On-premises Digital Vault with customer-managed infrastructure |
| **Hybrid** | Cloud management plane with on-prem vault connectors |

### Integration Ecosystem

| Category | Integrations |
|---|---|
| SIEM | Splunk, Microsoft Sentinel, QRadar, ArcSight, LogRhythm |
| ITSM | ServiceNow, BMC Remedy, Jira |
| Identity | Active Directory, Azure AD/Entra ID, Okta, Ping, SailPoint |
| DevOps | Jenkins, Ansible, Terraform, Kubernetes, OpenShift, Docker |
| Cloud | AWS, Azure, GCP native integrations |
| MFA | Duo, RSA, FIDO2, Azure MFA, CyberArk Identity MFA |

---

## 3. Free / Trial / Demo / Community Options

| Option | Details | Access |
|---|---|---|
| **Conjur Open Source** | Full secrets management engine (BSL licence) | https://github.com/cyberark/conjur |
| **Privilege Cloud Trial** | Available through CyberArk sales | https://www.cyberark.com/how-to-buy/ |
| **CyberArk Blueprint** | Prescriptive, phased PAM deployment methodology — free PDF | https://www.cyberark.com/resources/cyberark-blueprint |
| **CyberArk Marketplace** | Pre-built integrations, connectors, and plugins | https://cyberark-customers.force.com/marketplace |
| **Product Demo** | Guided demo through sales | https://www.cyberark.com/how-to-buy/ |
| **CyberArk Community** | 40,000+ member technical community | https://community.cyberark.com |

---

## 4. Training & Certification

### CyberArk University

| Resource | Details | Cost |
|---|---|---|
| **Free Introductory Courses** | Threat landscape overview, solution introductions | Free |
| **Instructor-Led Training (ILT)** | Live virtual or in-person with hands-on labs | Paid |
| **Self-Paced eLearning** | On-demand video courses for customers and partners | Paid |
| **Training Portal** | https://training.cyberark.com/learn | Login required |

### Certification Programs

All CyberArk exams are administered **in person only** (as of November 2025) through Pearson VUE.

| Certification | Focus | Prerequisites | Exam Cost |
|---|---|---|---|
| **CyberArk Certified Trustee (CCT)** | Foundational PAM concepts | None | ~$150 |
| **CyberArk Certified Defender (CCD)** | PAM implementation and administration | CCT recommended | ~$200 |
| **CyberArk Certified Delivery Engineer (CCDE)** | Advanced deployment and architecture | CCD required | ~$250 |
| **CyberArk Certified Sentry (CCS)** | Conjur / secrets management | None | ~$200 |
| **CyberArk Certified Endpoint Privilege Manager** | EPM deployment and administration | None | ~$200 |

- Exam blueprints available from CyberArk University
- Exams administered through **Pearson VUE** test centres
- Digital badges issued through **Credly**

---

## 5. Public & Free Learning Resources

| Resource | Description | Link | Cost |
|---|---|---|---|
| CyberArk Community | 40,000+ members; forums, knowledge base, events | https://community.cyberark.com | Free |
| CyberArk Blueprint | Step-by-step PAM deployment methodology | https://www.cyberark.com/resources/cyberark-blueprint | Free |
| CyberArk Documentation | Full product docs for Privilege Cloud and Self-Hosted | https://docs.cyberark.com | Free |
| CyberArk Blog | Threat research, best practices, product updates | https://www.cyberark.com/blog | Free |
| CyberArk Labs | Security research and open-source tools | https://www.cyberark.com/threat-research-blog | Free |
| CyberArk Marketplace | Pre-built integrations and connectors | https://cyberark-customers.force.com/marketplace | Free |
| Webinars | Live and on-demand security webinars | https://www.cyberark.com/resources/webinars | Free |
| YouTube Channel | Product demos, training snippets, thought leadership | Search "CyberArk" on YouTube | Free |
| CyberArk IMPACT Conference | Annual conference with recorded sessions | https://www.cyberark.com/impact | Free (recordings) |

### Third-Party Training

| Platform | Content | Cost |
|---|---|---|
| Udemy | CyberArk certification prep (CDE, Sentry, Trustee) | ~$15 - $50 |
| SecApps Learning | CyberArk training with lab access | Paid |
| Mindmajix | CyberArk online training and certification | Paid |
| HKR Trainings | CyberArk training with lab access | Paid |
| IdentitySkills.com | CyberArk exam preparation guides | Free & paid |

---

## 6. Suggested Learning Path

| Step | Activity | Time | Cost |
|---|---|---|---|
| 1 | Read the CyberArk Blueprint (phased PAM methodology) | 1 - 2 hours | Free |
| 2 | Take free introductory courses on CyberArk University | 2 - 4 hours | Free |
| 3 | Deploy Conjur Open Source in a lab environment | 1 - 2 days | Free |
| 4 | Join the CyberArk Community and explore knowledge base | Ongoing | Free |
| 5 | Request a Privilege Cloud trial or guided demo | 2 - 4 weeks | Free |
| 6 | Complete CCD (Certified Defender) training | 3 - 5 days | Paid |
| 7 | Pass the CCD certification exam at Pearson VUE | 2 hours | ~$200 |

---

*Disclaimer: Training availability, certification requirements, and pricing may change. Visit the linked URLs for the most current information.*
