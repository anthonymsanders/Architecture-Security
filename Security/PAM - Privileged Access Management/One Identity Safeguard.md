# One Identity Safeguard — PAM Capabilities & Learning Guide

> **Last Updated:** February 2026
> **Vendor:** One Identity (Quest Software / Clearlake Capital) | **Website:** https://www.oneidentity.com/one-identity-safeguard/

---

## 1. Product Capabilities

### Safeguard for Privileged Passwords

| Capability | Details |
|---|---|
| Credential Vaulting | Hardened appliance-based password vault with AES-256 encryption |
| Automated Discovery | Discover privileged accounts across the environment |
| Password Rotation | Automated, policy-driven rotation across platforms |
| Access Request Workflows | Role-based approval workflows with time-limited checkout |
| Just-in-Time Access | Grant credentials only when approved; auto-revoke after use |
| REST API | Full API for automation and integration |
| Platforms | Windows, Linux, Unix, databases, network devices, directory services, cloud |

### Safeguard for Privileged Sessions

| Capability | Details |
|---|---|
| Session Recording | Full video recording of RDP, SSH, VNC, Telnet, HTTP/S, and ICA sessions |
| Session Monitoring | Real-time monitoring with ability to terminate sessions on policy violation |
| Keystroke Logging | Searchable keystroke and command audit trails |
| Optical Character Recognition (OCR) | Index graphical session content for search (RDP, VNC) |
| Protocol-Level Proxy | Transparent proxy — users connect through Safeguard; never directly to targets |
| 4-Eyes Authorisation | Require a second person to monitor live sessions before access is granted |
| Content Policies | Trigger alerts or terminate sessions based on commands, window titles, or content |

### Safeguard for Privileged Analytics

| Capability | Details |
|---|---|
| User Behaviour Analytics (UBA) | ML-based anomaly detection on privileged user activity |
| Biometric Profiling | Typing pattern analysis and mouse movement profiling |
| Risk Scoring | Continuous risk scoring for privileged sessions |
| Alerting | Real-time alerts on anomalous behaviour |
| Integration | Feeds into SIEM (Splunk, Sentinel, QRadar) for correlated analysis |

### Deployment Options

| Option | Details |
|---|---|
| **Safeguard On-Premises** | Hardened physical or virtual appliance (OVA/Hyper-V) |
| **Safeguard On Demand** | SaaS-delivered PAM managed by One Identity |
| **Cloud PAM Essentials** | Lightweight cloud-native PAM for simpler environments |
| **Hybrid** | On-premises vault with cloud-connected management |

---

## 2. Architecture & Integration

### Appliance Model

Safeguard deploys as a hardened appliance (physical or virtual), which simplifies security hardening — the OS, database, and application are pre-configured and locked down.

| Component | Details |
|---|---|
| Vault Appliance | Stores credentials; hardened, tamper-resistant |
| Session Appliance | Proxies and records sessions; separate from vault for security isolation |
| Analytics | Can run on the session appliance or standalone |

### Integration Ecosystem

| Category | Integrations |
|---|---|
| SIEM | Splunk, Microsoft Sentinel, QRadar, ArcSight |
| ITSM | ServiceNow |
| Identity | Active Directory, LDAP, Azure AD/Entra ID |
| MFA | RSA, Duo, FIDO2, RADIUS |
| Cloud | AWS, Azure, GCP |
| API | Full REST API for custom integrations |

---

## 3. Pricing

| Model | Details |
|---|---|
| **Pricing Approach** | Appliance licence + per-concurrent-user subscription |
| **Appliance Licence** | Physical or virtual appliance licence fee |
| **User Licences** | Based on concurrent privileged sessions (not total users) |
| **Support** | Annual support and maintenance contract |
| **Typical Enterprise** | $30,000 - $150,000+/year |

> Pricing is custom-quoted. One Identity offers a **PAM Savings Calculator** at https://www.oneidentity.com/one-identity-safeguard/pam-savings-calculator.aspx

