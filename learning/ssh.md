# SSH Fundamentals

## What is SSH?

SSH (Secure Shell) is a protocol used to securely access remote systems over a network.

It encrypts all communication between the client and the server.

---

## Why SSH?

SSH allows a server to be administered remotely without requiring a monitor, keyboard, or mouse.

---

## Public Key Authentication

SSH uses asymmetric cryptography.

A key pair consists of:

* Private Key
* Public Key

The private key remains on the client.

The public key is copied to the server.

---

## SSH Authentication Flow

```
Fedora Laptop
│
├── Private Key
│
└──────────────► Ubuntu Server
                 │
                 └── Public Key
```

---

## known_hosts

Stores fingerprints of servers that have previously been trusted.

---

## authorized_keys

Stores public keys that are allowed to log in.

---

## SSH Socket Activation

Ubuntu can start the SSH service only when a connection is received.

This is known as socket activation.

---

## Lessons Learned

* SSH is the primary method of server administration.
* Public key authentication is more secure than passwords.
* The private key should never be shared.
* SSH allows headless server management.
