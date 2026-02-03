# Lab #2: Network Configuration with Netplan

## Lab Overview

This lab focuses on **network interface configuration using Netplan**, the
default network configuration tool for modern Ubuntu systems. Proper network
configuration is foundational for system accessibility, security controls, and
cloud compatibility.

The objective is to inspect the default Netplan configuration, understand how
network interfaces are defined, validate connectivity, and safely apply changes
using Netplan commands.

---

## Objectives

- Identify active network interfaces
- Understand Netplan YAML configuration structure
- Verify DHCP-based network configuration
- Apply and validate Netplan changes safely
- Confirm network connectivity and DNS resolution

---

## Prerequisites

- Ubuntu installed on VirtualBox (Lab #1 completed)
- Console or SSH access to the VM
- Sudo-enabled user account

---

## Environment Details

- **OS:** Ubuntu Server / Desktop LTS
- **Virtualization:** VirtualBox
- **Networking Mode:** NAT
- **Network Tool:** Netplan
- **Renderer:** systemd-networkd

---

## Tools & Commands Used

- `ip`
- `netplan`
- `systemd-networkd`
- `nano`
- `ping`
- `resolvectl`

---

## Lab Steps

### Step 1: Identify Network Interfaces

List network interfaces:

```bash
ip a
# Lab #2: Network Configuration with Netplan

