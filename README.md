<p align="center">
  <img src="https://i.imgur.com/Ua7udoS.png" height="80%" width="80%" alt="Ubuntu VM" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Traffic Inspection in Azure</h1>
This project demonstrates how network traffic flows between Azure Virtual Machines using Wireshark. It also explores how Network Security Groups (NSGs) affect different protocols, including ICMP, SSH, DHCP, DNS, and RDP.

<h2>Technologies Used</h2>

- Microsoft Azure (Virtual Machines, Compute, Network Security Groups)
- Remote Desktop
- Wireshark (Protocol Analyzer)
- Command-Line Tools
- Network Protocols (ICMP, SSH, DHCP, DNS, RDP)
- Operating Systems: Windows 10 (21H2), Ubuntu Server 20.04

<h2>Steps & Observations</h2>

<h3>Virtual Environment Setup</h3>

Created a Resource Group in Azure.
<p>
  <img src="https://imgur.com/bPFWA8U.png" height="75%" width="100%" alt="Resource Group"/>
</p>

Deployed a Windows 10 Virtual Machine, allowing Azure to generate a new Virtual Network (Vnet) and Subnet.
<p>
  <img src="https://imgur.com/saRXqr0.png" height="75%" width="100%" alt="Resource Group"/>
</p>

Deployed an Ubuntu Virtual Machine within the same Resource Group and Vnet.
<p>
  <img src="https://imgur.com/4RBahD9.png" height="75%" width="100%" alt="Resource Group"/>
</p>

<h3>ICMP Traffic Inspection</h3>

Installed Wireshark on the Windows VM and filtered for ICMP traffic.

Retrieved the Ubuntu VM’s private IP and initiated a ping request from the Windows VM.

Observed ICMP request and reply packets in Wireshark.
<p>
  <img src="https://imgur.com/Um9n1zE.png" height="75%" width="100%" alt="Resource Group"/>
</p>
<p>
  <img src="https://imgur.com/0SRCXKh.png" height="75%" width="100%" alt="Resource Group"/>
</p>

Disabled inbound ICMP traffic in the NSG of the Ubuntu VM and noted how pings failed.
<p>
  <img src="https://imgur.com/peYNbME.png" height="75%" width="100%" alt="Resource Group"/>
</p>
<p>
  <img src="https://imgur.com/NiQGYX0.png" height="75%" width="100%" alt="Resource Group"/>
</p>

Re-enabled ICMP and confirmed ping requests resumed.
<p>
  <img src="https://imgur.com/kbQ9kB6.png" height="75%" width="100%" alt="Resource Group"/>
</p>
<p>
  <img src="https://imgur.com/Jv2k1iR.png" height="75%" width="100%" alt="Resource Group"/>
</p>

<h3>SSH Traffic Analysis</h3>

Filtered Wireshark for SSH traffic.

Used SSH from the Windows VM to connect to the Ubuntu VM.

Executed commands (ls, pwd, etc.) and observed encrypted SSH traffic in Wireshark.
<p>
  <img src="https://imgur.com/8NNVKbq.png" height="75%" width="100%" alt="Resource Group"/>
</p>

<h3>DHCP Traffic Observation</h3>

Filtered Wireshark for DHCP traffic.

Renewed the Windows VM’s IP (ipconfig /renew).

Observed DHCP request and acknowledgment packets.
<p>
  <img src="https://imgur.com/qN1qM66.png" height="75%" width="100%" alt="Resource Group"/>
</p>

<h3>DNS Traffic Inspection</h3>

Filtered Wireshark for DNS traffic.

Used nslookup to resolve google.com and disney.com.

Observed DNS queries and responses in Wireshark.
<p>
  <img src="https://imgur.com/xE83zjA.png" height="75%" width="100%" alt="Resource Group"/>
</p>

<h3>RDP Traffic Monitoring</h3>

Filtered Wireshark for RDP traffic (tcp.port == 3389).

Noted continuous traffic, demonstrating that RDP constantly transmits data for a live remote session.
<p>
  <img src="https://imgur.com/WgXotrH.png" height="75%" width="100%" alt="Resource Group"/>
</p>

Conclusion

This project provided hands-on experience in monitoring network traffic between virtual machines in Azure and understanding how NSGs impact connectivity. By analyzing different protocols, it showcased how traffic behaves under various security configurations.
