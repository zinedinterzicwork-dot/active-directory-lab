# active-directory-lab
📌 Overview

This project demonstrates the setup and configuration of a basic Active Directory (AD) environment using Oracle VirtualBox.
The lab simulates a real-world enterprise network where a Domain Controller manages a client machine within a private network.

The goal of this project was to gain hands-on experience with:

-Active Directory Domain Services (AD DS)
-DNS configuration
-Network troubleshooting
-Domain joining processes

-Lab Environment-
Component	Details:
Virtualization	> Oracle VirtualBox
Domain Controller >	Windows Server
Client Machine >	Windows 10
Network Type >	Internal Network (intnet)
Domain Name >	home.local

-Network Configuration-

Device:         	    IP Address	        Role
Domain Controller	    192.168.100.10	    DNS + AD DS
Client Machine	      192.168.100.20	    Domain-joined workstation

Key Configuration Notes:
-Static IP addressing was used (no DHCP server present)
-DNS on the client points to the Domain Controller
-Both machines are connected to the same VirtualBox internal network

-Setup Process-

1. Domain Controller Setup
-Installed Active Directory Domain Services (AD DS)
-Promoted server to Domain Controller
-Created domain: home.local
-Configured DNS role automatically during AD setup

2. Network Configuration
-Identified issue with APIPA (169.254.x.x) addressing
-Assigned static IP addresses to both machines
-Configured DNS to point to the Domain Controller

3. Client Configuration
-Set static IP configuration
-Verified connectivity using ping
-Verified DNS resolution for home.local

4. Domain Join
-Successfully joined client machine to home.local
-Authenticated using domain administrator credentials
-Verified domain connectivity after reboot

-Verification-

Network Connectivity:
ping 192.168.100.10

DNS Resolution:
ping home.local

Expected Result_
-Successful replies from Domain Controller
-Domain name resolves correctly via DNS

-Troubleshooting-
❌ Issue: Domain Controller could not be contacted

Cause:

-Client received APIPA address (169.254.x.x)
-No DHCP server present
-DNS not configured correctly

Solution:

-Assigned static IP addresses
-Configured client DNS to point to Domain Controller
-Ensured both VMs are on the same internal network

Results:
-Functional Active Directory environment created
-Client successfully joined to domain
-DNS resolution working correctly
-Network communication fully operational

!!!Future Improvements!!!
-Add additional client machines
-Create and manage domain users/groups
-Implement Group Policy Objects (GPOs)
-Configure DHCP server
-Simulate enterprise scenarios (permissions, file shares)

Summary:

This project demonstrates the ability to build, configure, and troubleshoot a foundational Active Directory environment from scratch.
It highlights practical system administration skills relevant to real-world IT infrastructure.
Thank you for reading through my first steps in Active Directory!
