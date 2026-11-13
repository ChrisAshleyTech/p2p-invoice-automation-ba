# P2P Invoice Automation: Business Analysis Package

A complete business analysis package for moving accounts payable (AP) invoice processing from paper and email approvals to an automated ERP workflow with 3-way match and segregation-of-duties (SoD) controls.

The company, Harborline Distribution, and all figures are fictional and used for illustration.

## The problem

Invoices arrive by mail and email, are keyed by hand, and are approved by forwarding emails. An internal audit found:

- **Duplicate payments**: the same invoice keyed and paid twice
- **Late-payment penalties** and missed early-pay discounts
- **An SoD conflict**: one AP clerk could both create vendors and release payments

## Objectives

| ID | Objective | Target |
| --- | --- | --- |
| BO-01 | Cut invoice cycle time | 12 days to 4 |
| BO-02 | Stop duplicate payments | 0 per quarter |
| BO-03 | Capture early-pay discounts | 80% taken |
| BO-04 | Close the SoD audit finding | 0 users with a conflicting role pair |
| BO-05 | Reduce manual keying | 70% of invoices auto-matched |

## What's in the package

| Artifact | What it shows |
| --- | --- |
| **As-is vs to-be process flow** | Today's manual flow vs the automated flow: OCR capture and duplicate check, 3-way match with an exception queue, approval routing by amount, payment run by Treasury |
| **Gap analysis** | 5 gaps, each with its root cause, the future state and the requirements that close it |
| **Requirements** | 21 traced requirements (5 business, 12 functional, 4 non-functional), prioritized with MoSCoW |
| **SoD matrix** | 7 P2P duties split across 7 roles, 7 conflict rules (SOD-01 to SOD-07), and mitigating controls |
| **UAT test plan** | 18 test cases covering invoice capture, duplicate detection, 3-way match and exceptions, tiered approval routing, payment runs, SoD enforcement and audit logging, with entry and exit criteria |

## Files

- `P2P-Invoice-Automation-BA-Package.pdf`: process flow, gap analysis, requirements and SoD matrix
- `P2P Invoice Automation — UAT Test Plan.xlsx`: the 18 UAT test cases

## Highlights

- **Controls designed in, not audited after.** The SoD rules block conflicting role assignments at the point of access, and every approval, rejection and override is logged.
- **Exception-first testing.** Half the UAT cases test what goes wrong: price variance over tolerance, invoices with no goods receipt, a buyer trying to approve their own invoice, a vendor bank change with no second approver.
- **Traceability.** Every requirement traces to a business objective and forward to the UAT tests that prove it.

## Related project

The SoD rules in this package can be run against a user list with my [SoD Conflict Detector](https://sod-conflict-detector.vercel.app) ([repo](https://github.com/ChrisAshleyTech/sod-conflict-detector)).

## About me

Christopher Ashley: 16+ years in controls, audit and ERP administration (JDE, PeopleSoft, Tyler Munis, CargoWise). I've found these SoD conflicts in real ERPs as an auditor; this project shows the process design that prevents them.
