# VPN-Security-Assessment-Lab
An incident response lab focusing on VPN traffic analysis, MFA event correlation, and long-term enterprise access strategy

## Objective
This project is a digital forensics and incident response (DFIR) investigation focused on analyzing a remote access VPN session to determine if the activity is Legitimate, Suspicious, or Compromised. The core objective is to analyze evidence telemetry, build a timeline, handle evidentiary uncertainty, and design a secure architecture response.

## Methodology
The investigation is strictly observational. Active network scanning, brute-forcing, exploitation, and persistence mechanisms were explicitly out of scope for this environment.

### Phase 1: Investigation & Initial Verdict
Analyzed a unified dataset of seven evidence sources (`E01` to `E07`) alongside cryptographic hash verification files (`SHA256SUMS.txt` and `PACKAGE_SHA256SUMS.txt`) to ensure evidence integrity. 
Telemetry sources analyzed include:
* VPN outer and inner traffic
* VPN authentication and MFA activity
* Internal access activity
* User baseline and endpoint context

**Deliverable:** A documented timeline establishing a verdict (Legitimate, Suspicious, or Compromised) and a stated confidence level (Low, Medium, or High), backed by confirming and contradictory evidence.

### Phase 2: Evidence Reassessment
Evaluated new telemetry introduced mid-investigation to determine if the initial hypothesis should be Maintained, Revised, or Withdrawn based on changing facts.

### Phase 3: Architecture & Response Decision
Beyond the immediate incident response and containment, this phase evaluates long-term access architecture. It provides a control model recommendation between traditional VPN, Zero Trust Network Access (ZTNA), or a Hybrid approach. 

The architecture decision accounts for:
* Managed remote employees vs. BYOD/contractors
* Internal web applications vs. legacy services
* Privileged and emergency/break-glass access
* Identity assurance, device trust, and least privilege

## Repository Structure & Deliverables
The project files are organized to separate the raw evidence and challenge guidelines from the active analysis and final presentations:

* **`/Docs`**: Contains the core scoping rules, scenario background, and deliverable constraints.
* **`/Evidence`**: Contains the raw network captures (`.pcap`), authentication logs, and endpoint context files used for the investigation, validated against `SHA256SUMS.txt`. *(Note: The personal WireGuard configuration file is strictly excluded from this repository to maintain environment security.)*
* **`/analysis`**: Detailed markdown files tracking the timeline, confirmed observations, and unresolved questions.
* **`/architecture`**: Strategic recommendations for access policies, monitoring, and detection opportunities.
* **`/presentation`**: A concise, 4-slide executive presentation summarizing the incident timeline, key evidence, architecture decision, and immediate next steps.

## Tools & Environment
* **Network Analysis:** Wireshark
* **Connectivity:** WireGuard
* **Documentation:** PDF reader, text editors, spreadsheet applications

---
*Focused on Blue Teaming, Digital Forensics, Incident Response, and Network Security.*
