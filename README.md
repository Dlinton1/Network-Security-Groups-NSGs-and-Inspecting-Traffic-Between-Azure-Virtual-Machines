<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create 2 VM's on Azure
- Login to both VM's using remote desktop
- Download wireshark on 1 of the VM's
- Use wireshark to observe the traffic between the 2 VM's using different command lines and protocols

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/9RazVgO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
For the purpose of this exercise, the virtual machines were provisioned on the same virtual network and subnet in Azure.
</p>
<br />

<p>
<img src="https://i.imgur.com/Ec8NVnG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
While using Wireshark to monitor the network traffic between both VMs, I conducted a ping test from VM-1 to VM-2 using PowerShell, and received a successful reply as they are connected to the same virtual network. To observe the effect of blocking ICMP traffic from VM-1 to VM-2, I initiated a continuous ping test and then analyzed the traffic on Wireshark.
</p>
<br />

<p>
<img src="https://i.imgur.com/QJfPca9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This Azure setting blocks ICMP traffic from one VM to another. After enabling this setting, the perpetual ping ceased and resulted in continuous "request timed out" messages.
</p>
<br />
