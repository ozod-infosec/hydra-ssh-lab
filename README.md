# hydra-ssh-lab
SSH Bruteforce Lab using Hydra 
This project demonstrates an ethical hacking lab where Kali Linux is used to perform an SSH password brutforce attack against an Ubuntu target machine.
This lab is created strictly for educational and cybersecurity training purposes.
---
## Lab Overview
The goal of this lab:
-Understand SSH authentication
-Practice bruteforce techniques using Hydra
-Learn offensive security in a controlled environment
-Establish a security Host-Only network betwen attacker and target machines
---
## Environment Setup 
###Attacker Machine (Kali Linux) 
-Hydra installed 
-Host-only network configured 
-Access to Ubuntu server via SSH 
### Target Machine (Ubuntu 22.04)
-A special training user created: **labuser**
-Intentionally weak password assigned for practice 
-SSH service enabled and reachable from Kali 
---
## Step-by-Step Process
### 1. Create training user on Ubuntu 
'''bash 
sudo adduser labuser
