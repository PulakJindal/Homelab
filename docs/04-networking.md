# Networking

**Difficulty:** ★★★☆☆

**Estimated Time:** 45–60 minutes

**Prerequisites**

* Ubuntu Server installed
* Wi-Fi adapter supported by Linux
* Internet connection
* Basic terminal knowledge

**Outcome**

* Connected Ubuntu Server to Wi-Fi
* Configured Netplan
* Verified internet connectivity
* Verified DNS resolution
* Enabled remote administration over SSH

---

# Overview

Networking is the foundation of every server.

Without network connectivity, remote administration, software installation, and self-hosted services are impossible.

Unlike Ubuntu Desktop, Ubuntu Server uses **Netplan** to manage network configuration. During this phase, the server was configured to connect to a wireless network and verified to have full internet access.

---

# Network Architecture

Current setup:

```text
                Internet
                     │
              Mobile Hotspot
                     │
         ┌───────────┴───────────┐
         │                       │
 Fedora Workstation      Ubuntu Server
        SSH  ─────────────────────►
```

Future setup:

```text
                  Internet
                       │
                 Home Router
                       │
          ┌────────────┴────────────┐
          │                         │
    Fedora Workstation        Ubuntu Server
                                   │
                             Docker Services
```

---

# Why Netplan?

Ubuntu Server does not install NetworkManager by default.

Instead, networking is configured through Netplan.

Advantages:

* Declarative configuration
* YAML-based
* Suitable for servers
* Easy to version-control
* Supports multiple network interfaces

---

# Network Interfaces

The system detected:

| Interface | Purpose            |
| --------- | ------------------ |
| lo        | Loopback           |
| eno1      | Ethernet           |
| wlp2s0    | Wireless Interface |

The wireless interface (`wlp2s0`) was used for the initial configuration.

---

# Wi-Fi Configuration

The wireless network was configured using Netplan.

Configuration file:

```text
/etc/netplan/00-installer-config.yaml
```

The server was configured with:

* DHCP enabled
* Wi-Fi SSID
* WPA2 password

After editing the configuration, the changes were applied using:

```bash
sudo netplan generate
sudo netplan apply
```

---

# Connectivity Verification

The following checks were performed.

## Verify IP Address

```bash
ip addr show wlp2s0
```

The server successfully received an IP address from the DHCP server.

---

## Verify Internet Connectivity

```bash
ping -c 4 8.8.8.8
```

Confirmed outbound internet access.

---

## Verify DNS Resolution

```bash
ping -c 4 google.com
```

Confirmed correct DNS configuration.

---

# SSH over LAN

Once networking was functional, the server became accessible remotely.

```bash
ssh arjun@<server-ip>
```

This removed the need for a dedicated monitor, keyboard, and mouse.

The server can now be administered remotely from the Fedora workstation.

---

# Future Networking Improvements

Planned improvements include:

* Configure home Wi-Fi
* Configure multiple known Wi-Fi networks
* Configure DHCP reservation
* Install Tailscale
* Remote access from anywhere
* Reverse proxy
* Internal Docker networking

---

# Lessons Learned

During this phase, several important networking concepts were introduced.

* Difference between public and private IP addresses
* DHCP
* DNS
* Netplan
* SSH over LAN
* Wi-Fi configuration on Ubuntu Server
* Remote administration

---

# Troubleshooting

## NetworkManager Not Installed

### Problem

Commands such as:

```bash
nmtui
```

were unavailable.

### Cause

Ubuntu Server does not install NetworkManager by default.

### Solution

Configured networking using Netplan.

---

## YAML Indentation Errors

### Problem

Netplan reported:

```text
inconsistent indentation
```

### Cause

Tabs were used instead of spaces.

### Solution

Replaced all tabs with spaces.

---

## Missing Colon

### Problem

Netplan reported an error on the password line.

### Cause

The SSID line was missing a trailing colon (`:`).

### Solution

Added the missing colon.

---

## Typographical Error

### Problem

The renderer value contained a spelling mistake.

### Cause

Incorrect value:

```text
netwrokd
```

### Solution

Corrected to:

```text
networkd
```

---

## Wi-Fi Did Not Connect

### Cause

The SSID or password did not exactly match the wireless network.

### Solution

Verified the SSID and password and reapplied the Netplan configuration.

---

# Summary

At the end of this chapter, the server was capable of:

* Connecting to Wi-Fi
* Receiving an IP address via DHCP
* Accessing the internet
* Resolving domain names
* Accepting SSH connections over the local network

The networking foundation is now complete and ready for server hardening and container deployment.

