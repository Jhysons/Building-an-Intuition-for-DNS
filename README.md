<p align="center">
<img src="https://i.imgur.com/djPE5Mq.png" alt="osTicket logo"/>
</p>

<h1>Building-an-Intuition-for-DNS</h1>
This tutorial outlines The Domain Name System (DNS) protocol is an important part of the web's infrastructure.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>DNS Tutorial Stages</h2>

- Ping Mainframe
- Nslookup Mainframe
- Change Record Address

<h2>Stages</h2>

<p>
<img src="https://i.imgur.com/f081WGM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Turn on VMs: Ensure both DC-1 and Client-1 VMs are powered on in the Azure Portal.
Log into DC-1: Connect to DC-1 using your domain admin account.
Log into Client-1: Connect to Client-1 using an admin account.
Ping Mainframe: From Client-1, open Command Prompt and try to ping "mainframe". You'll notice it fails because there's no DNS record for "mainframe".
Nslookup Mainframe: Use the nslookup command to query "mainframe" and observe that it fails due to the absence of a DNS record.
Create A-Record: On DC-1, open the DNS Manager and create an A-record for "mainframe" pointing to DC-1's Private IP address.
Ping Mainframe Again: Return to Client-1 and ping "mainframe" again. This time, it should succeed because the DNS record now exists.
</p>
<br />

<p>
<img src="https://i.imgur.com/ha1v9AR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Change Record Address: On DC-1, modify the "mainframe" A-record to point to 8.8.8.8.
Ping Mainframe: From Client-1, ping "mainframe" again. You'll notice it still pings the old address because of the local DNS cache.
Display DNS Cache: On Client-1, use the ipconfig /displaydns command to display the local DNS cache and observe the cached entry for "mainframe".
</p>
<br />

<p>
<img src="https://i.imgur.com/yhgDpsl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Flush DNS Cache: Clear the local DNS cache using the ipconfig /flushdns command.
Display DNS Cache Again: Verify the cache is empty by running ipconfig /displaydns again.
Ping Mainframe Again: Ping "mainframe" once more and observe that it now resolves to the new address (8.8.8.8).
</p>
<br />
