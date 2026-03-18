# Install Wazuh Agent on Ubuntu 22.04

## Objective

Install a Wazuh agent on the monitored Ubuntu host and connect it to the remote Wazuh manager.

## Tested environment

- OS: Ubuntu 22.04 LTS
- Wazuh manager IP: `192.168.63.101`

## Network checks

Before attempting installation, verify connectivity to the manager:

```bash
ip -br a
ping -c 3 192.168.63.101
nc -zv 192.168.63.101 1514
nc -zv 192.168.63.101 1515
