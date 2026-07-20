# Reverse TCP Payload Penetration Testing (Metasploit)

**Timeframe:** Jan 2025 – May 2025
**Tools:** Metasploit, MSF Venom, Meterpreter, Python (HTTP server), NVD, CVSS

## Objective

Demonstrate the full attack lifecycle of a reverse TCP payload against a lab target — from payload generation through delivery, execution, and post-exploitation — and translate the technical findings into a documented vulnerability report with CVSS scoring, the way a real engagement would require.

## Environment


## Methodology

1. **Payload generation** — Used `msfvenom` to generate a reverse TCP payload targeting the lab machine's OS/architecture, configuring `LHOST`/`LPORT` to match the attacker listener.
2. **Delivery** — Hosted the payload for retrieval using a lightweight Python HTTP server (`python3 -m http.server`), simulating a common delivery vector where a victim downloads and executes a file from an attacker-controlled host.
3. **Handler setup** — Configured a Metasploit `multi/handler` listener matching the payload's connect-back parameters.
4. **Execution & post-exploitation** — Upon execution on the target, obtained a Meterpreter session and used it to enumerate system information, confirming code execution and session stability.
5. **Vulnerability documentation** — Mapped the exploitation path back to the underlying vulnerability class, referenced relevant NVD entries, and assigned/validated CVSS scores to communicate severity and prioritize remediation.

## Key Findings



## Remediation Recommendations

- Enforce endpoint protection/EDR capable of detecting Meterpreter-style in-memory payloads
- Restrict outbound connections to unapproved ports/hosts to limit reverse-shell callbacks
- Apply patch management to close the specific vulnerability exploited
- User awareness training on execution of untrusted downloaded files

## Skills Demonstrated

`Exploitation & Post-Exploitation` · `Payload Engineering` · `Python Automation` · `CVSS/NVD Vulnerability Documentation` · `Technical Reporting`

---
*Lab conducted in an isolated, non-production environment for educational purposes as part of coursework.*
