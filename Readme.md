# Linux Hardening using Ansible

## Overview
This project automates Linux server hardening using Ansible. It transforms a fresh Ubuntu server into a secure system by applying SSH restrictions, firewall rules, logging, and audit-based monitoring.

## Features

### SSH Hardening
- Disable root login  
- Disable password authentication  
- Limit login attempts  
- Restrict allowed users  

### Firewall (UFW + Fail2Ban)
- Default deny incoming traffic  
- Allow only required ports (SSH)  
- Brute-force protection via Fail2Ban  

### Logging
- rsyslog + journald persistence  
- Stores system logs in `/var/log/`  

### Audit System (auditd)
Monitors critical files:
- `/etc/passwd`
- `/etc/shadow`
- `/etc/sudoers`
- `/etc/group`
- `/var/log/auth.log`

## Usage

```bash
ansible-playbook -i inventory play.yml
```

## Verification

```bash
sudo ufw status
sudo fail2ban-client status sshd
sudo auditctl -l
```

## Goal

To demonstrate automated Linux security hardening using Ansible with a layered defense approach.
