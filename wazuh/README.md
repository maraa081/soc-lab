# Wazuh Integration

This directory documents the deployment of Wazuh components in the SOC lab.

## Goals

- Connect a monitored Linux server to a remote Wazuh manager
- Collect authentication and web server logs
- Observe detections related to SSH brute force, web attacks, and vulnerability exposure
- Document installation, configuration, validation, and cleanup steps

## Scope

This section focuses on:
- Wazuh agent deployment
- Agent to manager connectivity
- Example agent configuration
- Cleanup and rollback procedures
- Issues encountered during deployment

## Target architecture

- Wazuh manager: `192.168.63.101`
- Monitored host: Ubuntu 22.04 / Debian 12 recommended
- Host-only network for SOC visibility
- NAT interface for Internet access when required
