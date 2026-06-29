# Security

**Difficulty:** ★★☆☆☆

**Estimated Time:** 30–45 minutes

**Prerequisites**

* Ubuntu Server installed
* Network connectivity
* SSH access

**Outcome**

* SSH key authentication configured
* UFW firewall enabled
* Automatic security updates enabled
* Server hardened for remote administration

---

# Overview

Security should be considered from the beginning of a server deployment rather than added later.

Before installing Docker or exposing any services to the network, the server was configured with basic security controls to reduce its attack surface.

The initial security measures focused on:

* Secure remote access
* Firewall protection
* Automatic security updates

These provide a solid foundation for future services.

---

# Security Architecture

```text id="gbk6tt"
                Internet / Local Network
                         │
                  Ubuntu Firewall (UFW)
                         │
                 OpenSSH (Port 22)
                         │
                 SSH Key Authentication
                         │
                  Ubuntu Server
```

---

# SSH Authentication

OpenSSH was installed during the Ubuntu installation process.

Instead of relying solely on passwords, SSH key authentication was configured.

Advantages include:

* Stronger authentication
* Protection against brute-force attacks
* More convenient administration
* Standard practice for Linux servers

---

# SSH Key Generation

An Ed25519 key pair was generated on the Fedora workstation.

The public key was copied to the Ubuntu Server.

This enables passwordless authentication while keeping the private key on the client machine.

---

# SSH Key Authentication Workflow

```text id="xtlcml"
Fedora Workstation
│
├── Private Key
│
└──────────────► Ubuntu Server
                 │
                 └── Authorized Public Key
```

Only the public key is stored on the server.

The private key never leaves the client.

---

# Firewall Configuration

Ubuntu provides the **Uncomplicated Firewall (UFW)** as a front-end for iptables/nftables.

Before enabling the firewall, SSH traffic was explicitly allowed.

```bash id="oowiqg"
sudo ufw allow OpenSSH
```

The firewall was then enabled.

```bash id="fbcjlwm"
sudo ufw enable
```

Current firewall policy:

* Allow SSH
* Block unsolicited incoming connections

---

# Automatic Security Updates

The package **unattended-upgrades** was verified to be installed and enabled.

Configuration confirmed:

* Daily package list updates
* Automatic installation of security updates

This reduces the risk of known vulnerabilities remaining unpatched.

---

# Security Principles

The server follows several security principles.

## Principle of Least Privilege

Only required services should be accessible.

---

## Defense in Depth

Security should not rely on a single mechanism.

Current layers include:

* SSH Keys
* Firewall
* Automatic Updates

Additional layers such as Tailscale and Fail2Ban will be added later.

---

## Secure by Default

Services should remain inaccessible unless intentionally exposed.

---

# Future Security Improvements

Planned enhancements include:

* Disable SSH password authentication
* Install Fail2Ban
* Configure Tailscale
* Reverse proxy with HTTPS
* Automatic backups
* Log monitoring

---

# Lessons Learned

This chapter introduced several important concepts.

* Public/private key authentication
* SSH agents
* Authorized keys
* Firewalls
* Automatic patch management
* Layered security

---

# Troubleshooting

## SSH Service Appeared Inactive

### Problem

The SSH service appeared inactive when checking:

```bash id="aoccbj"
sudo systemctl status ssh
```

### Cause

Ubuntu uses **socket activation**.

The SSH daemon starts automatically when a connection is received.

### Solution

Verified that:

```bash id="jlwm4h"
sudo systemctl status ssh.socket
```

was active and listening.

---

## Firewall Could Lock Out SSH

### Problem

Enabling the firewall before allowing SSH would block remote administration.

### Solution

Allowed OpenSSH before enabling UFW.

```bash id="d1h4np"
sudo ufw allow OpenSSH
sudo ufw enable
```

---

## Automatic Updates Verification

Rather than assuming automatic updates were configured, the configuration files were inspected.

Verified:

* `50unattended-upgrades`
* `20auto-upgrades`

This confirmed that security updates would be installed automatically.

---

# Summary

At the end of this chapter, the server was configured with:

* SSH key authentication
* UFW firewall
* Automatic security updates
* Secure remote administration

These controls provide a secure foundation for installing Docker and hosting network-accessible services.
