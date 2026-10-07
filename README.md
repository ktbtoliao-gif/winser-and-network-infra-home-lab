# active-directory-home-lab
# Windows Server & Network Infrastructure Home Lab

A hands-on home lab simulating a small-business Windows environment using VMware Workstation, Windows Server 2022, and Windows 10.

The lab focuses on **System Administration, Windows networking, Active Directory, DNS, Group Policy, file permissions, and troubleshooting**.

## Lab Environment

| Component  | Configuration                  |
| ---------- | ------------------------------ |
| Hypervisor | VMware Workstation Pro 25H2    |
| Server     | Windows Server 2022 Datacenter |
| Client     | Windows 10 22H2                |
| Network    | VMware VMnet1 Host-Only        |
| Network    | 192.168.10.0/24                |
| Domain     | lab.local                      |
| Server IP  | 192.168.10.10                  |
| Client IP  | 192.168.10.20                  |

## Objectives

* Build an isolated Windows network environment
* Configure static IPv4 addressing and DNS
* Deploy Windows Server 2022 as a Domain Controller
* Configure Active Directory Domain Services
* Join a Windows 10 workstation to the domain
* Create Organizational Units, users, and security groups
* Implement Group Policy
* Configure file shares and NTFS permissions
* Practice Windows firewall and connectivity troubleshooting
* Analyze Windows Security event logs
* Verify configurations through testing and command-line tools

## Technologies & Tools

**System Administration**

* Windows Server 2022
* Active Directory
* Group Policy
* DNS
* File Services
* NTFS Permissions
* Windows Event Viewer

**Networking**

* IPv4 addressing
* Subnetting
* DNS
* ICMP
* Windows Firewall
* VMware Host-Only Networking

**Tools / Commands**

* PowerShell
* `ipconfig`
* `ping`
* `nslookup`
* `gpupdate`
* `gpresult`
* `auditpol`
* `icacls`
* `Get-ADGroupMember`
* `Get-SmbShare`

## What I Built

### 1. Virtual Network

Created an isolated VMware VMnet1 host-only network using:

`192.168.10.0/24`

DHCP was disabled so the lab could use manually assigned static addresses.

### 2. Windows Server & Active Directory

Configured Windows Server 2022 as a Domain Controller for:

`lab.local`

Configured:

* Active Directory Domain Services
* DNS
* Global Catalog
* Organizational Units
* Security Groups
* Domain Users

### 3. Windows Client

Joined a Windows 10 workstation to the `lab.local` domain and organized the computer object under the Workstations OU.

### 4. Group Policy

Implemented centralized policies including:

* Password complexity
* Password length
* Account lockout
* Control Panel restrictions
* Logon banner
* Department drive mapping
* Logon auditing

### 5. File Shares & Permissions

Created department file shares for:

* HR
* IT
* Sales

Access was controlled using security groups and NTFS permissions.

Access was tested using both **allowed and denied scenarios**.

### 6. Troubleshooting

I intentionally tested and investigated several common Windows administration issues, including:

* Failed connectivity caused by Windows Firewall
* Missing Group Policy drive mappings
* Account lockouts
* Failed logon events
* DNS behavior after Domain Controller promotion
* Incorrect VMware host-only subnet configuration
* UAC and administrator credential prompts

## Verification

The environment was tested after configuration.

Examples include:

* Server ↔ client connectivity
* DNS resolution
* Domain joining
* Domain authentication
* Group membership
* Group Policy application
* Network drive mapping
* File-share access control
* Account lockout behavior
* Windows Security event analysis

All documented tests passed.

## Documentation

For the complete build process, configuration details, verification steps, troubleshooting notes, and lessons learned:

**[View the complete Home Lab Documentation](documentation/Home_Lab_Documentation.pdf)**

## Key Takeaways

This project helped me develop practical experience with Windows administration and network troubleshooting.

A major focus was learning to troubleshoot systematically by checking configuration, testing connectivity, reviewing applied policies, and analyzing event logs instead of relying on assumptions.

## Future Improvements

* Add a DHCP server
* Add a second Domain Controller
* Configure Active Directory replication
* Add centralized logging/SIEM
* Practice delegated administration
* Automate user provisioning with PowerShell

---

**Author:** Kyla Trisha B. Toliao
**Focus:** System Administration | Network Support | Windows Infrastructure
