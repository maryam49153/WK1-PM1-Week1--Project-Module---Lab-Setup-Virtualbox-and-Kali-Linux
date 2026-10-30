# WK1-PM1-Week1--Project-Module---Lab-Setup-Virtualbox-and-Kali-Linux
# 🔐 Virtual Cybersecurity Lab | Week 01

**A Practical Lab Setup with VirtualBox and Kali Linux**

## 📌 Introduction

This project documents the creation of a virtual environment for learning cybersecurity fundamentals and performing authorized security experiments.

Using Oracle VirtualBox and Kali Linux, the lab provides a foundation for exploring virtual networking, system configuration, connectivity troubleshooting, and virtual machine recovery.

The environment is designed to support additional lab machines in future exercises.

## 🎯 Project Goals

The key goals of this project are to:

- Install and prepare VirtualBox for virtualization.
- Set up Kali Linux as the primary security-testing VM.
- Build a dedicated NAT Network for the lab.
- Configure Kali Linux IPv4 network settings.
- Check gateway access, Internet connectivity, and DNS resolution.
- Configure host-to-guest file sharing.
- Create a baseline snapshot for recovery.
- Maintain clear technical documentation with screenshots.

## 🏗️ Environment Design

The initial setup uses one Kali Linux virtual machine connected to a dedicated VirtualBox NAT Network. Additional virtual machines may be connected later for controlled testing.

**Network plan**

| Setting | Planned Configuration |
|---|---|
| Host Operating System | Windows 10 |
| Virtualization Platform | Oracle VirtualBox |
| Guest Operating System | Kali Linux |
| VM Memory | 2048 MB |
| Network Mode | NAT Network |
| Network Name | NatNetwork |
| IPv4 Network | `10.0.0.0/24` |
| Kali IPv4 Address | `10.0.0.2/24` |
| Planned Gateway | `10.0.0.1` |
| DNS Server | `8.8.8.8` |
| Potential Future VM Addresses | `10.0.0.3–10.0.0.99` |

*Note: These are the intended settings. Actual gateway, DNS, and connectivity must be confirmed through testing.*

## ⚙️ Implementation Steps

### 1. Prepare the Virtualization Platform

VirtualBox was selected to run the lab environment. The host system provides the resources required to operate the Kali Linux guest machine.

### 2. Set Up a Dedicated Virtual Network

A NAT Network named `NatNetwork` was created with the IPv4 prefix `10.0.0.0/24`.

The network is intended to let connected lab VMs communicate with each other while supporting outbound connectivity through VirtualBox network address translation.

### 3. Install Kali Linux

Kali Linux was installed as a virtual machine in VirtualBox and allocated 2048 MB of memory.

The VM network adapter is intended to use:

- **Attachment:** NAT Network
- **Network:** NatNetwork
- **IPv4 address:** `10.0.0.2/24`

### 4. Configure IPv4 Networking

The Kali network configuration was examined using Linux networking commands. A consistent IP address was planned to make the machine easier to identify in later lab exercises.

The following settings should be checked:

- IP address and subnet mask
- Default route and gateway reachability
- DNS configuration
- External network access

### 5. Configure Host-to-Guest File Sharing

A shared folder is planned to simplify the transfer of lab documents and other permitted files between Windows and Kali Linux. Shared-folder access and VirtualBox Guest Additions should be tested before marking this step complete.

### 6. Establish a Recovery Point

A snapshot named `Clean Kali - Network Setup` is recommended after the initial configuration has been verified.

A baseline snapshot helps restore the VM to a known configuration if later experiments affect its settings.

## 🧪 Verification Checklist

Run the checks below and record the actual results in the project documentation.

| Check | Command or Action | Status |
|---|---|---|
| IP configuration | `ip a` | To be verified |
| Routing table | `ip route` | To be verified |
| Gateway reachability | `ping -c 4 10.0.0.1` | To be verified |
| External connectivity | `ping -c 4 8.8.8.8` | To be verified |
| DNS resolution | `nslookup networkwalks.com` | To be verified |
| Nmap installation | `nmap --version` | To be verified |
| Shared-folder access | Open the configured shared folder | To be verified |
| Snapshot | Check the VM snapshot list | To be verified |

**Verification note:** A configured IP address alone does not prove that the network is working. Gateway access, external connectivity, and DNS resolution should be tested separately.

## 🐞 Troubleshooting Notes

### Network Connectivity

Static IP configuration may require additional troubleshooting if the gateway cannot be reached.

The troubleshooting process should include:

1. Confirm that the VM adapter is connected to `NatNetwork`.
2. Check the NAT Network configuration in VirtualBox.
3. Review the guest's IP address and routing table.
4. Test gateway access before testing external IP connectivity.
5. Investigate DNS only after basic network connectivity is working.

Record the actual error message and the confirmed fix rather than documenting an unverified workaround.

### Virtualization Support

If the VM does not start because hardware virtualization is disabled, check the computer's BIOS/UEFI settings for Intel VT-x or the equivalent virtualization option. Availability and menu names depend on the host hardware.

## 📚 Key Learning Outcomes

This project introduces several important concepts:

**Virtualization:** Running a separate operating system inside a virtual machine.

**NAT and NAT Network:** Understanding how virtual machines access external networks and how machines on a shared virtual network can communicate.

**IPv4 Configuration:** Working with addresses, subnet masks, default routes, and DNS settings.

**Troubleshooting:** Testing different layers of connectivity to identify where a network problem occurs.

**Snapshots and Recovery:** Keeping a baseline that can be used to restore a VM.

**Technical Documentation:** Recording configuration details, screenshots, test results, and troubleshooting steps.

## 🛡️ Responsible Use

This environment is intended for education and authorized security testing only. Any future reconnaissance, scanning, or vulnerability assessment should be restricted to systems owned by the learner or systems for which explicit permission has been granted.

## 🔗 Official Resources

- [Oracle VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)
- [Kali Linux Downloads](https://www.kali.org/get-kali/)
- [7-Zip Downloads](https://www.7-zip.org/download.html)

## 👩‍💻 Project Details

- **Program:** Networkwalks Cybersecurity Program
- **Batch:** B082
- **Week:** 01
- **Project:** Cybersecurity Lab Environment Setup
- **Author:** Maryam Ilyas

---

*This README documents the lab setup plan and verification checklist. Update the test statuses and add screenshots as each configuration step is completed and confirmed.*
