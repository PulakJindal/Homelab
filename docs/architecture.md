# Architecture

## Overview

This document describes the architecture of the homelab.

The architecture is intentionally designed to evolve over time. Each major milestone (Docker, Tailscale, self-hosted services, monitoring, backups, etc.) will update this document to reflect the current state of the system.

---

# Current Architecture

At the current stage of the project, the server consists of a minimal Ubuntu Server installation configured for secure remote administration.

```text
                           Internet
                               │
                        Mobile Hotspot
                               │
                ┌──────────────┴──────────────┐
                │                             │
        Fedora Workstation            Ubuntu Server
                │                             │
                └──────── SSH ───────────────►│
                                              │
                                    ┌─────────────────────┐
                                    │ Ubuntu Server 26.04 │
                                    │                     │
                                    │ • Netplan           │
                                    │ • OpenSSH           │
                                    │ • UFW Firewall      │
                                    │ • Auto Updates      │
                                    │ • Docker Installed  │
                                    └─────────────────────┘
```

---

# Current Software Stack

```text
Hardware
│
└── Dell Latitude E5440
     │
     ▼
Ubuntu Server 26.04 LTS
     │
     ├── Netplan
     ├── OpenSSH
     ├── UFW
     ├── Unattended Upgrades
     └── Docker Engine
```

---

# Current Network Topology

```text
                Internet
                     │
              Mobile Hotspot
                     │
          ┌──────────┴──────────┐
          │                     │
 Fedora Workstation      Ubuntu Server
          │
          └──────── SSH ───────►
```

The server is currently administered remotely over SSH from the Fedora workstation.

---

# Planned Architecture

The long-term goal is to transform the server into a complete self-hosted platform.

```text
                           Internet
                                │
                           Tailscale VPN
                                │
                        Ubuntu Server 26.04
                                │
                          Docker Engine
                                │
      ┌─────────────┬──────────────┬──────────────┬─────────────┐
      │             │              │              │
   Homepage      Jellyfin      Immich       Nextcloud
      │
      ├── AdGuard Home
      ├── Nginx Proxy Manager
      ├── Monitoring
      └── Additional Services
```

---

# Design Principles

The architecture follows several principles.

* Minimal host operating system.
* Containerized applications.
* Secure remote administration.
* Layered security.
* Reproducible deployments.
* Comprehensive documentation.

---

# Future Enhancements

Planned improvements include:

* Docker Compose
* Tailscale VPN
* Static IP / DHCP Reservation
* Reverse Proxy
* HTTPS
* Monitoring
* Backup Strategy
* Automated Deployments
* Additional self-hosted services

---

# Architecture Evolution

This document will be updated after each major milestone.

Future versions will include:

* Docker networking
* Container communication
* Storage layout
* Reverse proxy architecture
* VPN topology
* Backup architecture
* Monitoring architecture

```
```
