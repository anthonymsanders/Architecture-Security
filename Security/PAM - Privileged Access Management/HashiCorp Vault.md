# HashiCorp Vault — Capabilities & Learning Guide

> **Last Updated:** February 2026
> **Vendor:** HashiCorp (IBM) | **Website:** https://www.hashicorp.com/products/vault

---

## 1. Product Capabilities

### Core Secrets Management

| Capability | Details |
|---|---|
| Secrets Storage | Securely store and control access to tokens, passwords, certificates, API keys |
| Dynamic Secrets | Generate short-lived, on-demand credentials for databases, cloud providers, and more |
| Secret Rotation | Automated rotation with configurable TTLs |
| Leasing & Revocation | All secrets have a lease; automatic revocation on expiry or on demand |
| Namespaces | Multi-tenant isolation within a single Vault cluster (Enterprise) |
| Versioning | KV v2 secrets engine maintains version history |

### Secrets Engines

| Engine | Description |
|---|---|
| **KV (Key-Value)** | Generic secrets storage (v1 non-versioned, v2 versioned) |
| **Database** | Dynamic credentials for MySQL, PostgreSQL, MSSQL, MongoDB, Oracle, and more |
| **AWS** | Dynamic IAM credentials, STS tokens, and assumed roles |
| **Azure** | Dynamic service principal credentials |
| **GCP** | Dynamic service account keys and OAuth2 tokens |
| **PKI** | Full certificate authority — issue, renew, and revoke X.509 certificates |
| **SSH** | Signed SSH certificates or dynamic SSH OTP credentials |
| **Transit** | Encryption-as-a-service — encrypt/decrypt data without exposing keys |
| **TOTP** | Generate and validate time-based one-time passwords |
| **LDAP** | Dynamic LDAP credentials |
| **Kubernetes** | Generate Kubernetes service account tokens |
| **Transform** | Format-preserving encryption and data masking |

### Authentication Methods

| Method | Description |
|---|---|
| Token | Default; every auth method generates a Vault token |
| LDAP / Active Directory | Authenticate using corporate directory |
| OIDC / JWT | OpenID Connect and JSON Web Token authentication |
| AWS IAM | Authenticate using AWS IAM roles or EC2 instance metadata |
| Azure MSI | Authenticate using Azure Managed Identity |
| GCP IAM | Authenticate using GCP service accounts |
| Kubernetes | Authenticate using Kubernetes service account tokens |
| AppRole | Machine-oriented authentication for applications and automation |
| TLS Certificates | Mutual TLS authentication |
| GitHub | Authenticate using GitHub personal access tokens |
| Userpass | Simple username/password (development and testing) |

### Enterprise Features (Not in Community Edition)

