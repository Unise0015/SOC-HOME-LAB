# Challenges and Lessons Learned

## Challenges
- Getting consistent log forwarding from pfSense using syslog-ng required multiple configuration attempts.
- Reliable forwarding of Windows event logs via Universal Forwarder and EvtxECmd needed troubleshooting around data inputs and permissions.
- Snort IDS generated a high volume of false positives that required rule tuning to reduce noise.
- Setting up functional network segmentation with dual adapters across all VMs took iterative testing.

## Lessons Learned
- Minor misconfigurations in log forwarding can silently break monitoring coverage.
- Correlating both network-level and host-level logs is necessary to get a clear picture of an incident.
- Detection rules need ongoing tuning; default rulesets are rarely sufficient out of the box.
- Building a lab like this is iterative—expect to revisit and adjust configurations multiple times.
