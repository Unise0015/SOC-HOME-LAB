# SOC Lab: Mini Security Operations Center for Threat Detection and Incident Response

## Overview
A home lab project simulating a small-scale Security Operations Center (SOC) environment for practicing threat detection, log analysis, and incident response. The lab reproduces common SOC workflows—attack simulation, alert triage, and log correlation—using a mix of open-source and commercial tools running on virtual machines.

## Objective
Set up a functional SOC environment to study attack lifecycles, monitor endpoint and network activity, and practice responding to simulated incidents such as network scans and brute-force attempts. The goal is to gain practical exposure to the tools and processes used in day-to-day SOC operations.

## Tools Used
- **Ubuntu Server:** Hosts Splunk Enterprise, Wazuh Manager, and auditd for centralized log collection and analysis.
- **Windows 10:** Target endpoint configured with Sysmon, Wazuh Agent, Splunk Universal Forwarder, and EvtxECmd for detailed event logging.
- **Kali Linux:** Attacker machine used to run controlled reconnaissance and brute-force attacks.
- **pfSense Firewall:** Handles network traffic filtering and monitoring.
- **Snort IDS:** Network-level intrusion detection, forwarding alerts to Splunk.

## Project Structure
See the `/docs` folder for setup steps, architecture details, and notes on challenges encountered.

## Getting Started
Refer to [Setup-Instructions.md](docs/Setup-Instructions.md) for deployment and configuration steps.

## License
MIT License.
