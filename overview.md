# Risk Register — Methodology & Overview

## Purpose

This is a complimentary document to be used alongside the risk register and it explains the methodology used in their development. It assists to explain how risks were identified and scored, and also how the work aligns to the framework I am use in my information security practices, NIST CSF (2.0). It is intended to provide the why behind each structural decision. 

Note: For more depth on frameworks, mock company compliance needs, and other resources used in the development and methodology behind this project, look at the Reference section at the bottom and the links.

---

## Organizational Context

The risk register is developed in the scope of a small professional services firm (accounting, financial, tax) (10-50 employees) that handles sensitive client data such as financial records, tax documents, and personally identifiable information (PII). This mock firm was chosen deliberately to showcase my professional background and industry familiarity, it represents a client environment I typically would have an understanding of based on my current experience. Additionally, it allows for the representation of a very broad range of firms that may be lacking in effective information security resources and may not meet industry compliance requirements. It also  showcases a typical industry with real-world regulations such as the FTC Safeguard Rules and IRS WISP where the NIST CSF can assist in framing a security posture that addresses risk and remediates them through implementing a security plan that aligns with NIST CSF and compliance requirements (WISP development). 

The organization relies on a mix of cloud-hosted SaaS tools, a local file server, employee workstations, and third-party vendors for payroll and tax preparation software.

---

## Risk Identification Approach

Risks were identified using a combination of:

1. **Asset enumeration** — Starting with a list of critical information assets (endpoints, file servers, cloud accounts, third-party integrations, staff) rather than starting with threats. Asset-first identification prevents gaps.

2. **Threat modeling** — For each asset, plausible threat actors and threat events were identified. Sources include the NIST SP 800-30 threat catalog and common incident patterns reported in Verizon DBIR data for the SMB professional services sector.

3. **Vulnerability mapping** — Each threat was paired with the specific weakness or condition that enables it. Threat and vulnerability are kept as separate fields to maintain precision and avoid conflating "what could happen" with "why it could happen."

4. **SMB realism check** — Risks were filtered for relevance to the organizational context. Enterprise-only risks (e.g., BGP hijacking, nation-state APT lateral movement at scale) were excluded in favor of risks that practitioners actually encounter in this environment.

---

## Scoring Rubric

Risk scores use a standard **5×5 Likelihood × Impact matrix**. All scores are inherent risk (pre-mitigation) unless otherwise noted.

### Likelihood Scale

| Score | Label | Description |
|---|---|---|
| 1 | Rare | Unlikely in normal operations; would require unusual circumstances |
| 2 | Unlikely | Could occur but not expected within a typical year |
| 3 | Possible | Reasonably expected to occur at least once in 1–3 years |
| 4 | Likely | Expected to occur at least once per year under current conditions |
| 5 | Almost Certain | Expected to occur multiple times per year or is already occurring |

### Impact Scale

| Score | Label | Description |
|---|---|---|
| 1 | Negligible | Minimal operational effect; no client impact; no regulatory exposure |
| 2 | Minor | Limited disruption; recoverable quickly; low reputational risk |
| 3 | Moderate | Meaningful disruption; possible client notification required; measurable cost |
| 4 | Significant | Extended downtime or breach; regulatory scrutiny likely; client trust affected |
| 5 | Severe | Major data breach or prolonged outage; regulatory action; potential business failure |

### Risk Rating Thresholds

| Score Range | Rating | Suggested Response Timeline |
|---|---|---|
| 1–4 | Low | Monitor; address in routine cycle |
| 5–9 | Moderate | Plan mitigation within 90 days |
| 10–14 | High | Prioritize; mitigate within 30 days |
| 15–25 | Critical | Immediate action required |

---

## NIST CSF 2.0 Alignment

NIST CSF 2.0 organizes cybersecurity activities into six core Functions. Mitigations in the risk register are framed around these functions to make the control rationale explicit.

| Function | Abbreviation | What It Covers |
|---|---|---|
| Govern | GV | Policies, roles, risk strategy, compliance |
| Identify | ID | Asset management, risk assessment, supply chain |
| Protect | PR | Access control, awareness training, data security |
| Detect | DE | Continuous monitoring, anomaly detection |
| Respond | RS | Incident response planning and execution |
| Recover | RC | Recovery planning, communications, improvements |

Each mitigation in the register implicitly maps to one or more of these functions. For example, enforcing MFA on cloud accounts is a Protect(PR.AA) control. Establishing an incident response plan is a Respond (RS.MA)control.

Note: For a full explanation and deeper understanding of the NIST functions and their usage in the risk register please reference the NIST resources noted below in the References section.

---

## Field Definitions

| Field | Definition |
|---|---|
| **ID** | Sequential risk identifier for tracking and reference |
| **Asset** | The information asset, system, or resource at risk |
| **Threat** | The threat event or threat actor action that could cause harm |
| **Vulnerability** | The weakness or condition that allows the threat to succeed |
| **Likelihood (L)** | Probability of the threat event occurring (1–5) |
| **Impact (I)** | Magnitude of harm if the threat event occurs (1–5) |
| **Risk Score** | L × I |
| **Rating** | Qualitative label derived from score range |
| **Mitigation** | Primary control(s) to reduce likelihood or impact |
| **CSF Function** | Primary NIST CSF 2.0 function the mitigation supports |
| **Status** | Current implementation status of the mitigation |

---

## Limitations & Intended Use

This register is a point-in-time snapshot. In practice, risk registers should be reviewed at minimum annually and following significant changes (new systems, personnel changes, incidents, regulatory updates).

Scores reflect the assessor's judgment and should be validated with subject matter experts and, where possible, threat intelligence relevant to the organization's sector and geography.

This portfolio artifact is illustrative. Adapting it for a real organization requires scoping to that organization's actual asset inventory, threat environment, and regulatory obligations.

---

## References

- NIST Cybersecurity Framework 2.0 — https://www.nist.gov/cyberframework (https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf)
- NIST SP 800-30 Rev. 1 — Guide for Conducting Risk Assessments (https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-30r1.pdf)
- Verizon Data Breach Investigations Report (2025)(https://www.verizon.com/business/resources/infographics/2025-dbir-smb-snapshot.pdf)
- IRS Publication 4557 — Safeguarding Taxpayer Data (https://www.irs.gov/pub/irs-pdf/p4557.pdf)
- FTC Safeguard Rules — 16 CFR Part 314 (https://www.ftc.gov/business-guidance/resources/ftc-safeguards-rule-what-your-business-needs-know)(https://www.ecfr.gov/current/title-16/chapter-I/subchapter-C/part-314)
