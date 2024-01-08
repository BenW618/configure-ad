<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://youtu.be/u2psfGejUPE)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (22H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

![Create VMs](https://github.com/BenW618/configure-ad/assets/140227052/e74b0900-6bfb-4f64-9944-3c851d404181)

</p>
<p>
The first thing I did was set up my resources. I created my two virtual machines. The first virtual machine was my Domain Controller. It was a Windows Server 2022 with two virtual CPUs. The second virtual machine was called Client-1. This virtual machine was a Windows 10 version with two virtual CPUs. I had also set my Domain Controller NIC Private IP address to be static. To watch me do this step by step, watch the youtube video linked above. The timestamps are from 00:00 to 05:50.
</p>
<br />

![C1 ping DC1 (Doesn't work)](https://github.com/BenW618/configure-ad/assets/140227052/2c34213c-d3d7-49b2-80ce-9ce23314f158)

</p>
<p>
Next, I tried to ensure connectivity between the client and Domain Controller. I used a remote desktop connection to connect to Client-1. Once I was connected, I ran the command prompt as an administrator and tried to ping “DC-1” private IP address. It was unsuccessful. To watch me do this step by step, watch the youtube video linked above. The timestamps are from 05:50 to 08:45.
</p>
<br />

![Open wf msc](https://github.com/BenW618/configure-ad/assets/140227052/4fb31d14-6c97-46ca-b66d-29f77df6c7da)

</p>
<p>
To fix this, I logged into another “Remote Desktop Connection” with the DC-1 virtual machine. Next, I searched “wf.msc” on the virtual machine. I then enabled both “Core Networking Diagnostics- ICMP Echo Request (ICMPv4- In)”. Next I switched back to the “Client” virtual machine to watch the ping work. To watch me do this step by step, watch the youtube video linked above. The timestamps are from 08:45 to 11:30.
</p>
<br />

![Install Active Directory](https://github.com/BenW618/configure-ad/assets/140227052/435466b4-4a51-49b3-ac5d-9167de9d6fe1)

</p>
<p>
Next, I installed Active Directory. To do this, I switched to the DC-1 virtual machine and opened up Server Manager. To watch step by step about how to install AD, watch the youtube video linked above. The timestamps are from 11:40 to 20:00.
</p>
<br />

![Create an Admin and Normal User Account in AD](https://github.com/BenW618/configure-ad/assets/140227052/02c35d83-2075-494d-b65e-a32a3e2a6dd4)

</p>
<p>
Next, I created an admin and normal user account in the active directory. After creating this admin account, I logged into the DC-1 virtual machine with the admin’s account. To watch me do this step by step, watch the youtube video linked above. The timestamps are from 20:00 to 24:00.
</p>
<br />

![Join C1 to Domain](https://github.com/BenW618/configure-ad/assets/140227052/c14e23d6-efaa-4573-b799-413c07b1283b)

</p>
<p>
Next,  I tried to connect to the domain but it didn’t work. To fix this, I setted up the DNS server. Once the DNS server was set up, I connected it to the domain successfully. To watch me do this step by step, watch the youtube video linked above. The timestamps are from 24:00 to 31:25.
</p>
<br />

![Step 9](https://github.com/BenW618/configure-ad/assets/140227052/32427e6d-26b2-4c48-8cae-86441238e859)

</p>
<p>
Next, I setted up a remote desktop for non-administrative users on Client-1.To watch me do this step by step, watch the youtube video linked above. The timestamps are from 31:25 to 32:50.
</p>
<br />

![Step 11](https://github.com/BenW618/configure-ad/assets/140227052/3f1d318e-e869-4f3d-83b1-8326d41d5275)

</p>
<p>
Lastly, I created a bunch of additional users and logged into the Client-1 virtual machine with one of the users through powershell. To watch me do this step by step, watch the youtube video linked above. The timestamps are from 32:50 to the end of the video
</p>
<br />
