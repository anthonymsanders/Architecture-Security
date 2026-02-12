# Microsoft Entra Privileged Identity Management — Capabilities & Learning Guide

> **Last Updated:** February 2026
> **Vendor:** Microsoft | **Website:** https://www.microsoft.com/en-us/security/business/microsoft-entra-pricing

---

## 1. Product Capabilities

### Privileged Identity Management (PIM)

| Capability | Details |
|---|---|
| Just-in-Time (JIT) Access | Users activate roles only when needed; auto-expire after defined duration |
| Approval Workflows | Require one or more approvers before role activation |
| MFA Enforcement | Require multi-factor authentication for role activation |
| Justification Required | Users must provide business justification when requesting access |
| Time-Bound Assignments | Set maximum activation duration (e.g., 1 hour, 4 hours, 8 hours) |
| Eligible vs Active Roles | Assign users as "eligible" (must activate) vs. "active" (always on) |
| Azure Role Support | PIM for Azure resource roles (Contributor, Owner, Reader, custom) |
| Entra ID Role Support | PIM for Entra ID directory roles (Global Admin, User Admin, Security Admin, etc.) |
| Group-Based PIM | PIM for security groups — control group membership via JIT |
| Access Reviews | Periodic reviews of role assignments to ensure least privilege |
| Audit Logging | Full audit trail of all role activations, approvals, and denials |
| Alerts | Configurable alerts for suspicious role activity |

### Entra ID Governance (Complementary)

| Capability | Details |
|---|---|
| Access Reviews | Automated review and recertification of access |
| Entitlement Management | Access packages for bundled resource access with approval workflows |
| Lifecycle Workflows | Automated joiner/mover/leaver processes |
| Identity Governance Dashboard | Unified view of governance posture and recommendations |

### Conditional Access (Complementary)

| Capability | Details |
|---|---|
| Risk-Based Policies | Require MFA or block access based on sign-in risk level |
| Device Compliance | Require compliant or managed devices for privileged access |
| Location-Based Policies | Restrict privileged role activation by IP/location |
| Session Controls | Limit session duration, enforce re-authentication |

### Entra Permissions Management (CIEM)

| Capability | Details |
|---|---|
| Multi-Cloud Discovery | Discover identities and permissions across AWS, Azure, GCP |
| Permission Creep Index | Quantify over-provisioned permissions with a risk score |
| Right-Sizing | Automated recommendations to reduce permissions to least privilege |
| JIT for Cloud | Request time-limited cloud permissions through approval workflows |
| Monitoring | Continuous monitoring of cloud permission usage and anomalies |

---

## 2. Licensing & Pricing

| Licence | PIM Included | Price | Notes |
|---|---|---|---|
| **Entra ID P2** | Yes | ~$9/user/month | Standalone; includes PIM + Identity Protection |
| **Microsoft 365 E5** | Yes | ~$57/user/month | Full E5 bundle includes P2 |
| **Microsoft 365 E3** | No (P1 only) | ~$36/user/month | Requires P2 add-on for PIM |
| **Entra ID Governance** | Yes (adds lifecycle) | ~$7/user/month add-on | Requires P1 or P2 base |
| **Entra Permissions Management** | Separate | ~$10.40/resource/month | Multi-cloud CIEM |

### What Happens When P2 Expires

- PIM settings are preserved but users cannot activate roles
- Existing active assignments remain until they expire
- No new eligible assignments can be created

---

## 3. Free / Trial / Developer Options

| Option | Details | Duration | Link |
|---|---|---|---|
| **Entra ID P2 Free Trial** | Full P2 features including PIM | 30 days | https://www.microsoft.com/en-us/security/business/microsoft-entra-pricing |
| **Microsoft 365 E5 Trial** | 25-user E5 trial with full PIM access | 30 days | Via Microsoft 365 admin centre |
| **M365 Developer Program** | Renewable 90-day E5 sandbox with PIM | Renewable | https://developer.microsoft.com/en-us/microsoft-365/dev-program |
| **Microsoft Learn Sandboxes** | Temporary lab environments for PIM exercises | Per module | https://learn.microsoft.com |
| **Azure Free Account** | $200 credit for 30 days (test Azure role PIM) | 30 days | https://azure.microsoft.com/en-us/free/ |

