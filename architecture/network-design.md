# SOC Lab Network Architecture

## Overview

This lab simulates a small enterprise environment monitored by a Security Operations Center (SOC).

The goal is to practice:

- security monitoring
- log collection
- attack detection
- incident investigation
- defensive automation

The infrastructure is built using virtual machines.

---

# Network Segmentation

The lab is divided into several network zones.

## Attacker Network

Simulates an external attacker.

Network:

10.0.10.0/24

Machine:

kali (Kali Linux)

Purpose:

- scanning
- brute force attacks
- exploitation testing

---

## DMZ

Public-facing services exposed to the attacker.

Network:

10.0.20.0/24

Machines:

web01 (Ubuntu + Apache + SSH)

Purpose:

- simulate internet-facing services
- initial attack surface

---

## Internal Network

Represents internal systems.

Network:

10.0.30.0/24

Machines:

user01 (Ubuntu workstation)

Purpose:

- simulate internal activity
- lateral movement scenarios

---

## SOC / Monitoring Network

Security monitoring infrastructure.

Network:

10.0.40.0/24

Machines:

wazuh-server

Purpose:

- log collection
- security monitoring
- alert analysis

---

# Security Monitoring Stack

Current tools:

- Wazuh Manager
- Wazuh Agents
- Linux system logs
- SSH authentication logs

Future additions:

- Suricata (network IDS)
- Zeek (network telemetry)
- automated response scripts

---

# Future Improvements

- add IDS sensors
- implement network monitoring
- detection engineering
- automation with Ansible
