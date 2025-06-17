<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>VPN Setup and Configuration in Azure</h1>
This project is a tutorial and implementation guide for setting up a secure Virtual Private Network (VPN) using a virtual machine in Microsoft Azure. The purpose of the VPN is to allow encrypted remote access to internal network resources and demonstrate basic principles of tunneling, encryption, and secure network architecture.<br />

<h2>Environments and Technologies Used</h2>

- PowerShell (for provisioning and configuration)

<h2>Operating Systems Used </h2>
- Microsoft Azure (Virtual Machines, Networking)
- Windows 10 (VPN client and/or server)
- Ubuntu Server

<h2>List of Prerequisites</h2>

- Item 1 - Set Up Your Azure Account
- Item 2 - Create a Resource Group
- Item 3 - Create a Virtual Network (VNet)
- Item 4 - Provision a Virtual Machine (VPN Server)
- Item 5 - Configure Network Security Group (NSG)
- Item 6 - Prepare local machine
- Item 7 - Enable Remote Access

<h2>Installation Steps</h2>

1. Prepare the Windows Environment
Deploy a Windows 10 Virtual Machine on Azure (or use a local one).
Connect to the VM via Remote Desktop.
</p>


![96F207F5-3478-4388-B54E-F4B30EACC09D_1_105_c](https://github.com/user-attachments/assets/0433227d-951e-4c72-a6e8-29ea25c9b95f)

![5CB548B7-E674-4E02-89E4-769D6B930321](https://github.com/user-attachments/assets/99d3ea78-dabf-40d6-a6f5-d3b5e5d271d1)

<p>
2. Install IIS
Open Control Panel > Programs > Turn Windows features on or off.
Enable Internet Information Services and CGI under IIS.
Restart the machine if prompted.
<p>
3. Install PHP
Download PHP from the official site (https://windows.php.net/download).
Extract it to C:\PHP.
Configure php.ini:
Enable extensions: mysqli, pdo_mysql, gd, imap, xml, mbstring, intl
Add C:\PHP to the system Environment Variables > Path.
In IIS, configure a new Handler Mapping for PHP.
</p>

![Image](https://github.com/user-attachments/assets/648751ef-711a-42f1-9ea7-f256e18214b9)

<p>
4. Install MySQL Server
Download MySQL Community Server from https://dev.mysql.com/downloads/mysql/.
Install and configure with a root password.
Create a new database and user for osTicket using MySQL Workbench or the MySQL shell.
5. Download and Install osTicket
Download the latest stable version of osTicket.
Extract the files into C:\inetpub\wwwroot\osTicket.
Set file permissions (ensure IIS can write to /include and /setup).
Navigate to http://localhost/osTicket/setup in your browser.
Follow the installation wizard:
Enter database info, admin credentials, and system name.
Upon completion, delete the /setup directory and set /include/ost-config.php to read-only.

![0821AAFD-13B7-47BD-9E4E-A3A2C73ACE89](https://github.com/user-attachments/assets/ad07bc83-cd1c-450f-94f7-35cf89080221)

</p>
<br />
