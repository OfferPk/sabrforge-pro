# SABRForge Pro (v1.0.0)

> **CCSDS 734.3-B-1 Schedule-Aware Bundle Routing (SABR) & Contact Graph Routing (CGR) Studio**  
> Complete Contact Plan Parser, Estimated Volume Consumption (EVC) Engine, Dijkstra/Yen's Earliest Delivery Path (EDP) Solver, Route Termination Time (RTT) Bounding, Contact Residual Capacity Accounting, and 10-Point Normative Aerospace Standards Auditor.

---

## 🛰️ Product Overview

SABRForge Pro is a specialized aerospace delay-tolerant networking (DTN) and deep space communications engineering suite designed for interplanetary missions (Artemis Lunar Gateway, Mars relay architectures, Deep Space Optical Communications), CubeSat swarm constellations, and defense ad-hoc space networks. It delivers a comprehensive software reference implementation and compliance auditing toolkit for the **CCSDS 734.3-B-1** (*Schedule-Aware Bundle Routing*, Blue Book, July 2019\) standard.

### Key Capabilities

- **Contact Plan Parsing & Graph Expansion**: Parses contacts (start time, stop time, data rate, capacity) and range intervals (one-way light time / OWLT) into directed time-expanded contact graphs.  
- **Estimated Volume Consumption (EVC) Calculation**: Computes exact volume liens under CCSDS 734.3-B-1 §2.4.3: \$\\text{EVC} \= M \+ N \+ \\max(0.03(M+N), 100 \\text{ bytes})\$.  
- **Earliest Delivery Path (EDP) Routing**: Computes time-optimal multi-hop paths to destination nodes, minimizing bundle delivery arrival time.  
- **Route Termination Time (RTT) Bounding**: Determines the earliest expiration time among all hops in a route to ensure transmission before contact closure.  
- **Contact Capacity Depletion & Overbooking Guard**: Tracks contact consumption and residual bytes, preventing buffer exhaustion and oversubscription on non-critical bundles.  
- **10-Point Normative Standards Auditor**: Enforces rules SABR-001 through SABR-010 to guarantee mission-readiness.  
- **Zero-Dependency Architecture**: Cross-platform pure ES6+ library, zero-dependency Python 3 CLI, and interactive HTML5 Mission Operations Console.

---

## 🚀 Quick Start

### 1\. Interactive Mission Operations Console

Open `source-code/index.html` in any modern web browser to inspect visual contact timelines, test bundle injections, evaluate multi-hop route discoveries, and run compliance audits.

### 2\. Python Command Line Interface (CLI)

View the interplanetary Contact Plan schedule:

python3 source-code/sabr\_cli.py plan

Compute Estimated Volume Consumption (EVC):

python3 source-code/sabr\_cli.py evc \--header 32 \--payload 1024

Solve Earliest Delivery Path (EDP) from Earth (Node 1\) to Mars Rover (Node 4):

python3 source-code/sabr\_cli.py route \--src 1 \--dst 4 \--payload 1024

Execute the 10-Point Normative Standards Audit:

python3 source-code/sabr\_cli.py audit

### 3\. Automated Test Suite

Run the 10 automated unit verification tests:

python3 source-code/test\_runner.py

---

## 📊 Compliance Matrix Summary

| Rule ID | Normative Checkpoint | Standard Reference | Status |
| :---: | :---- | :---- | :---: |
| **SABR-001** | Contact Plan Structure & Syntax Validity | CCSDS 734.3-B-1 §2.3 | **PASS** |
| **SABR-002** | Estimated Volume Consumption (EVC) Calculation | CCSDS 734.3-B-1 §2.4.3 | **PASS** |
| **SABR-003** | Contact Volume Capacity Accounting | CCSDS 734.3-B-1 §2.4.2 | **PASS** |
| **SABR-004** | Route Continuity & Feasibility Verification | CCSDS 734.3-B-1 §2.5.1 | **PASS** |
| **SABR-005** | Earliest Delivery Path (EDP) Routing | CCSDS 734.3-B-1 §2.5.2 | **PASS** |
| **SABR-006** | Route Termination Time (RTT) Bounding | CCSDS 734.3-B-1 §2.5.3 | **PASS** |
| **SABR-007** | Bundle Time-To-Live (TTL) & Expiration | CCSDS 734.3-B-1 §2.6 | **PASS** |
| **SABR-008** | Contact Overbooking & Capacity Depletion | CCSDS 734.3-B-1 §2.7 | **PASS** |
| **SABR-009** | Critical Bundle Priority & Custody | CCSDS 734.3-B-1 §2.8 | **PASS** |
| **SABR-010** | Proximate Next-Hop Selection & Handoff | CCSDS 734.3-B-1 §2.9 | **PASS** |

---

## 💼 Commercial & Monetization Details

- **Target Customer**: Deep-space mission flight software teams (NASA JPL, ESA ESOC, JAXA), lunar relay infrastructure operators, commercial lunar/Mars landers, and DTN researchers.  
- **Distribution Model**: Professional Developer Seat & Enterprise Ground Station Site License.  
- **Pricing**: \$349/year per developer seat or \$2,499 one-time enterprise site license.  
- **Zero Cloud Infrastructure**: Client-side and local CLI execution with zero external data transmission.