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
- Account Lockout Policy
- 
- Dealing with account lockouts

<h2>Deployment and Configuration Steps</h2>

<p>

<img width="3780" height="1962" alt="client1-dns-server-to-dc-1-ip" src="https://github.com/user-attachments/assets/8b0a5a89-11c2-4656-80e0-06aee508fab6" />


</p>
<p>
This screenshot shows the network configuration for the client virtual machine in Microsoft Azure. The client VM's DNS settings were changed from the default Azure-provided DNS service to a custom DNS server using the Domain Controller's private IP address (10.0.1.4).

On the right side of the image, the Domain Controller (dc-1) is shown with a private IP address of 10.0.1.4. On the left side, the client VM (client-1312) is configured to use that same IP address as its DNS server.
</p>
<br />

<p>

<img width="3591" height="1983" alt="creating new user" src="https://github.com/user-attachments/assets/5329cb8f-f63b-4d81-8ddc-0495271537c5" />

</p>
<p>
This screenshot shows the New Object – User wizard in Active Directory Users and Computers (ADUC). A new user account is being created within the _ADMINS Organizational Unit.
</p>
<br />

<p>

<img width="3684" height="1971" alt="account lockout" src="https://github.com/user-attachments/assets/230b3587-5471-4220-9d26-9d3adb44e257" />

</p>
<p>
This screenshot shows the Group Policy Management Editor configured with an Account Lockout Policy for the Active Directory domain. The policy was configured to lock a user account after five failed logon attempts, keep the account locked for 30 minutes, and reset the failed logon counter after 10 minutes. The Administrator account lockout setting was also enabled to apply the same protection to administrative accounts.
</p>
<br />

<p>



<p>
<img width="3564" height="1968" alt="user ad" src="https://github.com/user-attachments/assets/2ffebece-e19c-484d-bcdc-16568ecc1bc1" />
</p>
<p>
In this screenshot, I created and organized user accounts within separate Organizational Units to simulate how an enterprise Active Directory environment is structured. This approach simplifies administration and allows administrators to apply security and configuration policies based on a user's role or department.
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
