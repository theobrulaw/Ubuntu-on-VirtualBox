# Ubuntu Installation on VirtualBox

## Objective
Install Ubuntu Linux on Oracle VirtualBox and configure a stable base system
suitable for learning Linux administration, cloud operations, and DevOps
fundamentals. This lab establishes the foundation for all subsequent Linux,
cloud, and security exercises.

---

## Architecture / Environment Overview

- Host OS: Windows or macOS
- Hypervisor: Oracle VirtualBox
- Guest OS: Ubuntu Server LTS
- VM Type: Single virtual machine
- Networking Mode: NAT
- Purpose: Local, isolated lab environment

This setup mirrors how Linux systems are commonly provisioned as virtual
machines in cloud and enterprise environments.

---

## Prerequisites

- Oracle VirtualBox installed
- Ubuntu Server LTS ISO downloaded
- At least:
  - 4 GB RAM available on host
  - 2 CPU cores
  - 25 GB free disk space
- Basic familiarity with command-line navigation (helpful but not required)

---

## Steps Performed

### 1. Create a New Virtual Machine
- Open VirtualBox and select **New**
- Name the VM (e.g., `Ubuntu-Lab`)
- Type: Linux
- Version: Ubuntu (64-bit)
- Allocate:
  - Memory: 2048–4096 MB
  - CPUs: 2

---

### 2. Configure Virtual Disk
- Disk type: VDI
- Allocation: Dynamically allocated
- Size: 25 GB

---

### 3. Attach Ubuntu ISO
- Select the VM → **Settings**
- Go to **Storage**
- Attach the Ubuntu Server ISO to the optical drive

---

### 4. Install Ubuntu
- Start the VM
- Select language and keyboard layout
- Configure networking (default DHCP via NAT)
- Skip proxy unless required
- Use default mirror settings
- Partition disk using guided setup
- Create:
  - Username
  - Strong password
- Select OpenSSH server during installation
- Complete installation and reboot
- Remove ISO when prompted

---

### 5. Log In and Update System
After reboot, log in and run:

```bash
sudo apt update && sudo apt upgrade -y
# Lab Title

## Objective
Briefly describe what this lab demonstrates and why it matters in a real-world
cloud, DevOps, or security context.

## Architecture / Environment Overview
Describe the environment, services, VMs, networking mode, or cloud components
used in this lab.

## Prerequisites
- Tools required
- Accounts or access needed
- Prior knowledge assumed

## Steps Performed
1. Step-by-step actions taken
2. Commands executed or configurations applied
3. Key decisions or trade-offs made

## Validation & Verification
Describe how you confirmed the lab worked:
- Commands
- Logs
- Screenshots
- Outputs

## Security & Operational Considerations
- Security risks addressed
- Hardening steps applied
- Operational trade-offs

## Lessons Learned
What worked well, what broke, and what you would do differently next time.
