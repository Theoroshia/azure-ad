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

<h2 align="center">Deployment and Configuration Steps</h2>

<p align="center">
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/1596195/275220186-b4d8a88c-d56d-45df-9d28-db519518124b.png" width="75%" height="75%">
</p>
<p>
Our first step in this project is to create two different virtual machines within Azure. The first one will be a Windows Server installation, and will serve as the domain controller. A domain controller is simply a server running Active Directory, and it's role is to authenticate users and devices that try and connect to the server. The second installation will be a regular Windows 10 installation and will serve as the client computer, which we will use to connect to the domain controller. We do this by opening Microsoft Azure in our browser and generating two virtual machines. In the set-up for one, we install Windows 10. In the set-up for the other one, we install Windows Server.
</p>
<br />
<p align="center">
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/1596195/275224750-e8f74b56-e6c6-4cf8-b85e-becf0ca3f98f.png" width="75%" height="100%">
</p>
<p>
It is critical that both of these virtual machines are running on the same network something that Azure does mostly automatically as long as the two virtual machines are in the same resource group. We can test this by running the _ping_ command. Doing this initially will result in no response being sent back from the server to the client. This is because by default Windows Server edition does not allow ICMP protocols, which the _ping_ command uses to connect. We enable this on the server installation so we can test the connectivity between the server and the client.
</p>
<br />

