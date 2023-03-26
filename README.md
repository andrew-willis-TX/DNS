<h1> Exploring DNS </h1>
In this lab exercise we explore various properties of DNS and DNS records. We will be using A-records and CNAME records. Both of these records are helpful for our machines to navigate the internet properly and organize various domains. A-records can map domain names to IP address while CNAME records can map together two different domain names. This is helpful for a site that has several different domains to create subdomains. 

<h2> Environment and Technology </h2> 

- Microsoft Azure
- Command Line

<h2> Operating Systems</h2> 

- Windows Server 2022
- Windows 10 Pro 

<h2> Prerequisites </h2> 
  
- Domain Controller
- Administrative User
- Domain Network
- Client Machine

<h2> Steps to Exploring DNS </h2>

1. Log in to DC-1 as the Adminstrative User.   

<p align="center">
<img src="https://i.imgur.com/LgmvAIs.png" height="50%" width="50%" alt="Login in to DC-1"/>
</p>

2. Log in to Client-1 as the Administrative User. 

<p align="center">
<img src="https://i.imgur.com/utCOYwx.png" height="50%" width="50%" alt="Log in to Client-1"/>

3. Within Client-1, ping the mainframe. Observe the ping failure. 
<p align="center">
<img src="https://i.imgur.com/4dICE57.png" height="50%" width="50%" alt="Ping mainframe failure."/>   

4. Within Client-1, open the command line ad enter the command "nslookup". Observe the lookup failure.  
<p align="center"> 
<img src="https://i.imgur.com/YjABOvk.png" height="50%" width="50%" alt="Lookup failure"/>

5. Within DC-1, create a DNS A-record for mainframe and have it point to DC-1's private IP address.  
<p align="center">
<img src="https://i.imgur.com/BS8mWb2.png" height="50%" width="50%" alt="Adding mainframe A-record"/>

6. Within Client-1, ping mainfram again. Observe the successful ping.
<p align="center">
<img src="https://i.imgur.com/sE3dWZh.png" height="50%" width="50%" alt="Ping mainframe success"/>

7. Within DC-1, change mainframe's record address to 8.8.8.8.  
<p align="center">
<img src="https://i.imgur.com/YspOTmw.png" height="50%" width="50%" alt="Changing mainframe A-record"/>. 

8. Within Client-1, ping mainframe again. Observe the success ping, but at the previous IP adress for mainframe. 
<p align="center">
<img src="https://i.imgur.com/GFBA1ok.png" height="50%" width="50%" alt="Unexpected ping mainframe success"/>.  

9. within Client-1, observe the local DNS cache using "ipconfig /displaydns". Observe the A-record with the previous mainframe IP address. 
<p align="center">
<img src="https://i.imgur.com/F7DM5BI.png" height="50%" width="50%" alt="Display DNS results show previous mainframe IP Address"/>

10. Within Client-1, run the command line as an Administrator. Flush the DNS cache using the command "ipconfig /flushdns".
<p align="center">
<img src="https://i.imgur.com/WZYRuZB.png" height="50%" width="50%" alt="Flushing the DNS cahce"/>

11. Attempt to ping the mainframe again. Observe the A-record is updated to the new IP Address. 
<p align="center">
<img src="https://i.imgur.com/QmgpMVM.png" height="50%" width="50%" alt="Observe the updated A-record"/>

12. Within DC-1, create a CNAME record that points any host "search" to google.com. 
<p align="center">
<img src="https://i.imgur.com/xyTXfOS.png" height="50%" width="50%" alt="Creating a new CNAME record"/>

13. Within Client-1, ping search and observe the results of the CNAME record.  
<p align="center">
<img src="https://i.imgur.com/PMO2vq5.png" height="50%" width="50%" alt="Observe the results of the new CNAME record"/>

14. Within Client-1, use the command "ipconfig /displaydns". Observe the result of the CNAME search. 
<p align="center">
<img src="https://i.imgur.com/ZxrtGRC.png" height="50%" width="50%" alt="Displaydns results"/>






