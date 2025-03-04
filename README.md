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
  <img src="https://imgur.com/bPFWA8U" height="75%" width="100%" alt="Resource Group"/>
</p>

Deployed a Windows 10 Virtual Machine, allowing Azure to generate a new Virtual Network (Vnet) and Subnet.

Deployed an Ubuntu Virtual Machine within the same Resource Group and Vnet.

Used Azure Network Watcher to observe the virtual network setup.

ICMP Traffic Inspection

Installed Wireshark on the Windows VM and filtered for ICMP traffic.

Retrieved the Ubuntu VM’s private IP and initiated a ping request from the Windows VM.

Observed ICMP request and reply packets in Wireshark.

Disabled inbound ICMP traffic in the NSG of the Ubuntu VM and noted how pings failed.

Re-enabled ICMP and confirmed ping requests resumed.

SSH Traffic Analysis

Filtered Wireshark for SSH traffic.

Used SSH from the Windows VM to connect to the Ubuntu VM.

Executed commands (ls, pwd, etc.) and observed encrypted SSH traffic in Wireshark.

DHCP Traffic Observation

Filtered Wireshark for DHCP traffic.

Renewed the Windows VM’s IP (ipconfig /renew).

Observed DHCP request and acknowledgment packets.

DNS Traffic Inspection

Filtered Wireshark for DNS traffic.

Used nslookup to resolve google.com and disney.com.

Observed DNS queries and responses in Wireshark.

RDP Traffic Monitoring

Filtered Wireshark for RDP traffic (tcp.port == 3389).

Noted continuous traffic, demonstrating that RDP constantly transmits data for a live remote session.

Conclusion

This project provided hands-on experience in monitoring network traffic between virtual machines in Azure and understanding how NSGs impact connectivity. By analyzing different protocols, it showcased how traffic behaves under various security configurations.