---

## 4. Free / Trial / Developer Options

| Option | Details | Cost |
|---|---|---|
| **Free Trial** | Available for download from One Identity | Free |
| **Product Demo** | Guided demo through One Identity sales | Free |
| **One Identity Community** | Forums, knowledge base, documentation | Free |
| **Technical Documentation** | Full admin and deployment guides | Free |

> One Identity does not offer a permanent free or community edition.

---

## 5. Training & Certification

### One Identity Training

| Resource | Details | Cost |
|---|---|---|
| **One Identity University** | Instructor-led and self-paced courses | Paid |
| **On-Demand Training** | Video-based courses for Safeguard products | Paid |
| **Documentation & Guides** | Full product documentation | Free |

### Certification

| Certification | Focus | Format | Cost |
|---|---|---|---|
| **One Identity Certified Specialist — Safeguard** | Safeguard deployment and administration | Exam-based | Paid |
| **One Identity Certified Professional** | Advanced deployment and architecture | Exam-based | Paid |

### Partner Training

| Programme | Details |
|---|---|
| One Identity Partner Circle | Training and enablement for authorised partners |
| Technical Enablement | Partner-specific Safeguard training |

---

## 6. Public & Free Learning Resources

| Resource | Description | Link | Cost |
|---|---|---|---|
| Product Documentation | Full admin, deployment, and API guides | https://support.oneidentity.com/technical-documents | Free |
| One Identity Community | Forums, knowledge base, and how-to articles | https://www.oneidentity.com/community/ | Free |
| One Identity Blog | Security best practices, product updates | https://www.oneidentity.com/community/blogs | Free |
| Webinars | Live and on-demand security and product webinars | https://www.oneidentity.com/resources/ | Free |
| YouTube Channel | Product demos, webinar recordings | Search "One Identity" on YouTube | Free |
| PAM Savings Calculator | Estimate ROI and cost savings from PAM deployment | https://www.oneidentity.com/one-identity-safeguard/pam-savings-calculator.aspx | Free |
| Gartner Peer Insights | Verified reviews and ratings | https://www.gartner.com/reviews/market/privileged-access-management/vendor/one-identity | Free |
| Whitepapers | PAM best practices, compliance guides | https://www.oneidentity.com/resources/ | Free |
| Top 5 PAM Tools Guide | One Identity comparison of PAM solutions | https://www.oneidentity.com/learn/top-5-privileged-access-management-tools-in-2025.aspx | Free |

### Third-Party Resources

| Platform | Content | Cost |
|---|---|---|
| Udemy | Privileged access management courses | ~$15 - $50 |
| Gartner Research | PAM Magic Quadrant (references One Identity) | Paid |

### Complementary Certifications

| Certification | Relevance | Exam Cost |
|---|---|---|
| CompTIA Security+ | Foundational identity and access control | ~$392 |
| CISSP (ISC2) | IAM domain covers PAM concepts | ~$749 |
| SC-300 (Microsoft) | Identity and access management (Entra integration context) | ~$165 |

---

## 7. Suggested Learning Path

| Step | Activity | Time | Cost |
|---|---|---|---|
| 1 | Read the product documentation and architecture overview | 1 - 2 hours | Free |
| 2 | Watch product demo videos on YouTube | 1 - 2 hours | Free |
| 3 | Use the PAM Savings Calculator to build a business case | 30 min | Free |
| 4 | Request a free trial download from One Identity | 2 - 4 weeks | Free |
| 5 | Deploy the virtual appliance in a lab environment | 1 - 2 days | Free |
| 6 | Join the One Identity Community for support and knowledge sharing | Ongoing | Free |
| 7 | Complete One Identity University training for Safeguard | 3 - 5 days | Paid |
| 8 | Pass the Certified Specialist — Safeguard exam | 1 - 2 hours | Paid |

---

*Disclaimer: Training availability, pricing, and certification details may change. Visit the linked URLs for the most current information.*
