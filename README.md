
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

<h1>VPN Setup and Demonstration in Microsoft Azure</h1>

<h2>Installation Steps</h2>

<h3>Item 1: Set Up Your Azure Account</h3>
<ul>
  <li>Sign up or log into your Azure Portal</li>
  <li>Set up a subscription with billing information</li>
</ul>

![97708ECC-7C2B-42B7-9AA0-15B72C91DBC4](https://github.com/user-attachments/assets/1719c632-1d73-48ed-b1c7-c37a0fd92fc0)

<h3>Item 2: Create a Resource Group</h3>
<ul>
  <li>Use the Azure Portal or PowerShell</li>
</ul>

<h3>Item 3: Create a Virtual Network (VNet)</h3>
<ul>
  <li>Define the IP address space and subnets</li>
</ul>

<h3>Item 4: Provision a Virtual Machine (VPN Server)</h3>
<ul>
  <li>Deploy a Windows Server 2022 VM in the VNet</li>
  <li>Ensure RDP (port 3389) is open</li>
  <li>Use a Standard SKU for compatibility with RRAS and networking features</li>
</ul>

![478C71CD-E496-40AB-8755-7241E3DFF5F3](https://github.com/user-attachments/assets/3fe885c8-5bdb-4323-ae72-420f7c51dbf4)


<h3>Item 5: Configure Network Security Group (NSG)</h3>
<ul>
  <li>Add inbound rules to allow VPN protocols:</li>
  <ul>
    <li>UDP 500 (IKE)</li>
    <li>UDP 1701 (L2TP)</li>
    <li>UDP 4500 (IPSec NAT-T)</li>
    <li>TCP 1723 (PPTP)</li>
    <li>Protocol 50 (ESP – via CLI or PowerShell)</li>
  </ul>
</ul>

<h3>Item 6: Prepare Local Machine (Client)</h3>
<ul>
  <li>On your Windows 10 PC:</li>
  <ul>
    <li>Ensure VPN Client is enabled via Network & Sharing Center</li>
    <li>Optional: install Wireshark for packet inspection</li>
  </ul>
</ul>

![24ACB314-4933-45B6-9E28-BE2793C46874](https://github.com/user-attachments/assets/2a98afdf-c8fd-46fd-b87c-53f33c9bb09d)


<h3>Item 7: Enable Remote Access on the Server</h3>
<ul>
  <li>Install the Remote Access role</li>
  <li>Configure Routing and Remote Access (RRAS) to allow VPN access</li>
  <li>Set up user permissions and firewall rules</li>
</ul>

![image](https://github.com/user-attachments/assets/b1c06f5e-1ab3-4ae1-902b-fa254acc0e89)

<hr/>

<h2>Demonstration Section</h2>

<h3>1. VPN Connection from Windows 10 Client</h3>
<p>
The VPN connection was successfully established from a Windows 10 client using built-in VPN settings.
</p>

<h3>2. Verifying Internal Network Access</h3>
<p>
Once connected, we tested access to internal resources in the Azure Virtual Network by pinging the internal IP of the VPN server.
</p>
<pre><code>ping 10.0.0.4</code></pre>
<p>Result: Successful ping to internal VM over the VPN tunnel</p>

<h3>3. Monitoring Traffic with Wireshark (Optional)</h3>
<p>
Using Wireshark, we captured and analyzed the traffic between the VPN client and server.
The screenshot showed encrypted traffic using VPN protocols such as ESP and ISAKMP.
</p>

<h3>4. Secure and Functional Connection</h3>
<ul>
  <li>Encrypted communication</li>
  <li>Remote access to internal resources</li>
  <li>Successful client-server interaction through the VPN tunnel</li>
</ul>

