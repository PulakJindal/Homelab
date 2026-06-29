# Networking Troubleshooting

This document records networking issues encountered during the initial server setup.

---

## `nmtui` Command Not Found

### Problem

Running:

```bash
nmtui
```

returned:

```text
command not found
```

### Cause

Ubuntu Server does not install NetworkManager by default.

### Solution

Configure networking using Netplan.

---

## NetworkManager Not Installed

### Problem

Attempting to use NetworkManager failed.

### Cause

Ubuntu Server uses **Netplan** with the **networkd** renderer.

### Solution

Edit:

```text
/etc/netplan/00-installer-config.yaml
```

Apply changes:

```bash
sudo netplan generate
sudo netplan apply
```

---

## Inconsistent Indentation

### Problem

Netplan returned:

```text
inconsistent indentation
```

### Cause

Tabs were used instead of spaces.

### Solution

Replace all tabs with spaces.

YAML is indentation-sensitive.

---

## Error Reported on Password Line

### Problem

The parser reported an error on the Wi-Fi password line.

### Cause

The actual issue was a missing colon (`:`) after the SSID line.

### Solution

Correct the YAML syntax.

---

## Wi-Fi Does Not Connect

### Cause

Possible causes include:

* Incorrect SSID
* Incorrect password
* YAML formatting errors

### Solution

1. Verify the SSID.
2. Verify the password.
3. Validate the YAML file.
4. Run:

```bash
sudo netplan generate
sudo netplan apply
```

---

## Verify Connectivity

Useful commands:

```bash
ip addr show wlp2s0
ping 8.8.8.8
ping google.com
```

