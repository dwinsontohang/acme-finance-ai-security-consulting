# RAID Log – CTO Team

| ID | Type | Description | Category / Area | Priority | Mitigation / Action | Owner |
|----|------|-------------|------------------|----------|---------------------|-------|
| R-CTO-01 | Risk | Incomplete implementation of encryption and access control mechanisms across AI services | Data Security | High | Enforce AES-256 at rest, TLS 1.3 in transit; apply RBAC via IAM and Kubernetes policies | Security Architect |
| R-CTO-02 | Risk | Absence of clear data classification for content used in RAG chatbots | GDPR Compliance | High | Apply tagging via Microsoft Purview and validate input/output filtering rules | Risk Lead |
| R-CTO-03 | Risk | External AI APIs or model plugins may transfer or log personal data outside approved jurisdictions | Data Residency | Medium | Use proxy layer for isolation; enforce data residency controls in design | DevSecOps Lead |
| R-CTO-04 | Risk | Delays in aligning chatbot functionality with privacy consent requirements | Regulatory Alignment | Medium | Coordinate early with client legal team on public-facing disclaimers and consent | Project Manager |
| A-CTO-01 | Assumption | All logs and prompt metadata will be stored in GDPR-compliant, client-approved environments | Data Residency | High | Validate infrastructure storage regions during Sprint 2 | DevSecOps Lead |
| A-CTO-02 | Assumption | Personal data will be excluded or anonymised before ingestion into AI systems | GDPR Compliance | High | Product team to apply data masking pipeline | Product Owner |
| A-CTO-03 | Assumption | Client legal team will provide wording for chatbot disclaimers and consent notices | Legal / UX | Medium | Schedule legal handover review during Sprint 4 | Client Sponsor |
| I-CTO-01 | Issue | Lack of classification labels during initial RAG system testing | Data Classification | Medium | Configure Microsoft Purview and reprocess data with tagging policies | Security Architect |
| I-CTO-02 | Issue | Retention policies for chatbot logs are unclear | GDPR Compliance | Low | Define log lifespan and apply policy in line with GDPR Article 5 | Risk Lead |
| D-CTO-01 | Dependency | Access to Microsoft Purview and Key Vault must be provisioned by client infrastructure team | Infrastructure Access | High | Coordinate provisioning during Sprint 1–2 | Client IT |
| D-CTO-02 | Dependency | Confirmation of GDPR policy interpretation from client compliance and legal functions | Regulatory Alignment | Medium | Host compliance working session in Sprint 2 | Client Legal |
| D-CTO-03 | Dependency | Secure architecture deployment requires baseline network segmentation and AKS readiness | Architecture Setup | High | Track client infra readiness during Sprint 2 planning | DevSecOps Lead |
