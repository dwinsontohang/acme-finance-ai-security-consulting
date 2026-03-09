# Technical Solution – CISO Team

## Architecture Design

The diagram illustrates the layered security model, clearly separating external and internal AI components while integrating shared infrastructure and control layers.

<img width="540" height="736" alt="image" src="https://github.com/user-attachments/assets/a8e3a695-34ec-482f-8a97-3aa25a57ed9d" />


## Target Architecture

The architecture integrates Azure Security Copilot as a native layer on top of Azure Sentinel, ensuring a seamless transition with minimal disruption to SOC workflows.

Key architectural components include:
- **Azure Sentinel** as the central SIEM platform
- **Security Copilot** integrated via Microsoft Defender and Sentinel APIs
- **Role-based access enforcement** through Azure Active Directory and Microsoft Entra ID
- **Custom logic apps** to automate incident response, enrich alerts, and integrate third-party data
- **Secure zones and permission boundaries** established for incident data, prompts, and AI-generated output

## Security Technologies and Controls

### Identity and Access Management (IAM)
- Azure AD and Entra ID used to enforce RBAC across Copilot, Sentinel, and integrated tools
- Conditional Access and Privileged Identity Management (PIM) for elevated tasks
- Copilot access restricted to analyst roles with proper justification and approval logging

### Data Protection
- TLS 1.3 enforced across all Copilot communications
- Data masking and redaction applied to sensitive log and case content
- Microsoft Purview policies integrated to classify and protect SOC data surfaced to Copilot

### Monitoring and Visibility
- Integration with Azure Monitor and Microsoft Defender XDR to correlate Copilot activities
- Full logging of Copilot prompts, responses, and user interactions within Sentinel
- Alert tagging to distinguish AI-generated suggestions from analyst actions

### Automation and Workflow Control
- Logic Apps and Sentinel Playbooks used to manage Copilot-triggered actions
- Multi-stage approval workflows for high-impact automation tasks (e.g. account lockouts, threat containment)
- Event-driven triggers to launch Copilot analysis only under defined incident conditions

## External Services and Dependencies

- **Azure Sentinel** – Core SIEM platform
- **Azure Security Copilot** – Generative AI assistant for security operations
- **Microsoft Defender for Cloud & Endpoint** – Upstream telemetry and context enrichment
- **Microsoft Entra ID** – Federated identity, RBAC, and governance
- **Azure Logic Apps** – Automation and orchestration of security response
- **Microsoft Purview** – Information protection, DLP, and compliance tagging
- **Azure Monitor** – Infrastructure and usage telemetry

## Operational Alignment

The integration is designed to align directly with ACME Finance's existing SOC procedures. It preserves existing detection, triage, and escalation flows while adding:
- AI-assisted alert summarisation and contextual analysis
- Natural language querying for threat hunting
- Response recommendations based on historical incident patterns
- Analyst feedback loops to refine Copilot responses over time
