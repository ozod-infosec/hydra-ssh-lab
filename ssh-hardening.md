# SSH Hardening Lab (Defensive Security)

## Overview
This lab demonstrates how SSH brute-force attacks work
and how to prevent them using proper SSH hardening.

All actions were performed in a controlled lab environment
using VirtualBox (Kali Linux attacker → Ubuntu target).

---

## Initial State (Vulnerable)
- Password authentication enabled
- Root login allowed
- Weak user credentials
- Successful Hydra SSH brute-force

---

## Hardening Steps

### Disable Password Authentication
```bash
sudo nano /etc/ssh/sshd_config
Change: PasswordAuthentication yes
to: PasswordAuthentication no
Disable Root Login
PermitRootLogin yes
to: PermitRootLogin no
Restart SSH Service
sudo systemctl restart ssh
sudo systemctl status ssh
##Verification
From Kali Linux:
ssh practice1@UBUNTU_IP
Expected result:
Password login rejected
Brute-force attacks no longer possible
##Security Impact
SSH brrute force attackes blocked
Root account protected
System aligned with professional hardening standarsts
##Skill gained
SSH attack understanding
SSH server hardening
Offensive-Defensive security transition
Blue Team/SOC-level practice 