| Feature | Details |
|---|---|
| Namespaces | Multi-tenant isolation |
| Replication | Performance and disaster recovery replication across clusters |
| HSM Support | Seal/unseal with Hardware Security Modules (PKCS#11) |
| Sentinel Policies | Fine-grained policy-as-code (OPA-like) |
| MFA | Multi-factor authentication enforcement |
| Control Groups | Require multiple authorisations for sensitive operations |
| FIPS 140-2 | Compliance-ready builds |

---

## 2. Product Editions & Pricing

| Edition | Hosting | Price | Key Differences |
|---|---|---|---|
| **Community Edition** | Self-hosted | Free (BSL 1.1 licence) | Full secrets engine; no namespaces, replication, or HSM |
| **HCP Vault Secrets Free** | SaaS | Free | 25 secrets, 5 versions, 5 sync destinations |
| **HCP Vault Secrets Plus** | SaaS | $0.50/secret/month | Up to 2,500 secrets, 50 versions, 200 sync destinations |
| **HCP Vault Secrets Enterprise** | SaaS | $0.95/secret/month | Up to 25,000 secrets, auto-rotation, dynamic secrets |
| **HCP Vault Dedicated (Dev)** | Managed | ~$1.58/hour | Single-node development cluster |
| **HCP Vault Dedicated (Standard)** | Managed | ~$1.84/hour | 3-node HA cluster |
| **HCP Vault Dedicated (Plus)** | Managed | ~$2.40/hour | Perf replication, HSM, advanced features |
| **Vault Enterprise** | Self-hosted | Custom quote ($50K - $200K+/year) | All features; namespaces, DR, HSM, Sentinel |

### BSL Licence Note

As of August 2023, Vault Community Edition uses the **Business Source License (BSL) 1.1** instead of MPL 2.0. This allows:
- Free use for internal purposes
- Free use for development and testing
- **Not permitted:** offering Vault as a managed service competing with HashiCorp

---

## 3. Free / Trial / Developer Options

| Option | Details | Cost |
|---|---|---|
| **Community Edition** | Full Vault binary, all secrets engines, self-hosted | Free |
| **HCP Vault Secrets Free Tier** | 25 secrets, 5 versions, 5 sync destinations | Free |
| **Dev Mode** | `vault server -dev` — in-memory, auto-unsealed, for learning only | Free |
| **HCP Free Tier** | HashiCorp Cloud Platform free tier credits | Free |
| **Tutorials (developer.hashicorp.com)** | 100+ hands-on tutorials with embedded terminals | Free |
| **Vault Playground** | Interactive browser-based Vault environment | Free |

---

## 4. Training & Certification

### HashiCorp Training

| Resource | Details | Cost |
|---|---|---|
| **HashiCorp Learn (Tutorials)** | 100+ hands-on tutorials covering every feature | Free |
| **Instructor-Led Training** | Live virtual courses with hands-on labs | Paid |
| **HashiCorp Certified: Vault Associate** | Foundational certification | ~$70 exam |
| **HashiCorp Certified: Vault Operations Professional** | Advanced operations and architecture certification | ~$295 exam |

### Certification Details

| Certification | Level | Format | Duration | Prerequisites | Cost |
|---|---|---|---|---|---|
| **Vault Associate (003)** | Foundational | Multiple choice | 1 hour | None | ~$70 |
| **Vault Operations Professional** | Advanced | Multiple choice + hands-on | 4 hours | Associate recommended | ~$295 |

- Exams administered through **PSI** online proctoring
- Certifications valid for **2 years**
- Study guides available on HashiCorp Learn

---

## 5. Public & Free Learning Resources

| Resource | Description | Link | Cost |
|---|---|---|---|
| HashiCorp Learn — Vault Tutorials | 100+ hands-on tutorials | https://developer.hashicorp.com/vault/tutorials | Free |
| Vault Documentation | Complete reference documentation | https://developer.hashicorp.com/vault/docs | Free |
| Vault API Reference | Full HTTP API documentation | https://developer.hashicorp.com/vault/api-docs | Free |
| Vault Associate Study Guide | Exam preparation guide | https://developer.hashicorp.com/vault/tutorials/associate-cert | Free |
| HashiCorp Blog | Product updates, use cases, best practices | https://www.hashicorp.com/blog | Free |
| HashiCorp Discuss | Community forum for Q&A and discussion | https://discuss.hashicorp.com | Free |
| Vault GitHub Repository | Source code, issues, and community contributions | https://github.com/hashicorp/vault | Free |
| YouTube — HashiCorp | Product demos, HashiConf talks, tutorials | Search "HashiCorp Vault" on YouTube | Free |
| HashiConf Recorded Sessions | Annual conference talks and demos | https://www.hashicorp.com/events | Free |

### Third-Party Resources

| Platform | Content | Cost |
|---|---|---|
| Udemy | Vault Associate exam prep, hands-on courses | ~$15 - $50 |
| Pluralsight | Vault fundamentals and operations | Subscription (~$29/month) |
| A Cloud Guru | Vault certification courses | Subscription |
| KodeKloud | Vault hands-on labs and courses | Subscription |
| Coursera | Secrets management and DevSecOps courses | Free (audit) |

---

## 6. Suggested Learning Path

| Step | Activity | Time | Cost |
|---|---|---|---|
| 1 | Install Vault Community Edition and run in dev mode | 30 min | Free |
| 2 | Complete the "Get Started" tutorial series on HashiCorp Learn | 2 - 3 hours | Free |
| 3 | Work through KV, database, and PKI secrets engine tutorials | 1 - 2 days | Free |
| 4 | Deploy a production-like Vault with Consul/Raft storage backend | 1 - 2 days | Free |
| 5 | Study the Vault Associate exam guide | 1 - 2 weeks | Free |
| 6 | Sign up for HCP Vault Secrets Free Tier and explore SaaS experience | 1 day | Free |
| 7 | Pass the Vault Associate (003) certification | 1 hour | ~$70 |
| 8 | (Optional) Prepare for Vault Operations Professional | 2 - 4 weeks | ~$295 exam |

---

*Disclaimer: Licensing, pricing, and certification details may change. Visit the linked URLs for the most current information.*
