# SentinelOne Singularity XDR

## Product Overview

| Attribute | Detail |
|-----------|--------|
| **Product Name** | Singularity XDR (Singularity Platform) |
| **Vendor** | SentinelOne |
| **XDR Type** | Native XDR |
| **Deployment** | Cloud-native (SaaS); agent operates autonomously offline |
| **Licensing** | Per-endpoint (Core, Control, Complete, Commercial, Enterprise) |
| **Analyst Recognition** | Gartner MQ Leader (EPP 2024) |

## Product Portfolio (XDR Components)

| Component | Coverage Domain |
|-----------|----------------|
| Singularity Endpoint | EPP + EDR (Windows, macOS, Linux) |
| Singularity Identity | Identity threat detection (Attivo Networks tech - AD, deception) |
| Singularity Cloud Security | CNAPP (CWPP + CSPM + CIEM; formerly PingSafe) |
| Singularity Network Discovery | Network visibility, device fingerprinting, rogue device detection |
| Singularity Mobile | Mobile threat defense (iOS, Android) |
| Singularity Data Lake | Cloud data lake for third-party data ingestion |
| PurpleAI | Generative AI security analyst |
| Vigilance | Managed detection and response (MDR) |

## Key Capabilities

- **Storyline Technology**: Patented auto-correlation linking related events into coherent attack narratives at endpoint level
- **Autonomous Response**: Automated kill, quarantine, rollback without cloud connectivity
- **Ransomware Rollback**: Automatically restores files encrypted by ransomware to pre-attack state (Windows) -- unique capability
- **PurpleAI**: Natural language interface for querying Data Lake and accelerating threat hunting
- **Star Rules**: Custom detection rules for proactive threat hunting across the data lake
- **RemoteOps**: Built-in remote scripting and management for response actions

## Strengths

- Autonomous AI-first approach (agent works without cloud connectivity)
- Ransomware rollback -- only XDR vendor with native file restoration
- Storyline technology for excellent automated investigation
- Speed: detection to remediation in seconds without human intervention
- Singularity Data Lake for open, flexible XDR data ingestion
- Strong identity security (Attivo Networks acquisition)
- Consistently high MITRE ATT&CK scores (especially autonomous detection)
- Strong Linux and container/Kubernetes protection

## Weaknesses

- No native email security
- No native NDR (limited to device discovery)
- Smaller company scale than Microsoft, CrowdStrike, Palo Alto
- Cloud security capabilities (PingSafe) still being integrated
- Data Lake still building breadth of parsers/dashboards vs. mature SIEMs
- Brand perception as "endpoint-only" company (changing)

## Integration Ecosystem

- Singularity Marketplace: growing pre-built integrations
- Data Lake ingests from: firewalls (Palo Alto, Fortinet, Check Point), email (Proofpoint, Mimecast), identity (Okta, Azure AD), cloud (AWS, Azure, GCP), NDR (Vectra, ExtraHop, Darktrace)
- REST APIs for SIEM/SOAR integration
- SIEM: Splunk, QRadar, Sentinel, Sumo Logic
- SOAR: XSOAR, Splunk SOAR, Swimlane, Tines
- ITSM: ServiceNow, Jira

## Ideal For

- Organizations wanting autonomous, AI-driven threat response
- Environments requiring offline/air-gap agent resilience
- Enterprises concerned about ransomware (rollback capability)
- Linux/container-heavy cloud workloads
- Organizations wanting an open data lake for multi-vendor XDR
