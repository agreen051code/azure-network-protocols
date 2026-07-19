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
<img width="3441" height="1962" alt="log in bume user" src="https://github.com/user-attachments/assets/dc069eab-f33c-49d4-996d-635fe4b2b7bf" />

</p>
<p>
The _EMPLOYEES OU contains user accounts that represent employees in the organization. Organizing users into dedicated OUs makes it easier to manage accounts, delegate administrative tasks, and apply Group Policy Objects to user groups rather than configuring each account individually.

In this lab, I created and organized user accounts within separate Organizational Units to simulate how an enterprise Active Directory environment is structured. This approach simplifies administration and allows administrators to apply security and configuration policies based on a user's role or department.
</p>
<br />

<p>
<img width="3738" height="1935" alt="final lockout" src="https://github.com/user-attachments/assets/0b587c22-fc29-4892-8e32-be620449ea1e" />

</p>
<p>
The left side of the screenshot shows that the user is unable to sign in because the account has been locked after exceeding the maximum number of failed login attempts. Windows displays an error indicating that the account has been temporarily locked as a security measure to help protect against unauthorized access.


The right side of the screenshot shows Active Directory Users and Computers with the user's account properties open on the Account tab. The account lockout was confirmed by the "Unlock account. This account is currently locked out on this Active Directory Domain Controller." option. After verifying the issue, the account was unlocked, allowing the user to authenticate successfully and regain access to domain resources.
</p>
<br />
