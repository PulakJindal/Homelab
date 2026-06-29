# Networking Fundamentals

## What is an IP Address?

An IP address uniquely identifies a device on a network.

Examples:

* 192.168.x.x
* 10.x.x.x

These are private IP addresses.

---

## DHCP

DHCP automatically assigns IP addresses to devices joining a network.

Without DHCP, IP addresses must be configured manually.

---

## DNS

DNS translates domain names into IP addresses.

Example:

```
google.com
```

↓

```
142.x.x.x
```

---

## Netplan

Netplan is Ubuntu's network configuration system.

Configuration files are stored under:

```
/etc/netplan/
```

Changes are applied using:

```bash
sudo netplan apply
```

---

## Loopback Interface

```
lo
```

The loopback interface allows the system to communicate with itself.

---

## Ethernet vs Wi-Fi

Ethernet:

* Faster
* Lower latency
* More reliable

Wi-Fi:

* Convenient
* Portable
* Slightly higher latency

---

## Lessons Learned

* Ubuntu Server uses Netplan by default.
* YAML indentation is critical.
* DHCP simplifies network configuration.
* SSH requires working network connectivity.
