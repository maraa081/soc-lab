# SOC Lab Roadmap

This project is intended to evolve over time into a complete cyber defense lab.  
Each phase builds on the previous one to simulate a realistic SOC environment.

---

## Phase 1 – Basic Monitoring 

**Goals**
-  Deploy Wazuh Manager
-  Deploy Wazuh agents
-  Collect system logs
-  Collect authentication logs
-  Validate agent communication with manager

---

## Phase 2 – Attack Simulation 

**Goals**
-  Simulate SSH brute force
-  Simulate network scans
-  Simulate web attacks
-  Observe alerts in Wazuh

**Tools** : Kali Linux, Nmap, Hydra

---

## Phase 3 – Detection Engineering 

**Goals**
-  Create detection use cases
-  Map detections to MITRE ATT&CK
-  Write custom Wazuh rules
-  Write Sigma rules
-  Reduce false positives
-  Document all rules in detections/

---

## Phase 4 – Network Monitoring 

**Goals**
-  Deploy Suricata
-  Analyze network traffic
-  Detect reconnaissance activity
-  Integrate Suricata alerts into Wazuh

---

## Phase 5 – Automation 

**Goals**
-  Automate agent deployment (Bash scripts)
-  Automate defensive actions
-  Introduce Ansible playbooks
-  Script to reset lab to clean state

---

## Phase 6 – Advanced Lab 

**Goals**
-  Integrate Zeek
-  Improve detection coverage
-  Build incident response playbooks
- [ ] Cover all major MITRE ATT&CK tactics with at least one scenario
- [ ] Explore Wazuh active response (auto-block attacking IP)
