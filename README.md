<div align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</div>

<h1 align="center"> Active Directory Deployed in the Cloud (Azure)</h1>

<h2 align="center">Summary</h2>
  
<p>This readme.md outlines the deployment of Active Directory within two Azure Virtual Machines. The purpose of this project was to get a better understanding of both Azure and Active Directory, and the process of setting up a Windows Server installation as a domain controller for Active Directory. We also used Powershell to help us generate many random users into Active Directory. This project was repeated multiple times to ensure we gained a strong understanding of Active Directory and it's basic functions.</p>

<h2 align="center">Environments and Technologies Used</h2>

- Microsoft Azure
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2 align="center">Operating Systems Used </h2>

- Windows Server 2022
- Windows 10

<h2 align="center">Macro-Level Deployment and Configuration Steps</h2>

- Set-up two different virtual machines: a regular Windows 10 installation and a Windows Server installation.
- Double check the connectivity between the two different virtual machines using _ping_.
- Install Active Directory onto the Windows Server installation.
- Create two groups within Active Directory, Admin's and Users, and make a new Admin user that we will use going forward to test that we set-up permissions properly.
- Link the client computer (Windows 10 installation) to the domain controller (Windows Server installation).
- Allow non-admin users to log-in to the client computer.
- Generate a large number of random users using Powershell and ensure they have the proper permissions by logging into the client on one of the accounts generated.

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
