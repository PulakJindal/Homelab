# Ubuntu Installation Troubleshooting

This document records issues encountered during the Ubuntu Server installation process and their solutions.

---

## Invalid Configuration Information

### Problem

During startup, the BIOS displayed:

```text
Invalid configuration info - please run setup program
Time-of-day not set - please run setup program
```

### Cause

The CMOS battery had reset the BIOS configuration, causing the system date and time to become invalid.

### Solution

1. Enter the BIOS setup using **F2**.
2. Set the correct date and time.
3. Save and reboot.

---

## Invalid Partition Table

### Problem

After installing Ubuntu, the system displayed:

```text
Invalid partition table
```

### Cause

Ubuntu was installed in **UEFI mode**, but the BIOS attempted to boot in **Legacy mode**.

### Solution

1. Enter BIOS Setup.
2. Change Boot Mode to **UEFI**.
3. Save and reboot.

---

## No Graphical Interface

### Problem

After installation, Ubuntu booted into a text-based terminal instead of a desktop.

### Cause

Ubuntu Server does not install a graphical desktop environment.

### Solution

No action required.

Ubuntu Server is designed for command-line administration and remote management via SSH.
