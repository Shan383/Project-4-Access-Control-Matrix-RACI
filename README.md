# Project 4 — Access Control Matrix & RACI

**Framework / Standard:** ISO/IEC 27001:2022 Annex A.5.15 (Access Control) · NIST CSF 2.0 PR.AA · NIST SP 800-53 Rev. 5 AC family
**Difficulty:** Beginner
**Organization used:** Aegis Northline Technologies *(fictitious organization, built for portfolio purposes)*

## Overview

This project defines role-based access control (RBAC) for a fictitious mid-sized organization and documents the end-to-end process by which that access is requested, approved, provisioned, and periodically reviewed. It builds directly on the system inventory produced in [Project 1/2](#) by mapping each in-scope system to the access level each role should hold, then assigns clear ownership across that lifecycle using a RACI matrix.

The goal is to demonstrate two core GRC skills:
- Designing least-privilege access models that map cleanly to a control framework
- Turning a process into unambiguous, auditable role assignments (RACI)

## What's inside

| File | Description |
|---|---|
| `Access_Control_Matrix.xlsx` | Role × system access matrix (None / Read / Write / Admin), plus the system inventory and control legend |
| `RACI_Chart.xlsx` | RACI matrix for the access-provisioning and periodic-review process, plus a step-by-step process narrative |
| `screenshots/access-matrix.png` | Preview of the access matrix |
| `screenshots/raci-matrix.png` | Preview of the RACI matrix |

## 1. Roles

Five representative roles were modeled, spanning both business and technical functions:

- **HR** — manages employee records and the HRIS
- **Finance** — manages the accounting/ERP system and financial data
- **IT Admin** — administers infrastructure, identity, and security tooling
- **Employee** — general workforce baseline access
- **Contractor** — restricted, time-bound access for third parties

## 2. Access Control Matrix

Each role was mapped against 10 systems carried forward from the Project 1/2 asset inventory (HRIS, Finance ERP, Email & Collaboration, File Server, Active Directory, Firewall, SIEM, CRM, Backup, and ITSM), with an access level assigned per system:

| Level | Meaning |
|---|---|
| **None** | No access |
| **Read** | View only |
| **Write** | Create / modify data within scope |
| **Admin** | Full administrative control, including configuration and user management |

The model follows least privilege throughout — for example, Finance holds Admin only on the accounting system and Write access on collaboration tools, but no access at all to infrastructure systems like the domain controller or SIEM, which are restricted to IT Admin.

![Access Control Matrix](screenshots/access-matrix.png)

## 3. Access-Provisioning Process

Access is granted and maintained through a four-stage lifecycle:

1. **Request** — Manager or HR submits a new hire / access request; IT Admin maps it against the standard role profile in the Access Control Matrix
2. **Approval** — Line manager confirms the access is job-required; the relevant system owner approves access to their system (Security/Compliance is consulted for Restricted or Admin-level access)
3. **Implementation** — IT Admin provisions the account at the approved access level and confirms completion
4. **Periodic Review** — Access is reviewed quarterly; excess or unused access is revoked, and accounts are fully deprovisioned on an employee's exit or a contractor's end date

## 4. RACI Matrix

Each activity in the process above is assigned exactly one **Accountable** owner, with Responsible, Consulted, and Informed parties defined across six roles: Requesting Manager, HR, IT Admin, System Owner, Security/Compliance, and Employee/Contractor.

| Code | Meaning |
|---|---|
| **R** | Responsible — performs the work |
| **A** | Accountable — owns the outcome, final sign-off (one per activity) |
| **C** | Consulted — two-way input before the activity completes |
| **I** | Informed — kept up to date after the fact |

![RACI Matrix](screenshots/raci-matrix.png)

## Control mapping

- **ISO/IEC 27001:2022** — Annex A.5.15 (Access control), A.5.18 (Access rights)
- **NIST CSF 2.0** — PR.AA-01 (Identity and credential management), PR.AA-05 (Access permissions and authorizations)
- **NIST SP 800-53 Rev. 5** — AC-2 (Account Management), AC-3 (Access Enforcement), AC-5 (Separation of Duties), AC-6 (Least Privilege)

## Notes

- This is a portfolio artifact built around a fictitious organization to demonstrate GRC documentation skills — it is not a live compliance deliverable.
- The system inventory in this project mirrors the structure of the Project 1/2 asset inventory; swap in real inventory data to keep the two projects consistent.

## Related projects

- Project 1/2 — Asset Inventory
- Project 3 — Core Information Security Policy Suite (ISO 27001 / NIST CSF 2.0)
