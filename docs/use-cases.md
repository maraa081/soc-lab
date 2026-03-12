# Detection Use Cases

This document describes security detection scenarios implemented in the SOC lab.

---

# SSH Brute Force

Description:

Multiple authentication attempts against an SSH service.

Tools:

Hydra

Detection Sources:

- auth.log
- Wazuh authentication alerts

Indicators:

- repeated failed login attempts
- same source IP
- short time interval

MITRE ATT&CK:

T1110 – Brute Force

---

# Network Scanning

Description:

Reconnaissance activity using network scanning tools.

Tools:

Nmap

Detection Sources:

- IDS alerts (future Suricata)
- unusual connection attempts

Indicators:

- multiple ports scanned
- short time interval

MITRE ATT&CK:

T1046 – Network Service Discovery

---

# Suspicious User Creation

Description:

Creation of a new user account on a monitored host.

Detection Sources:

- Linux system logs
- Wazuh alerts

Indicators:

- useradd command executed
- new account created

MITRE ATT&CK:

T1136 – Create Account
