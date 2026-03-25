# SOC Lab Roadmap

This project is intended to evolve over time into a complete cyber defense lab.  
Each phase builds on the previous one to simulate a realistic SOC environment.

---

## Phase 1 – Basic Monitoring 

**Goals**
- [x] Deploy Wazuh Manager
- [x] Deploy Wazuh agents
- [x] Collect system logs
- [x] Collect authentication logs
- [x] Validate agent communication with manager

---

## Phase 2 – Attack Simulation 

**Goals**
- [x] Simulate SSH brute force
- [x] Simulate network scans
- [ ] Simulate web attacks
- [x] Observe alerts in Wazuh

**Tools** : Kali Linux, Nmap, Hydra

---

## Phase 3 – Detection Engineering 

**Goals**
- [x] Create detection use cases
- [x] Map detections to MITRE ATT&CK
- [x] Write custom Wazuh rules
- [ ] Write Sigma rules
- [ ] Reduce false positives
- [ ] Document all rules in detections/

---

## Phase 4 – Network Monitoring 

**Goals**
- [ ] Deploy Suricata
- [ ] Analyze network traffic
- [ ] Detect reconnaissance activity
- [ ] Integrate Suricata alerts into Wazuh

---

## Phase 5 – Automation 

**Goals**
- [x] Automate agent deployment (Bash scripts)
- [ ] Automate defensive actions
- [ ] Introduce Ansible playbooks
- [ ] Script to reset lab to clean state

---

## Phase 6 – Advanced Lab 

**Goals**
- [ ] Integrate Zeek
- [ ] Improve detection coverage
- [ ] Build incident response playbooks
- [ ] Cover all major MITRE ATT&CK tactics with at least one scenario
- [ ] Explore Wazuh active response (auto-block attacking IP)
