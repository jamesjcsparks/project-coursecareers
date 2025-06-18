
![EDAEBFFA-8D62-41A7-9A47-3FE91953E10B](https://github.com/user-attachments/assets/cfaf0c60-5f44-4fd4-b1b3-ab9e6c1c9a3e)
</p>

<h1>VPN Setup and Configuration in Azure</h1>
This project is a tutorial and implementation guide for setting up a secure Virtual Private Network (VPN) using a virtual machine in Microsoft Azure. The purpose of the VPN is to allow encrypted remote access to internal network resources and demonstrate basic principles of tunneling, encryption, and secure network architecture.<br />

<h2>Environments and Technologies Used</h2>

- PowerShell (for provisioning and configuration)
- Microsoft Azure (Virtual Machines, Networking, NSG)

<h2>Operating Systems Used </h2>
 Microsoft Azure ,
 Windows 10, and 
 Ubuntu Server
<h2>List of Prerequisites</h2>

- Item 1 - Set Up Your Azure Account
- Item 2 - Create a Resource Group
- Item 3 - Create a Virtual Network (VNet)
- Item 4 - Provision a Virtual Machine (VPN Server)
- Item 5 - Configure Network Security Group (NSG)
- Item 6 - Prepare Local Machine
- Item 7 - Enable Remote Access

<h2>Installation Steps</h2>

Item 1: Set Up Your Azure Account
Sign up or log into your Azure Portal.
Set up a subscription with billing information.
</p>


![F04D4C78-6B96-442F-A37E-C9A239C107FB](https://github.com/user-attachments/assets/31bf8f45-6905-4498-a544-9dead10bce38)

Item 2: Create a Resource Group
Use the Azure Portal or PowerShell
<p>
Item 3: Create a Virtual Network (VNet)
Define the IP address space and subnets.

Item 4: Provision a Virtual Machine (VPN Server)
Deploy a Windows Server 2022 VM in the VNet.
Ensure RDP (port 3389) is open.
Use a Standard SKU for compatibility with RRAS and networking features.
![0EFCB00C-A9F4-45EA-892A-B6445C62EAFA](https://github.com/user-attachments/assets/b6b5dd54-2315-45f7-8598-877f11083326)

</p>


<p>
Item 5: Configure Network Security Group (NSG)
Add inbound rules to allow VPN protocols:
UDP 500 (IKE)
UDP 1701 (L2TP)
UDP 4500 (IPSec NAT-T)
TCP 1723 (PPTP)
Protocol 50 (ESP — via CLI or PowerShell)
</p>

Item 6: Prepare Local Machine (Client)
On your Windows 10 PC:
Ensure VPN Client is enabled via Network & Sharing Center.
Optional: install Wireshark for packet inspection.
![14B7C8E6-EEF4-4EDA-BB1C-6B6D9450D1A3](https://github.com/user-attachments/assets/3262949b-181e-4b73-a068-4f8dfe789eca)

</p>
<p></p>
Item 7: Enable Remote Access on the Server
Install the Remote Access role.
Configure Routing and Remote Access (RRAS) to allow VPN access.
Set up user permissions and firewall rules.
</p>
<br />
<h1>Demonstration section </h1>
<p>

This section illustrates how the configured VPN is used to establish a secure connection and access internal resources within the Azure environment.

---

### 1. VPN Connection from Windows 10 Client

The VPN connection was successfully established from a Windows 10 client using built-in VPN settings.


---

### 2. Verifying Internal Network Access

Once connected, we tested access to internal resources in the Azure Virtual Network by pinging the internal IP of the VPN server.

``powershell
ping 10.0.0.4
``
Successful ping to internal VM over the VPN tunnel

 3. Monitoring Traffic with Wireshark (Optional)
Using Wireshark, we captured and analyzed the traffic between the VPN client and server. The screenshot below shows encrypted traffic using VPN protocols such as ESP and ISAKMP.


Encrypted traffic (ESP/UDP 500) captured on Wireshark during VPN session

 4. Secure and Functional Connection
This confirms that the VPN setup allows for:

Encrypted communication
Remote access to internal resources
Successful client-server interaction through the VPN tunnel
