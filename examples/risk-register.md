[risk-register.md](https://github.com/user-attachments/files/26962185/risk-register.md)
# Risk Register

**Organization:** Apex Professional Services LLC (Illustrative)

**Assessment Date:** 2025-Q2

**Assessor:** Information Security Contractor

**Framework:** NIST CSF 2.0

**Scope:** All information assets supporting client data processing and firm operations

---

> **Scoring:** Risk Score = Likelihood (1–5) × Impact (1–5) | Low: 1–4 | Moderate: 5–9 | High: 10–14 | Critical: 15–25
> All scores reflect **inherent risk** (pre-mitigation).

---

| ID | Asset | Threat | Vulnerability | L | I | Score | Rating | Mitigation | CSF Function | Status |
|----|-------|--------|--------------|---|---|-------|--------|-----------|-------------|--------|
| R-01 | Employee Workstations | Phishing — credential harvesting via email lure | Staff lack consistent training; no email filtering with sandboxing | 5 | 4 | **20** | Critical | Deploy email security gateway with attachment sandboxing; conduct phishing simulation training quarterly | PR / GV | In Progress |
| R-02 | Cloud File Storage (SharePoint/OneDrive) | Unauthorized access — compromised staff credentials used to exfiltrate client files | No MFA enforced on Microsoft 365 accounts | 4 | 5 | **20** | Critical | Enforce MFA for all M365 accounts via Conditional Access; disable legacy auth protocols | PR.AA | Planned |
| R-03 | Tax Preparation Software (Cloud-Hosted) | Account takeover — attacker gains access to client tax data via stolen credentials | Shared or weak passwords; no MFA on tax software accounts | 4 | 5 | **20** | Critical | Enforce unique strong passwords via password manager; enable MFA on all tax software accounts | PR.AA | Planned |
| R-04 | Local File Server | Ransomware encryption of client files and firm records | No endpoint detection; backups stored on the same network segment | 3 | 5 | **15** | Critical | Deploy EDR on all endpoints; move backups to immutable off-site/cloud storage; segment backup network | PR / RC | Planned |
| R-05 | Employee Workstations | Malware installation via drive-by download or removable media | Workstations lack current AV/EDR; USB ports uncontrolled | 4 | 3 | **12** | High | Deploy managed EDR solution; enforce USB device control policy via GPO or MDM | PR.PS | In Progress |
| R-06 | Staff Email Accounts | Business Email Compromise (BEC) — attacker impersonates executive to redirect payment | No DMARC/DKIM/SPF enforcement; staff not trained on wire fraud indicators | 3 | 4 | **12** | High | Implement DMARC (p=reject), DKIM, and SPF; conduct BEC awareness training; add payment verification callback procedure | PR / GV | Planned |
| R-07 | Payroll Platform (Third-Party SaaS) | Supply chain compromise — payroll vendor breach exposes employee PII and banking data | Minimal vendor security assessment conducted at onboarding | 2 | 5 | **10** | High | Conduct annual vendor security review; review vendor SOC 2 reports; define contractual security requirements | ID.SC | Planned |
| R-08 | Client PII (All Systems) | Insider threat — staff member intentionally or accidentally exfiltrates client records | No data loss prevention controls; excessive access permissions; no activity logging | 2 | 5 | **10** | High | Implement least-privilege access model; enable audit logging on file server and cloud storage; deploy basic DLP rules | PR.AA / DE | Planned |
| R-09 | Firm Network (Router/Firewall) | Network intrusion — attacker exploits unpatched vulnerability in perimeter device | Firewall firmware not on a patched update schedule | 3 | 3 | **9** | Moderate | Establish monthly patch review cycle for network devices; enable automatic firmware updates where supported | PR.PS | Not Started |
| R-10 | Employee Workstations | Unpatched OS/application vulnerabilities exploited via known CVEs | No formal patch management process; workstations updated ad hoc | 4 | 3 | **12** | High | Implement centralized patch management (e.g., WSUS, Intune); set SLA of 14 days for critical patches | PR.PS | Not Started |
| R-11 | Client Portal (Web Application) | Brute force or credential stuffing attack on client login portal | No account lockout policy; no rate limiting; no MFA for clients | 3 | 4 | **12** | High | Enable account lockout after 5 failed attempts; implement rate limiting; offer/require MFA for client accounts | PR.AA | Planned |
| R-12 | Physical Office (Reception/Workstations) | Unauthorized physical access — visitor or contractor accesses unlocked workstation | Workstations not configured to auto-lock; visitor access not formally managed | 3 | 3 | **9** | Moderate | Configure 5-minute screen lock via GPO; establish visitor sign-in log; escort policy for non-staff in work areas | PR.AA / GV | Not Started |
| R-13 | Staff Mobile Devices (BYOD) | Lost or stolen device exposes client data accessed via mobile apps | No MDM; no device encryption requirement; no remote wipe capability | 3 | 4 | **12** | High | Implement MDM policy requiring encryption and remote wipe; restrict client data access to managed devices | PR.DS / PR.AA | Not Started |
| R-14 | Data Backups | Backup failure — restores unavailable when needed following incident | Backups never tested; restore procedures undocumented | 2 | 5 | **10** | High | Establish quarterly backup restore tests; document and store recovery procedures; assign backup owner | RC.RP | Not Started |
| R-15 | All Systems | Prolonged outage due to hardware failure or ISP disruption with no continuity plan | No documented business continuity or disaster recovery plan | 2 | 4 | **8** | Moderate | Develop and annually test a basic BCP/DRP covering critical systems and communication procedures | RC / RS | Not Started |
| R-16 | Staff Accounts (All Platforms) | Account persistence — former employee retains access after termination | No formal offboarding checklist; account deprovisioning done manually and inconsistently | 3 | 4 | **12** | High | Create and enforce formal offboarding procedure with account deactivation within 24 hours of separation | PR.AA / GV | Not Started |
| R-17 | Wireless Network | Rogue device or eavesdropping on unsegmented guest Wi-Fi | Guest and corporate Wi-Fi share the same network segment | 2 | 3 | **6** | Moderate | Segment guest Wi-Fi onto isolated VLAN with no access to internal resources; implement WPA3 | PR.PS | Planned |
| R-18 | Security Program (Overall) | Regulatory non-compliance — failure to meet FTC Safeguard Rule requirements | No formal written information security plan (WISP) or designated security coordinator | 3 | 4 | **12** | High | Develop and maintain a written WISP aligned to FTC Safeguard Rules; designate a qualified individual | GV | In Progress |
| R-19 | Incident Response Capability | Slow or ineffective response to security incident due to lack of preparation | No incident response plan; staff unaware of reporting procedures | 3 | 4 | **12** | High | Develop and tabletop-test an incident response plan annually; define roles, escalation paths, and notification obligations | RS.MA / RS.CO | Not Started |
| R-20 | Sensitive Data (Emails & Documents) | Unencrypted transmission of client PII or tax data via email | Staff routinely email sensitive documents without encryption | 4 | 3 | **12** | High | Deploy email encryption solution (e.g., M365 sensitivity labels or Virtru); train staff on handling requirements | PR.DS | Not Started |

---

## Summary Dashboard

| Rating | Count | Risk IDs |
|--------|-------|----------|
| Critical (15–25) | 4 | R-01, R-02, R-03, R-04 |
| High (10–14) | 11 | R-05, R-06, R-10, R-11, R-13, R-14, R-16, R-18, R-19, R-20, R-08 |
| Moderate (5–9) | 5 | R-07 (pending re-score), R-09, R-12, R-15, R-17 |
| Low (1–4) | 0 | — |

---

## Mitigation Status Summary

| Status | Count |
|--------|-------|
| In Progress | 3 |
| Planned | 9 |
| Not Started | 8 |
| Completed | 0 |

---

*Last reviewed: 2025-Q2. Next scheduled review: 2025-Q4 or following any significant system change or security incident.*
