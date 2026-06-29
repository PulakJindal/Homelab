# Ubuntu Server Installation

## Overview

This chapter documents the installation of Ubuntu Server on the Dell Latitude E5440. The objective was to prepare a lightweight, reliable operating system that would serve as the foundation for the homelab.

Unlike Ubuntu Desktop, Ubuntu Server provides a minimal environment without a graphical interface. This reduces resource usage while encouraging administration through the command line and SSH.

---

# Why Ubuntu Server?

Several Linux distributions were considered before choosing Ubuntu Server.

Reasons for choosing Ubuntu Server:

* Long-Term Support (LTS) releases
* Excellent community support
* Large software repository
* Official support for Docker
* Stable release cycle
* Widely used in production environments
* Lightweight compared to desktop distributions

---

# Installation Media

## Requirements

* Ubuntu Server ISO
* USB flash drive (8 GB or larger)
* Fedora workstation for creating installation media

The installation USB was created using **Fedora Media Writer**.

---

# BIOS Configuration

The Dell Latitude E5440 required several BIOS changes before installation.

## BIOS Settings

| Setting       | Value       |
| ------------- | ----------- |
| Boot Mode     | UEFI        |
| Secure Boot   | Disabled    |
| Boot Priority | USB Storage |

During installation the system clock had reset due to the CMOS battery, requiring the date and time to be configured manually in the BIOS.

---

# Ubuntu Installation

The following options were selected during installation.

| Setting             | Selection             |
| ------------------- | --------------------- |
| Installation Type   | Ubuntu Server         |
| Network             | Wi-Fi                 |
| Proxy               | None                  |
| Mirror              | Default Ubuntu Mirror |
| Storage             | Use Entire Disk       |
| OpenSSH Server      | Installed             |
| Additional Packages | None                  |

The OpenSSH Server package was selected during installation to enable remote administration immediately after installation.

---

# First Boot

After installation the system successfully booted into Ubuntu Server.

Unlike Ubuntu Desktop, Ubuntu Server does not provide a graphical desktop environment.

Instead, the administrator is presented with a Linux terminal where all management tasks are performed.

This is expected behavior and one of the primary reasons Ubuntu Server uses significantly fewer system resources.

---

# Lessons Learned

During installation several important concepts became clear.

* Ubuntu Server is designed to be administered through the terminal.
* Installing OpenSSH during setup simplifies remote administration.
* UEFI boot mode should be used consistently throughout installation.
* The system can operate without a graphical interface, reducing resource consumption.

---

# Troubleshooting

## Invalid Partition Table

### Problem

After completing the installation and rebooting, the system displayed:

```text
Invalid partition table
```

### Cause

Ubuntu was installed using UEFI, but the BIOS attempted to boot in Legacy mode.

### Solution

Changed the BIOS Boot Mode from **Legacy** to **UEFI**.

---

## Incorrect System Date and Time

### Problem

On startup, the BIOS displayed:

```text
Invalid configuration info - please run setup program
Time-of-day not set
```

### Cause

The system clock had reset.

### Solution

Entered the BIOS setup (F2) and manually configured the correct date and time.

---

## No Graphical User Interface

### Problem

After logging in, only a terminal was available.

### Cause

Ubuntu Server does not install a desktop environment.

### Solution

No action required. This is the intended behavior. The server will be administered using the terminal and SSH.

---

# Summary

At the end of this chapter, the server had:

* Ubuntu Server successfully installed
* UEFI boot configured
* OpenSSH installed
* Terminal-based administration available
* Foundation ready for network configuration and security hardening

The next chapter covers networking, including Wi-Fi configuration using Netplan, internet connectivity, and remote SSH access.
