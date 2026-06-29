# Hardware

## Overview

The homelab is built using repurposed consumer hardware instead of dedicated enterprise equipment.

The objective is to demonstrate that a reliable and capable home server can be created using an old laptop while keeping costs close to zero.

Using a laptop also provides several advantages over a desktop computer:

* Built-in UPS (battery backup)
* Lower power consumption
* Integrated display and keyboard for troubleshooting
* Compact form factor
* Quiet operation

---

# Hardware Specifications

| Component   | Specification               |
| ----------- | --------------------------- |
| Model       | Dell Latitude E5440         |
| Device Type | Laptop                      |
| CPU         | Intel Core i5               |
| RAM         | 8 GB DDR3                   |
| Storage     | 500 GB HDD                  |
| Network     | Intel Wireless 7260         |
| Ethernet    | Integrated Gigabit Ethernet |
| Boot Mode   | UEFI                        |

> **Note:** This document should be updated whenever hardware is upgraded (RAM, SSD, Wi-Fi card, etc.).

---

# Why This Hardware?

Rather than purchasing a dedicated server, an unused laptop provides an excellent platform for learning.

Advantages include:

* Already available
* No additional hardware cost
* Low electricity consumption
* Battery protects against short power failures
* Portable during initial configuration

This makes it ideal for building a personal homelab.

---

# Expected Workloads

The hardware is expected to comfortably support:

* SSH Remote Administration
* Docker Engine
* Docker Compose
* Tailscale
* Homepage Dashboard
* Jellyfin (Direct Play)
* Immich
* Nextcloud
* AdGuard Home
* Nginx Proxy Manager

Because the system has limited memory, services should be deployed efficiently using Docker containers rather than virtual machines.

---

# Storage Strategy

Current configuration:

* Operating System
* Docker Engine
* Docker Images
* Docker Volumes
* Self-hosted Services

Future improvements:

* Replace HDD with SSD
* Add external USB storage for media and backups
* Separate application data from backup storage

---

# Network Connectivity

Current configuration:

* Wireless connection using Intel Wireless 7260
* Temporary mobile hotspot during initial setup

Planned configuration:

* Primary Network: Home Wi-Fi
* Secondary Network: Mobile Hotspot
* Remote Access: Tailscale VPN

---

# Power Considerations

The laptop's internal battery provides a small amount of backup power.

Benefits include:

* Protection against brief power outages
* Graceful shutdown during extended outages
* Reduced risk of filesystem corruption

Future improvement:

* Dedicated UPS for longer runtime.

---

# Hardware Limitations

Current limitations include:

* Limited RAM compared to enterprise servers
* Mechanical HDD results in slower disk performance
* No hardware RAID
* Limited CPU resources for heavy workloads

These constraints encourage efficient resource management and lightweight deployments.

---

# Future Upgrade Plan

Potential hardware upgrades include:

* SSD upgrade
* RAM upgrade (if supported)
* External backup drive
* Gigabit Ethernet as the primary network connection
* Dedicated UPS

The server is intentionally designed so that these upgrades can be performed without changing the overall software architecture.

---

# Lessons Learned

A dedicated server is not required to learn Linux administration, Docker, networking, and self-hosting.

Older consumer hardware is more than capable of supporting a modern homelab while providing an excellent platform for practical learning.
