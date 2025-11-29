# System Hardening

# System Hardening

A structured guide to strengthening system security through configurations, patching, and reducing the attack surface.

---

## 1. What Is System Hardening?

System hardening is the process of securing a system by:
- Reducing vulnerabilities  
- Limiting unnecessary functionalities  
- Enforcing secure configurations  
- Minimizing exposure to attacks  

It ensures systems remain resilient against exploitation, malware, and unauthorized access.

---

## 2. Core Components of System Hardening

### **A. Firewall Configuration**
Proper firewall management restricts unauthorized traffic and enforces network rules.

#### Key Practices
- Enable the system firewall (e.g., UFW, Firewalld, Windows Defender Firewall)  
- Allow only necessary ports  
- Block unused or risky services  
- Enforce inbound/ outbound filtering  
- Log and monitor firewall activity  

#### Examples
- **Linux (UFW)**:  
  - Allow: `ufw allow 22/tcp`  
  - Deny: `ufw deny 23/tcp`  
  - Enable: `ufw enable`  

- **Windows Firewall**:  
  - Create inbound/outbound rules  
  - Restrict remote access  
  - Configure logging  

---

### **B. Patch & Update Management**
Keeping systems up to date closes security gaps.

#### Why It Matters
- Fixes known vulnerabilities  
- Prevents exploitation via outdated software  
- Improves stability and performance  

#### Best Practices
- Enable automatic updates where possible  
- Maintain a patch schedule  
- Apply vendor security advisories  
- Update OS, apps, libraries, and dependencies  

#### Examples
- **Linux**: `apt update && apt upgrade -y`  
- **Windows**: Apply monthly “Patch Tuesday” updates  

---

### **C. Disabling Unnecessary Services**
Every running service increases your attack surface.

#### Steps
1. Identify services not required  
2. Disable or remove them  
3. Prevent them from starting at boot  

#### Examples
- Disable legacy protocols (FTP, Telnet)  
- Disable unused remote access services  
- Remove outdated software packages  

#### Commands (Linux)
- List services: `systemctl list-units --type=service`  
- Disable service: `systemctl disable service-name`  
- Stop service: `systemctl stop service-name`  

---

## 3. Additional Hardening Techniques

### **A. User & Permission Management**
- Enforce least privilege  
- Remove unnecessary accounts  
- Use strong authentication policies  
- Audit sudoers regularly
