# Risk Register — Information Security Portfolio Project

## What This Is

A realistic information security risk register modeled on NIST Cybersecurity Framework (CSF) 2.0 principles. It covers 20 identified risks across a small professional services organization, documenting assets, threats, vulnerabilities, likelihood, impact, risk scores, and mitigations in a consistent, auditable format.

The register is available as both a Markdown table and a structured CSV that may be imported into GRC tools, spreadsheet platforms, or used as a standalone reference artifact.

This is primarily a portfolio project that can be used as a reference guide for furture information security projects, risk managment resources, and educational purposes. 

---

## Why It Matters

Risk registers are a foundational deliverable in any security program. They give organizations a living document to:

- Prioritize remediation efforts by quantified risk score
- Demonstrate due diligence to auditors, regulators, and clients
- Map threats and vulnerabilities to specific assets
- Track mitigation status over time

For small and mid-size businesses — particularly those subject to the **FTC Safeguard Rules** or **IRS WISP requirements** — a well-maintained risk register is not optional. It is a compliance obligation and an operational necessity. Without it, organizations are reacting to incidents rather than managing risk.

---

## What This Demonstrates

| Skill | How It Appears Here |
|---|---|
| **Risk identification & scoring** | 20 realistic risks with calculated scores (Likelihood × Impact, 1–5 scale) |
| **Asset-centric thinking** | Each risk anchored to a specific asset, not a vague category |
| **NIST CSF 2.0 alignment** | Mitigations mapped to Govern, Identify, Protect, Detect, Respond, Recover functions |
| **Threat/vulnerability separation** | Threat (the *what*) and vulnerability (the *why it works*) kept distinct |
| **Practitioner realism** | Risks reflect the actual threat landscape for professional services SMBs |
| **Documentation hygiene** | Consistent field structure, ready for GRC tool ingestion or client delivery |

---

## Repository Structure

```
risk-register/
├── README.md          
├── overview.md        
└── examples/
    └── risk-register.csv       
    └── risk-register.md           
```

---

## Framework Alignment

This register is built around **NIST CSF ()2.0)**, my preferred industry standard for cybersecurity risk management based on my professional background and current practices. The six core functions, **Govern, Identify, Protect, Detect, Respond, Recover**, inform both how risks are categorized and how mitigations are framed.

Where applicable, this is also in alignment and guided by the below compliance and industry standards:
- **IRS Publication 4557** (Safeguarding Taxpayer Data)
- **FTC Safeguard Rules** (16 CFR Part 314) for financial services firms
- **NIST SP 800-30** risk assessment methodology

---

## Risk Scoring Methodology

Risks are scored on a simple 5×5 matrix:

**Risk Score = Likelihood (1–5) × Impact (1–5)**

| Score Range | Rating |
|---|---|
| 1–4 | Low |
| 5–9 | Moderate |
| 10–14 | High |
| 15–25 | Critical |

See `overview.md` for the full rubric and scoring rationale.

---

*This is a portfolio artifact. Organization names, system names, and specific data are illustrative and do not represent any real entity.*
