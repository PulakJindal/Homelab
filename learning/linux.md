# Linux Fundamentals

## What is Linux?

Linux is an open-source operating system kernel that forms the foundation of many operating systems, including Ubuntu, Fedora, Debian, Arch Linux, and others.

A Linux distribution combines the Linux kernel with system utilities, package managers, libraries, and applications.

---

## Ubuntu Server vs Ubuntu Desktop

Ubuntu Server does not include a graphical desktop environment by default.

Advantages:

* Lower memory usage
* Lower CPU usage
* Faster boot time
* Better suited for servers
* Managed remotely using SSH

---

## The Linux Filesystem

Linux uses a hierarchical filesystem beginning at the root directory.

Important directories:

| Directory | Purpose                    |
| --------- | -------------------------- |
| /         | Root directory             |
| /home     | User home directories      |
| /etc      | System configuration       |
| /var      | Variable data such as logs |
| /usr      | Installed applications     |
| /tmp      | Temporary files            |

---

## System Services

Ubuntu uses **systemd** to manage services.

Examples:

* SSH
* Docker
* Networking

Useful commands:

```bash
systemctl status
systemctl start
systemctl stop
systemctl restart
```

---

## Package Management

Ubuntu uses **APT**.

Common commands:

```bash
sudo apt update
sudo apt upgrade
sudo apt install
sudo apt remove
```

---

## Lessons Learned

* Servers do not require a GUI.
* Most administration is performed through the terminal.
* Services are managed using systemd.
* Configuration files are typically stored under `/etc`.
