# active-directory-deployment
A guide on deploying Active Directory as part of an internal authentication, support, and knowledge suite in the cloud (Azure)

<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure)</h1>
This guide outlines the implementation of Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Protocol
- Active Directory Domain Services
- DNS
- PowerShell
- Tailscale

<h2>Operating Systems Used </h2>

- Windows Server 2022

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Initial VM deployment and Azure configurations
- Step 2: Installing and configuring tailscale
- Step 3: Adding server roles and features
- Step 4: Configuring Active Directory
- Step 5: Configuring DNS
- Step 6: Creating users and organizational units
- Step 7: Configuring group policies

<h2>Deployment and Configuration Steps</h2>
<p>
  1. Deploy your windows server VM and set the virtual NIC to a static IP in Settings>IP Configurations - this is required for domain controller and DNS server.
</p>
<p>
  <img src="https://github.com/user-attachments/assets/6c9c63bb-c197-4004-99ff-31811c43495f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />
<p>
  2. RDP into your VM and install tailscale and check "Run unattended" in the preferences submenu from the taskbar so it will automatically start upon reboots and run as the admin user you have made
</p>
<p>
  <img src="https://github.com/user-attachments/assets/51a6a800-2c6d-4b08-845b-09678bc2712e" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />
<p>
  3. When adding server roles and features, check Active Directory Domain Services, DNS, and IIS. After those are done installing, go back through server roles and features again and check CGI under IIS->Application Development.
</p>
<p>
  <img src="https://github.com/user-attachments/assets/62487467-6101-49b5-bdf0-81e8842a438d" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />
<p>
  4. Promote your server to domain controller, configuring your new forest, domain, and DSRM password
</p>
<p>
  <img src="https://github.com/user-attachments/assets/5521bb17-624b-44ce-ac2d-314228d9db2e" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />
<p>
  5. In Tailscale admin DNS settings add a split DNS nameserver at the internal tailscale IP for your domain. This is so you can utilize Tailscale's magic DNS for internal FQDN.
</p>
<p>
  <img src="https://github.com/user-attachments/assets/a0d838cb-4f2c-4e74-b610-73e27b3590cc" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />
<p>
  6. 
</p>
<p>
  <img src="https://github.com/user-attachments/assets/a0d838cb-4f2c-4e74-b610-73e27b3590cc" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
