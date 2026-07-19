<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Preparing Active Directory in Microsoft Azure
- Create User
- 
- 

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="3780" height="1962" alt="client1-dns-server-to-dc-1-ip" src="https://github.com/user-attachments/assets/c757ffda-3881-49b8-bbf9-b512893d9756" />

</p>
<p>
In Microsoft Azure, I changed the network interface DNS settings for the client VM (client-1312) from Azure's default DNS to a custom DNS server pointing to my Domain Controller (10.0.1.4). This allows the client to locate Active Directory services so it can join the domain and authenticate users.
</p>
<br />

<p>
<img width="3591" height="1983" alt="creating new user" src="https://github.com/user-attachments/assets/b2257b37-a3a0-47c7-b53f-cc2537ef9b3b" />

</p>
<p>
This screenshot shows the New Object – User wizard in Active Directory Users and Computers. At this stage, a new user account is being created inside the _ADMINS Organizational Unit (OU) of the mydomain.com domain.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

