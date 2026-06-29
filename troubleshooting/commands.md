# Server Commands Cheat Sheet

This document contains frequently used commands for administering and troubleshooting the homelab.

---

# System Information

## Hostname

```bash
hostnamectl
```

Displays hostname, operating system, kernel version, architecture, and hardware information.

---

## Current User

```bash
whoami
```

Displays the currently logged-in user.

---

## Current Directory

```bash
pwd
```

Displays the current working directory.

---

## Current Time

```bash
timedatectl
```

Displays the current time, timezone, and NTP status.

---

# System Management

## Update Package List

```bash
sudo apt update
```

---

## Upgrade Installed Packages

```bash
sudo apt upgrade
```

---

## Shutdown Server

```bash
sudo shutdown now
```

---

## Reboot Server

```bash
sudo reboot
```

---

# Network

## Display Network Interfaces

```bash
ip addr
```

---

## Display Wireless Interface

```bash
ip addr show wlp2s0
```

---

## Verify Internet Connectivity

```bash
ping 8.8.8.8
```

---

## Verify DNS Resolution

```bash
ping google.com
```

---

## Display Routing Table

```bash
ip route
```

---

# Netplan

## Apply Configuration

```bash
sudo netplan apply
```

---

## Validate Configuration

```bash
sudo netplan generate
```

---

## Edit Configuration

```bash
sudo nano /etc/netplan/00-installer-config.yaml
```

---

# SSH

## Connect to Server

```bash
ssh arjun@SERVER_IP
```

---

## Display SSH Status

```bash
sudo systemctl status ssh
```

---

## Display SSH Socket Status

```bash
sudo systemctl status ssh.socket
```

---

## Copy Public Key

```bash
ssh-copy-id arjun@SERVER_IP
```

---

# Firewall

## Display Firewall Status

```bash
sudo ufw status verbose
```

---

## Display Numbered Rules

```bash
sudo ufw status numbered
```

---

## Allow SSH

```bash
sudo ufw allow OpenSSH
```

---

## Enable Firewall

```bash
sudo ufw enable
```

---

# Docker

*(Commands will be added as Docker is configured.)*

---

# Logs

## View Journal

```bash
journalctl
```

---

## View Boot Logs

```bash
journalctl -b
```

---

## Follow Live Logs

```bash
journalctl -f
```

---

# Useful Directories

| Directory      | Purpose               |
| -------------- | --------------------- |
| `/etc`         | System configuration  |
| `/home`        | User home directories |
| `/var/log`     | Log files             |
| `/etc/netplan` | Netplan configuration |
| `/etc/ssh`     | SSH configuration     |

---

# First Response Checklist

When something is not working, check the following:

### Is the server reachable?

```bash
ping SERVER_IP
```

---

### Is networking working?

```bash
ip addr
```

---

### Can the server reach the Internet?

```bash
ping 8.8.8.8
```

---

### Is DNS working?

```bash
ping google.com
```

---

### Is SSH running?

```bash
sudo systemctl status ssh.socket
```

---

### Is the firewall active?

```bash
sudo ufw status
```

---

### Has the server received an IP address?

```bash
ip addr show wlp2s0
```

---

# Notes

This file is intended to be a quick reference during day-to-day administration.

As new technologies are introduced (Docker, Tailscale, monitoring, backups, etc.), their most frequently used commands will be added here.