> The **M365 Developer Program** is the best option for long-term free learning — the 90-day E5 sandbox renews automatically as long as you use it for development.

---

## 4. Training & Certification

### Microsoft Learn — Free Learning Paths

| Path | Modules | Link | Cost |
|---|---|---|---|
| Plan and implement privileged access | PIM configuration, role settings, access reviews | https://learn.microsoft.com/en-us/training/paths/plan-implement-privileged-access/ | Free |
| Plan and implement identity governance | PIM + entitlement management + access reviews | https://learn.microsoft.com/en-us/training/paths/plan-implement-identity-governance-strategy/ | Free |
| SC-300 full learning path | Identity and access management (includes PIM) | https://learn.microsoft.com/en-us/training/paths/implement-identity-management-solution/ | Free |

### Certification

| Certification | Focus | Exam Cost | Link |
|---|---|---|---|
| **SC-300: Identity and Access Administrator** | Entra ID, PIM, Conditional Access, governance | ~$165 | https://learn.microsoft.com/en-us/credentials/certifications/identity-and-access-administrator/ |
| **SC-200: Security Operations Analyst** | Sentinel, Defender (references PIM alerts) | ~$165 | https://learn.microsoft.com/en-us/credentials/certifications/security-operations-analyst/ |
| **SC-100: Cybersecurity Architect** | Zero Trust architecture including PIM strategy | ~$165 | https://learn.microsoft.com/en-us/credentials/certifications/cybersecurity-architect-expert/ |

---

## 5. Public & Free Learning Resources

| Resource | Description | Link | Cost |
|---|---|---|---|
| PIM Documentation | Complete configuration and usage guides | https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-configure | Free |
| PIM Getting Started Guide | Step-by-step first-time setup | https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-getting-started | Free |
| Microsoft Learn Modules | Interactive exercises with sandbox labs | https://learn.microsoft.com/en-us/training/ | Free |
| Microsoft Tech Community Blog | PIM updates, best practices, announcements | https://techcommunity.microsoft.com/t5/microsoft-entra-blog/bg-p/Identity | Free |
| Microsoft Security Blog | Broader security context for PIM | https://www.microsoft.com/en-us/security/blog/ | Free |
| YouTube — Microsoft Security | PIM demos, Ignite sessions, deep dives | Search "Microsoft Entra PIM" on YouTube | Free |
| Entra ID Governance Docs | Access reviews, entitlement management, lifecycle | https://learn.microsoft.com/en-us/entra/id-governance/ | Free |

### Third-Party Resources

| Platform | Content | Cost |
|---|---|---|
| Coursera | SC-300 preparation courses | Free (audit) |
| Udemy | Entra ID and PIM courses | ~$15 - $50 |
| John Savill's YouTube | Excellent deep-dive videos on PIM and Entra ID | Free |
| AdminDroid Blog | PIM for Groups guides and tutorials | Free |
| Sikich Blog | P1 vs P2 comparison guides | Free |

---

## 6. Suggested Learning Path

| Step | Activity | Time | Cost |
|---|---|---|---|
| 1 | Read the PIM Getting Started documentation | 30 min | Free |
| 2 | Sign up for the M365 Developer Program (E5 sandbox) | 15 min | Free |
| 3 | Complete the "Plan and implement privileged access" Learn path | 3 - 4 hours | Free |
| 4 | Configure PIM in your developer tenant (roles, policies, access reviews) | 1 - 2 days | Free |
| 5 | Complete the full SC-300 learning path | 1 - 2 weeks | Free |
| 6 | Pass the SC-300 certification exam | 2 hours | ~$165 |

---

*Disclaimer: Licensing, pricing, and certification details may change. Visit the linked URLs for the most current information.*
