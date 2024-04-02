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

- Windows 10 (22H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Ping virtual machine within private network
- Configure NSG
- Observe denial of traffic
- Monitor traffic

<h2>Actions and Observations</h2>

<p>

![A](https://github.com/kennyfrantz/azure-network-protocols/assets/163783743/2612e1ab-9010-4328-962b-4907751df017)
</p>
<p>
I began this exercise by pinging another virtual machine within my private network to ensure connectivity.
</p>
<br />

<p>

![Screen Shot 2024-03-29 at 11 13 36 AM](https://github.com/kennyfrantz/azure-network-protocols/assets/163783743/1546437b-87c9-4e29-b002-b0c05e182882)
</p>
<p>
Next I went into the network security group settings.  Here I created a rule to block inbound ICMP traffic with a higher priority than the other rules.  This would ensure that it would stop the traffic.
</p>
<br />

<p>

![Screen Shot 2024-03-29 at 11 16 15 AM](https://github.com/kennyfrantz/azure-network-protocols/assets/163783743/29019a81-e5a0-44b4-97ad-306cfb850bcb)
</p>
<p>
This image shows my NSG rule was successful in blocking the inbound traffic to this virtual machine.  It allowed me to see what would happen when I pinged it and received a timed out request while using WireShark as well as the command prompt.
</p>
<br />
<p>
  
</p>

![Screen Shot 2024-03-29 at 11 40 23 AM](https://github.com/kennyfrantz/azure-network-protocols/assets/163783743/d47420f9-7cb9-434d-849e-2905d4a1dd13)

I practiced examining various protocols while utilizing WireShark.  Above is monitoring SSH traffic.
