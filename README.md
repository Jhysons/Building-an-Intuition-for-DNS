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

- Remote Desktop
- Ping Mainframe
- Nslookup Mainframe
- Change Record Address

<h2>Stages</h2>

<h2>Connect to the Server via Remote Desktop</h2>

<p>

<img src="https://i.imgur.com/gJZx2GQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  
Open Remote Desktop Connection: On your local machine, press Win + R, type mstsc, and press Enter.

Enter the Server's IP Address: In the Remote Desktop Connection window, enter the IP address or hostname of the server you want to connect to and click Connect.

Log In: Enter your credentials to log in to the server.

<img src="https://i.imgur.com/f081WGM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log into DC-1: Use your domain admin account .

Log into Client-1: Use an admin account .

Ping "mainframe" from Client-1: Notice that it fails.

Nslookup "mainframe" from Client-1: Notice that it fails (no DNS record).

Create a DNS A-record on DC-1: Point "mainframe" to DC-1’s Private IP address.

Ping "mainframe" from Client-1 again: Observe that it works.
</p>
<br />

<p>
<img src="https://i.imgur.com/ha1v9AR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Change mainframe’s record address on DC-1: Set it to 8.8.8.8.

Ping "mainframe" from Client-1 again: Observe that it still pings the old address.

Observe the local DNS cache on Client-1: Use ipconfig /displaydns.

Flush the DNS cache on Client-1: Use ipconfig /flushdns.

Observe the empty cache on Client-1: Use ipconfig /displaydns.

Ping "mainframe" from Client-1 again: Observe the new record address showing up.
</p>
<br />

<p>
<img src="https://i.imgur.com/yhgDpsl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a CNAME record on DC-1: Point the host "search" to "www.google.com".

Ping "search" from Client-1: Observe the results of the CNAME record.

Nslookup "search" from Client-1: Observe the results of the CNAME record.
</p>
<br />
