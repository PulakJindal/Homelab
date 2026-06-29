# Homelab

> A self-hosted homelab built on an old Dell Latitude E5440 to learn Linux system administration, networking, Docker, DevOps, self-hosting, and cybersecurity through hands-on projects.

---

## Overview

This repository documents the complete journey of transforming an old laptop into a production-style home server.

Instead of simply installing software, this project focuses on understanding **how** and **why** each component works. Every service, configuration, and architectural decision is documented so that the entire server can be rebuilt from scratch.

The homelab serves two purposes:

* A practical learning environment for Linux, networking, Docker, and infrastructure.
* A collection of useful self-hosted services accessible from anywhere.

---

# Goals

* Learn Linux system administration
* Learn networking through real deployments
* Build and manage Docker containers
* Self-host useful services
* Understand security best practices
* Document everything for reproducibility
* Create a long-term engineering project

---

# Hardware

| Component | Details                   |
| --------- | ------------------------- |
| Machine   | Dell Latitude E5440       |
| RAM       | 4 GB                      |
| Storage   | 256 GB HDD                |
| Network   | Intel Wireless 7260 Wi-Fi |
| Purpose   | Dedicated Home Server     |

---

# Operating System

* Ubuntu Server 26.04 LTS
* UEFI Boot Mode

---

# Planned Architecture

```text
                    Internet
                         │
                  Tailscale VPN
                         │
                Ubuntu Server 26.04
                         │
                  Docker Engine
                         │
     ┌──────────┬──────────┬──────────┬──────────┐
     │          │          │          │
 Homepage   Jellyfin    Immich   Nextcloud
     │
     ├── AdGuard Home
     ├── Nginx Proxy Manager
     ├── Monitoring
     └── Future Services
```

---

# Technologies

## Operating System

* Ubuntu Server
* Linux
* systemd
* Netplan

## Networking

* SSH
* UFW Firewall
* Wi-Fi
* Tailscale (Planned)

## Containerization

* Docker
* Docker Compose

## Self-hosted Services (Planned)

* Homepage Dashboard
* Jellyfin
* Immich
* Nextcloud
* AdGuard Home
* Nginx Proxy Manager
* WireGuard
* Grafana
* Prometheus

---

# Repository Structure

```text
homelab/
│
├── README.md
├── docs/
├── docker/
├── configs/
├── diagrams/
├── images/
├── learning/
├── scripts/
└── troubleshooting/
```

---

# 📈 Progress

## Phase 1 — Server Foundation

* [x] Install Ubuntu Server
* [x] Configure UEFI Boot
* [x] Configure Wi-Fi with Netplan
* [x] Update System Packages
* [x] Configure SSH
* [x] Configure SSH Key Authentication
* [x] Configure UFW Firewall
* [x] Enable Automatic Security Updates
* [x] Install Docker Repository
* [x] Install Docker Engine

## Phase 2 — Container Platform

* [ ] Verify Docker Installation
* [ ] Run First Container
* [ ] Learn Docker Fundamentals
* [ ] Learn Docker Compose
* [ ] Configure Docker Networks
* [ ] Configure Docker Volumes

## Phase 3 — Networking

* [ ] Configure Home Wi-Fi
* [ ] Configure Static IP
* [ ] Install Tailscale
* [ ] Remote Access

## Phase 4 — Services

* [ ] Homepage Dashboard
* [ ] Jellyfin
* [ ] Immich
* [ ] Nextcloud
* [ ] AdGuard Home
* [ ] Nginx Proxy Manager

## Phase 5 — Infrastructure

* [ ] Monitoring
* [ ] Logging
* [ ] Backups
* [ ] Disaster Recovery

---

# Learning Objectives

This project is intended to provide practical experience in:

* Linux Administration
* Networking
* Docker
* Container Orchestration
* Infrastructure Management
* Server Security
* Self-hosting
* DevOps Fundamentals
* System Monitoring
* Backup and Recovery

---

# Documentation

Each major milestone is documented under the `docs/` directory.

The documentation includes:

* Why the technology is used
* Installation steps
* Configuration
* Troubleshooting
* Lessons learned

The goal is to make this repository completely reproducible.

---

# Current Status

🟢 Foundation complete.

The server is running Ubuntu Server with:

* Wi-Fi connectivity
* SSH access
* SSH key authentication
* Firewall protection
* Automatic security updates
* Docker installed

The next milestone is building the container platform and deploying the first self-hosted service.

---

## ⭐ Project Philosophy

This repository is not just about building a home server.

It is an engineering notebook documenting the process of learning Linux, networking, Docker, DevOps, and self-hosting through real-world implementation.

Every configuration, command, mistake, and solution is documented so the knowledge gained is as valuable as the finished server.
