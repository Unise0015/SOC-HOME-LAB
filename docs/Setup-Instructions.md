# SOC Lab Setup Instructions

## Virtual Machine Setup

1. Install VirtualBox and create three VMs:
   - Ubuntu Server (Monitoring/SIEM)
   - Windows 10 (Target Endpoint)
   - Kali Linux (Attacker)

2. Configure network adapters on each VM:
   - Adapter 1: NAT for internet access
   - Adapter 2: Host-Only or Internal Network for isolated lab traffic

## Software Installation and Configuration

### Ubuntu Server
- Install Splunk Enterprise; configure as the central log indexer.
- Install Wazuh Manager for host-based intrusion detection.
- Set up auditd for kernel-level system auditing.

### Windows 10
- Install Sysmon with a suitable configuration for detailed process and network event logging.
- Deploy Wazuh Agent for endpoint monitoring and log forwarding to the manager.
- Configure Splunk Universal Forwarder to send event data to the Splunk indexer.
- Use EvtxECmd for offline Windows Event Log parsing when needed.

### Kali Linux
- Use built-in tools (Nmap, Hydra, etc.) to run controlled scans and brute-force attempts against the Windows target.

### pfSense and Snort
- Deploy pfSense as the lab firewall; configure Snort IDS for network-level detection.
- Forward Snort alerts and pfSense logs to Splunk via syslog.

## Running Attack Simulations

- Launch reconnaissance and brute-force attacks from Kali Linux.
- Monitor detection alerts on the Splunk dashboard in real time.
- Correlate logs from Sysmon, Wazuh, Snort, and auditd to trace attack activity.
