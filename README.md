<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

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

- Create Windows virtual machine and create a Linux virtual machine
- Download and install Wireshark
- Use Windows Powershell to ping VM2
- Change the NSG to block icmp traffic on vm2

<h2>Actions and Observations</h2>
<img width="725" alt="Screen Shot 2023-08-29 at 10 20 14 AM" src="https://github.com/malikharris4587/azure-network-protocols/assets/143438495/b66c72a3-6727-47d3-a96f-8fdfcf46e6e0">
<img width="752" alt="Screen Shot 2023-08-29 at 10 20 42 AM" src="https://github.com/malikharris4587/azure-network-protocols/assets/143438495/88a456d2-ea4f-4517-a600-409843e6e516">
<img width="710" alt="Screen Shot 2023-08-29 at 10 21 30 AM" src="https://github.com/malikharris4587/azure-network-protocols/assets/143438495/a248b136-4521-4940-884f-14d148d300b7">
<p>
Create Windows virtual machine and create a Linux virtual machine with the above configurations. For Linux set the authentication type to password instead of SSH.
</p>
<br />

<img width="626" alt="Screen Shot 2023-08-29 at 10 31 08 AM" src="https://github.com/malikharris4587/azure-network-protocols/assets/143438495/6f03eafd-db0a-47b2-ac85-9d8c359e62ae">
<img width="809" alt="Screen Shot 2023-08-29 at 10 31 22 AM" src="https://github.com/malikharris4587/azure-network-protocols/assets/143438495/e5f69c60-d10a-4d22-8aea-6f96385acb86">
<img width="405" alt="Screen Shot 2023-08-29 at 10 37 46 AM" src="https://github.com/malikharris4587/azure-network-protocols/assets/143438495/d3a80016-f59c-4502-853b-00971f8b2c50">
<img width="800" alt="Screen Shot 2023-08-29 at 10 44 19 AM" src="https://github.com/malikharris4587/azure-network-protocols/assets/143438495/a643470b-cdfc-4065-9fc5-9f264684a37b">
<img width="945" alt="Screen Shot 2023-08-29 at 10 43 51 AM" src="https://github.com/malikharris4587/azure-network-protocols/assets/143438495/75bca63f-6597-4f43-a478-e1c6b876e0c4">
<img width="724" alt="Screen Shot 2023-08-29 at 10 45 23 AM" src="https://github.com/malikharris4587/azure-network-protocols/assets/143438495/6ea7fb74-b5b7-4494-97cc-5e80d9cc6746">


<p>
download and install wireshark on VM1. After installing and opening it up. Click on ethernet then the blue icon on the top left to start capturing packets. ALthough you may not be doing anything there may be a lot of traffic happening in the background. Filter the traffic so it stops spamming everything. zizn the top bar type in ICMP. Find the IP address of VM2. You can find it on the the azure portal. Go to VM2 and locate the private ip address. Now in VM1 find the stock app, Powershell. Then type in ping and type in the vm2 private ip address. click enter. You can do this for all sorts of Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP).
</p>
<br />

<img width="1339" alt="Screen Shot 2023-08-29 at 10 50 58 AM" src="https://github.com/malikharris4587/azure-network-protocols/assets/143438495/2b54f983-3254-4c0b-9d69-6f7d953408ce">
<img width="1341" alt="Screen Shot 2023-08-29 at 10 52 49 AM" src="https://github.com/malikharris4587/azure-network-protocols/assets/143438495/910f020e-e70d-4c1c-9307-eaec152db23d">
<img width="411" alt="Screen Shot 2023-08-29 at 10 52 40 AM" src="https://github.com/malikharris4587/azure-network-protocols/assets/143438495/4fb249b4-e11e-475d-a47a-c3ca9a43c4d7">

<p>
Here you want to manipulate the firewall to block various protocols. here we will block icmp traffic on vm2. Go to Azure-type in Network security group-vm2-settings0inbound security rules-add-select icmp protocol-set action to deny-change priority # to earlier number-change name. Now Windows powerwall and wireshark will reflect that change. The request will time out. If you delete this rule you will start seeing traffic flow again. 
</p>
<br />
