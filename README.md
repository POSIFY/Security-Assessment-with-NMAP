# Security Assessment with NMAP

**Overview**

This portfolio demonstrates my practical skills, analytical thinking, and communication ability as a cybersecurity analyst. It is intentionally structured to serve two purposes:
* Recruiter‑facing portfolio: Clearly shows what I can do, how I think, and how I document security work.
* Beginner‑friendly guide: Helps new cybersecurity learners understand Nmap from the ground up without being overwhelmed.

The focus is not just on running commands, but on why they are used, what the results mean, and how they support security decisions.

**Tool Introduction: Nmap**
Nmap (Network Mapper) is an open‑source tool used for:
* Host discovery
* Port scanning
* Service and version detection
* OS fingerprinting
* Vulnerability discovery (via scripts)

It is commonly used by:

1. Security analysts
2. Penetration testers
3. Blue teams for network auditing

**Lab Environment**
Scanning Host: Kali Linux
Target Option: Metasploitable2 (local lab)

*All scans in this portfolio are conducted in a controlled and authorized environment.*

---
### Phase 1: Host Discovery
Objective

Identify live hosts on a network before deeper scanning. This reduces noise and improves efficiency.

**Command**

```nmap -sn 172.20.10.0/28```

**Explanation**
-sn: Ping scan (no port scan)
Discovers which IPs are alive

**Analyst Insight**
This step is critical in large networks to avoid scanning inactive systems and triggering unnecessary alerts.
<img width="1031" height="781" alt="image" src="https://github.com/user-attachments/assets/e060e9a4-4931-44ba-ba11-ee7f02168b1c" />

---

### Phase 2: Basic Port Scanning
**Objective**

Identify open TCP ports on a target system.

**Command**

```nmap 172.20.10.5```

**Explanation**

**Default scan**
Scans the most common 1000 TCP ports

**Analyst Insight**
Open ports reveal potential attack surfaces. Even a single exposed service can become an entry point if misconfigured.
<img width="1105" height="825" alt="image" src="https://github.com/user-attachments/assets/4eef2b80-095a-4ce9-b0fd-3a4c73cdbc8e" />

---

### Phase 3: Full TCP Port Scan
**Objective**

Ensure no open ports are missed.

**Command**
```nmap -p- 172.20.10.5```

**Explanation**

-p-: Scans all 65,535 TCP ports

**Analyst Insight**
Attackers often hide services on uncommon ports. A full scan removes blind spots during reconnaissance.

---

### Phase 4: Service and Version Detection
**Objective**

Identify what services are running and their versions.

**Command**
```nmap -sV 172.20.10.5```
**Explanation**

-sV: Detects service versions

**Analyst Insight**
Knowing the exact version helps correlate services with known vulnerabilities (CVEs).

