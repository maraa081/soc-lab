# Detection Validation Reports

This folder contains validation reports for each detection implemented in the lab.  
Each report documents the attack simulation, the alert generated, and the analyst conclusion.

---

## Report Index

| Report | Scenario | Date | Status |
|--------|----------|------|--------|
| [SSH Brute Force – Detection Validation](ssh-bruteforce-validation.md) | SSH Brute Force | 2025 | Validated |

---

## Validation Methodology

Each detection is validated using the following process :

**1. Pre-conditions**
- Wazuh agent is running on the target machine
- Attack machine has network access to the target
- Wazuh dashboard is accessible

**2. Attack execution**
- Attack is launched from Kali Linux
- Tools and commands are documented

**3. Alert verification**
- Wazuh dashboard is checked for expected alerts
- Rule ID, level, and description are confirmed
- Source IP and target are verified

**4. Log analysis**
- Raw logs are reviewed to confirm detection accuracy
- False positive risk is assessed

**5. Conclusion**
- Detection is marked as Validated, Partial, or Failed
- Improvement notes are added if needed

---

## SSH Brute Force – Detection Validation

### Attack Details

| Field | Value |
|-------|-------|
| Date | 2025 |
| Attacker | Kali Linux – 192.168.63.101 |
| Target | Ubuntu1 – 192.168.63.109 |
| Tool | Hydra |
| Command | `hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://192.168.63.109` |

---

### Expected Alerts

| Rule ID | Description | Expected Level |
|---------|-------------|----------------|
| 5760 | SSH brute force detected | 10 |
| 5710 | Login attempt with non-existent user | 5 |
| 5715 | SSH authentication success | 3 |

---

### Results

| Rule ID | Fired | Level | Notes |
|---------|-------|-------|-------|
| 5760 | Yes | 10 | Alert fired after ~10 failed attempts |
| 5710 | Yes | 5 | Multiple invalid usernames detected |
| 5715 | Yes | 3 | Successful login detected |

---

### Analyst Notes

- Detection triggered as expected
- Wazuh correctly identified the brute force pattern
- No false positives observed during the test window
- **Gap identified** : no alert correlating brute force + success from same IP → custom rule 100001 created

---

### Conclusion

**Detection validated**  
The SSH brute force scenario is correctly detected by native Wazuh rules.  
A custom rule has been developed to improve correlation between failed and successful attempts.
