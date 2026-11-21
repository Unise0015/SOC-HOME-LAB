# SOC Lab Architecture and Network Design

## Virtualization Platform
The lab runs on VirtualBox, selected for its cross-platform support and ability to manage multiple VMs with different network configurations.

## Network Segmentation
A dual-adapter setup isolates attacker and defender traffic while still allowing log forwarding between machines.

- **Internal Network (Host-Only):** Used for communication between the Windows endpoint and the Ubuntu monitoring server.
- **External Network (NAT):** Kali Linux connects through NAT to simulate an external attacker.

Each VM has two network interfaces to keep monitoring traffic separate from attack traffic.

## Machines

### Ubuntu Server (192.168.19.10)
- Runs Splunk Enterprise and Wazuh Manager for centralized log aggregation and alerting.
- auditd configured for system-level auditing.
- Correlates host and network events.

### Windows 10 Endpoint (192.168.19.20)
- Target machine for simulated attacks.
- Generates endpoint telemetry via Sysmon; logs forwarded through Wazuh Agent and Splunk Universal Forwarder.

### Kali Linux (192.168.56.30)
- Used for controlled reconnaissance (Nmap) and brute-force attacks.
- Generates traffic and artifacts for detection testing.

