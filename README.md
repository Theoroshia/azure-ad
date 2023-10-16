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
It is critical that both of these virtual machines are running on the same network, something that Azure does mostly automatically as long as the two virtual machines are in the same resource group. We can test this by running the <i>ping</i> command. Doing this initially will result in no response being sent back from the server to the client. This is because by default Windows Server edition does not allow ICMP protocols, which the <i>ping</i> command uses to connect. We enable this on the server installation so we can test the connectivity between the server and the client. Once this is done, we can check back on our <i>ping</i> and see that the server is now responding to the client.
</p>
<br />
<p align="center">
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/1596195/275225006-1c01942f-7ed3-429b-bedf-bf637fb50a7a.png" width="75%" height="75%">
</p>
<p>
Now we can begin the process of installing Active Directory onto our Windows Server installation and making it a domain controller. The process is fairly simple, as Active Directory is built-in to Windows Server but not installed by default. First we have to login to our Windows Server installation using Remote Desktop. Then, we open up Server Manager and began configuring our server. We follow most of the prompts and select the default options, but it is important that we install the correct Active Directory service: Active Directory Domain Services. We follow the rest of the prompts and wait for Active Directory to be installed.
</p>
<p align="center">
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/1596195/275499949-67b034a6-5065-497e-8c46-24b70ebf9d2f.png" width="75%" height="50%">
</p>
<p>
A final step is to configure the server as a domain controller. This is also a relatively easy step. We simply go back into Server Manager and select the option to promote the server to a domain controller. Now we can begin the process of actually adding users to Active Directory and simulating what it would be like to work with this software in an IT setting. To do this we need to make two different accounts: an administrator account and a user account. First we open up Active Directory Users and Computers. Then, we add two new Organization Units: Admins and Users. This step is technically optional, as Organizational Units don't really have a mechanical use within Active Directory. However, by doing this we can stay organized and that will help not only us but anyone adding or editing users in the future. Next we right click in the Admins folder and add a new user, Jane Doe. After adding the user we then want to grant this user Admin privileges. We do this by right clicking the account and giving it the administrator role.
</p>
<p align="center">
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/1596195/275513957-66a56bad-a044-459a-91c9-57b66d766549.png" width="75%" height="75%"></img>
</p>
<p>
We do a similar process to add a regular user, named John Doe, and give them User privileges. Our next step is to link the client installation to the newly created domain controller. To do this, we need to login to Microsoft Azure and change the DNS server that our Windows 10 installation is using. In the virtual network interface for the Windows 10 installation, we edit it's DNS settings so that it points to the Windows Server installation's private IP address. Then we restart both of our virtual machines to flush the DNS cache and the Windows 10 installation will be linked to the Windows Server installation, which is serving as the domain controller.
</p>
<p align="center">
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/1596195/275551767-6479b3a3-220a-43a7-b354-fd71255e48af.png" width="75%" height="75%"></img>
</p>
<p>
To actually add the client PC to the domain controller, we now have to edit the client PC's settings and login to the domain controller using System Properties. The client PC will restart and then it is officially connected as a client to the domain controller.
</p>
