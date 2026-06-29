# Glossary

This glossary contains important terms encountered while building the homelab.

The goal is to provide concise definitions that can be quickly referenced without reading the full documentation.

---

| Term                             | Definition                                                                                                                                                |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **APT**                          | Ubuntu's package manager used to install, update, and remove software packages.                                                                           |
| **Boot Mode**                    | The method used by the firmware to start the operating system. Modern systems typically use UEFI, while older systems may use Legacy BIOS.                |
| **CMOS Battery**                 | A small battery on the motherboard that maintains BIOS settings such as date and time when the computer is powered off.                                   |
| **Daemon**                       | A background process that runs without direct user interaction and provides system services (e.g., Docker daemon, SSH daemon).                            |
| **DHCP**                         | Dynamic Host Configuration Protocol. Automatically assigns IP addresses and network settings to devices on a network.                                     |
| **DNS**                          | Domain Name System. Translates human-readable domain names (e.g., `google.com`) into IP addresses.                                                        |
| **Docker**                       | A containerization platform used to package and run applications in isolated environments. *(Covered in detail later.)*                                   |
| **Firewall**                     | Software or hardware that controls incoming and outgoing network traffic based on predefined rules.                                                       |
| **GUI**                          | Graphical User Interface. Ubuntu Server does not include one by default, making it lightweight and suitable for servers.                                  |
| **Headless Server**              | A server that operates without a monitor, keyboard, or mouse. It is typically managed remotely through SSH.                                               |
| **Hostname**                     | A human-readable name assigned to a device on a network.                                                                                                  |
| **IP Address**                   | A numerical identifier assigned to a device so it can communicate on a network.                                                                           |
| **Loopback Interface (`lo`)**    | A virtual network interface that allows a system to communicate with itself.                                                                              |
| **MAC Address**                  | A unique hardware identifier assigned to a network interface card (NIC).                                                                                  |
| **Netplan**                      | Ubuntu's network configuration utility that uses YAML configuration files to define network interfaces and settings.                                      |
| **OpenSSH**                      | The open-source implementation of the SSH protocol used for secure remote access.                                                                         |
| **Package Repository**           | A trusted source from which software packages are downloaded and installed.                                                                               |
| **Private IP Address**           | An IP address used within local networks (e.g., `192.168.x.x`, `10.x.x.x`) that is not directly accessible from the internet.                             |
| **Public Key**                   | The shareable part of an SSH key pair stored on the server to authenticate clients.                                                                       |
| **Private Key**                  | The secret part of an SSH key pair that must remain on the client machine. It proves the client's identity.                                               |
| **Renderer**                     | The backend service used by Netplan to apply network configurations (e.g., `networkd`, `NetworkManager`).                                                 |
| **Repository**                   | A storage location containing software packages or version-controlled project files (e.g., Git repository).                                               |
| **SSH (Secure Shell)**           | A secure protocol used for encrypted remote access and administration of systems over a network.                                                          |
| **SSH Key Pair**                 | A pair of cryptographic keys (public and private) used for secure SSH authentication.                                                                     |
| **SSH Socket Activation**        | A systemd feature where the SSH service starts automatically when an incoming connection is received.                                                     |
| **SSID**                         | Service Set Identifier. The name of a Wi-Fi network visible to users.                                                                                     |
| **systemd**                      | The initialization and service management system used by modern Linux distributions.                                                                      |
| **UEFI**                         | Unified Extensible Firmware Interface. Modern firmware that replaces the traditional BIOS and supports features such as GPT partitioning and Secure Boot. |
| **UFW (Uncomplicated Firewall)** | Ubuntu's user-friendly interface for configuring the Linux firewall.                                                                                      |
| **Unattended Upgrades**          | A service that automatically installs security updates without requiring manual intervention.                                                             |
| **YAML**                         | A human-readable data serialization format commonly used for configuration files. YAML relies on spaces for indentation and is sensitive to formatting.   |

---
