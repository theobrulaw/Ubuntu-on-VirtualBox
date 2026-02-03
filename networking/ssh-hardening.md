# Lab #4: SSH Configuration & Hardening

## Lab Overview

This lab focuses on **securing Secure Shell (SSH) access** to an Ubuntu system.
SSH is one of the most commonly targeted services on Linux servers and cloud
instances. Hardening SSH is a critical control for reducing unauthorized access
and meeting baseline security compliance requirements.

The objective is to configure SSH for **key-based authentication**, restrict
access to approved users, disable insecure defaults, and validate secure remote
administration.

---

## Objectives

- Enable and verify SSH service operation
- Configure SSH key-based authentication
- Disable password-based authentication
- Restrict SSH access to approved users
- Disable direct root SSH login
- Validate hardened SSH configuration

---

## Prerequisites

- Ubuntu VM with user & sudo configuration completed (Lab #2)
- At least one non-root sudo-enabled user
- Terminal access to the system
- Snapshot taken prior to configuration changes (recommended)

---

## Environment Details

- **OS:** Ubuntu Server / Desktop LTS
- **Virtualization:** VirtualBox
- **Networking:** NAT
- **Access Method:** Local console and SSH
- **SSH Service:** OpenSSH

---

## Tools & Commands Used

- `openssh-server`
- `ssh`
- `ssh-keygen`
- `ssh-copy-id`
- `systemctl`
- `sshd_config`
- `nano` / `vi`

---

## Lab Steps

### Step 1: Install and Verify SSH Service

Install OpenSSH server (if not already installed):

```bash
sudo apt update
sudo apt install -y openssh-server



Verify SSH service status:

sudo systemctl status ssh


Ensure the service is active and running.

Step 2: Generate SSH Key Pair (Client)

On the client system (host or another VM):

ssh-keygen -t ed25519 -C "devuser@ubuntu-vm"


Accept the default file location and optionally set a passphrase.

Step 3: Copy Public Key to Server

Copy the SSH public key to the Ubuntu VM:

ssh-copy-id devuser@<vm-ip-address>


Test key-based login:

ssh devuser@<vm-ip-address>


Successful login without a password confirms key-based authentication.

Step 4: Harden SSH Configuration

Edit SSH daemon configuration:

sudo nano /etc/ssh/sshd_config


Apply the following secure settings:

PermitRootLogin no
PasswordAuthentication no
PubkeyAuthentication yes
AllowUsers devuser
MaxAuthTries 3
LoginGraceTime 30


Save and exit.

Step 5: Validate Configuration and Restart SSH

Test configuration syntax:

sudo sshd -t


Restart SSH service:

sudo systemctl restart ssh

Step 6: Verify Hardened Access Controls

From the client system:

Confirm SSH access works for devuser

Attempt password-based login (should fail)

Attempt root login (should fail)

Validation & Verification

Successful completion is confirmed by:

SSH service running and accessible

Key-based authentication functioning correctly

Password authentication disabled

Root login disabled

SSH access restricted to approved users

No configuration errors on SSH restart

Optional validation:

SSH access logged in /var/log/auth.log

Snapshot created post-hardening

Security & Compliance Considerations

SSH keys provide stronger authentication than passwords

Disabling root login enforces accountability and traceability

Restricted user access reduces attack surface

Configuration aligns with CIS Linux Benchmark recommendations

Changes are reversible using snapshots and versioned configs

Lessons Learned

SSH is a high-risk service that requires explicit hardening

Key-based authentication significantly improves security posture

Restricting access by user enforces least-privilege principles

These controls directly map to cloud VM and EC2 hardening practices

This hardened SSH configuration establishes a secure remote access baseline
for automation, configuration management, and cloud connectivity.

Next Lab

Lab #4: Firewall Configuration with UFW

Default-deny inbound traffic

Allow SSH explicitly

Validate network exposure

Prepare system for service deployment




Install OpenSSH server (if not already installed):

```bash
sudo apt update
sudo apt install -y openssh-server
