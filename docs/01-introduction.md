# Introduction

## Project Overview

This project documents the process of transforming an old laptop into a fully functional self-hosted home server.

Rather than simply installing software, the objective is to understand every layer of the system—from the operating system and networking to containerization, security, monitoring, and automation.

Every decision, configuration, and troubleshooting step is documented so that the entire environment can be recreated from scratch.

---

# Why This Project?

Modern software development extends beyond writing code. Backend engineers, DevOps engineers, Site Reliability Engineers (SREs), and cybersecurity professionals are expected to understand Linux systems, networking, containerization, deployment, and infrastructure.

Instead of learning these topics independently, this project combines them into a single practical environment.

By the end of this project, the homelab will function as a personal cloud platform capable of hosting multiple production-like services.

---

# Objectives

The primary objectives of this project are:

* Learn Linux system administration
* Understand computer networking through practical implementation
* Learn Docker and containerized applications
* Deploy multiple self-hosted services
* Secure the server using modern best practices
* Build experience with infrastructure automation
* Create comprehensive technical documentation
* Develop a reproducible deployment process

---

# What Will Be Built?

The final homelab is expected to include the following components:

## Operating System

* Ubuntu Server

## Infrastructure

* SSH
* UFW Firewall
* Docker
* Docker Compose
* Tailscale VPN

## Self-hosted Applications

* Homepage Dashboard
* Jellyfin
* Immich
* Nextcloud
* AdGuard Home
* Nginx Proxy Manager

## Monitoring

* Grafana
* Prometheus

## Storage

* Shared file storage
* Backup system
* Docker volumes

---

# Learning Philosophy

This repository is designed as both a deployment guide and a learning resource.

Each chapter documents:

* The purpose of the technology
* Installation steps
* Configuration
* Troubleshooting
* Lessons learned

Instead of focusing only on *what* commands were executed, the documentation explains *why* those commands are required and *how* each component works internally.

---

# Target Audience

This documentation is intended for:

* Students learning Linux
* Developers interested in self-hosting
* Beginners exploring Docker
* Anyone building a personal home server
* Future contributors to this project

No prior experience with Linux or server administration is assumed.

---

# Repository Organization

The repository is divided into multiple sections.

* **docs/** – Complete documentation for every phase of the project.
* **configs/** – Configuration files used by the server.
* **docker/** – Docker Compose files and service configurations.
* **learning/** – Conceptual notes about Linux, networking, Docker, and related technologies.
* **scripts/** – Utility scripts developed during the project.
* **troubleshooting/** – Common issues encountered and their solutions.

---

# Project Principles

This project follows several guiding principles:

1. Understand before implementing.
2. Document every important decision.
3. Use open-source technologies whenever possible.
4. Prefer reproducible configurations over manual changes.
5. Build incrementally, validating each step before proceeding.
6. Treat the homelab as a long-term engineering project rather than a one-time setup.

---

# Project Roadmap

The project is divided into the following phases:

1. Server Foundation
2. Networking
3. Security
4. Docker
5. Container Management
6. Remote Access
7. Self-hosted Services
8. Monitoring
9. Backup and Recovery
10. Continuous Improvements

Each phase builds upon the previous one, resulting in a maintainable and extensible home server.
