# Virtual-Network-Peering
In this project, my goal was to pair two virtual networks within the same region, ensuring they were connected and that resources could communicate with each other.  
<h2>Environments Used </h2>

- <b>Azure Portal</b>
- <b>CLI</b> 


<h2>Project walk-through:</h2>

<p align="center">
I already have a virtual network named Vnet1 which I planned to peer with a new virtual network named vnet2 that I needed to create. <br/>
<br />
I started the creation of vnet2 using the CLI and made sure that the IP address space did not overlap with Vnet1’s: <br/>
<img src="https://i.imgur.com/kzs2Bah.png" height="80%" width="80%" />
<br />
<br />
<br />
I then verified the creation of vnet2 in the portal:  <br/>
<img src="https://i.imgur.com/QEgRwXY.png" height="80%" width="80%" />
<br />
<br />
<br />
I then started the creation of a virtual machine (vm3) within the virtual network (vn2) using the CLI:  <br/>
 <img src="https://i.imgur.com/1KWYyzY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
I then confirmed the creation of vm3 in the portal:  <br/>
<img src="https://i.imgur.com/qB74Ls6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br /> 
the next step was peering the virtual networks. in the portal, I went to vnet 2 and created a peering between vnet2 and Vnet1:  <br/>
<img src="https://i.imgur.com/GPJJauU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
I named the peering MainVnetPeering and the peering link name Vnet1-to-vnet2. I selected both “Allow 'vnet2' to access 'Vnet1’” and “Allow 'Vnet1' to access 'vnet2’”:  <br/>
<img src="https://i.imgur.com/3h5kXG0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 
<br />
I then made sure the peering status was connected:  <br/>
<img src="https://i.imgur.com/L1XXIJE.pngg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 
<br />
Once the peering was complete I connected to vm3 in the portal via native RDP and followed the prompts:  <br/>
<img src="https://i.imgur.com/UPOVhXm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/SFMVGJB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Y6sWJUQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/WYoRElk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 
<br />
Once i was connected to vm3 i pinged VM1  which is hosted within vnet1 using its private IP address, which was 10.1.0.4:  <br/>
<img src="https://i.imgur.com/pdMDtzE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 
<br />
After pinging VM1 from vm3 I attempted to connect to VM1 from vm3 by running the following command mstsc /v:10.1.0.4:  <br/>
<img src="https://i.imgur.com/fckN7BB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 
<br />
The connection was successful, so then I filled in VM1 credentials and followed the prompts:  <br/>
<img src="https://i.imgur.com/ZgqmR4h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/QeQrKMA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 
<br />
I successfully connected to VM1 from vm3 and reached the Goal of this project:  <br/>
<img src="https://i.imgur.com/gSq6003.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
