<h1> Exploring DNS </h1>
<h2> Environment and Technology </h2>. 

- Microsoft Azure
- Command Line

<h2> Operating Systems
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

6. Within Client-1, ping mainfram again. Observe that the successful ping.
<p align="center">
<img src="https://i.imgur.com/sE3dWZh.png" height="50%" width="50%" alt="Ping mainframe success"/>

7. Within DC-1, change mainframe's record address to 8.8.8.8.  
<p align="center">
<img src="https://i.imgur.com/YspOTmw.png" height="50%" width="50%" alt="Changing mainframe A-record"/>. 

8. Within Client-1, ping mainframe again. Observe the success ping, but at the previous IP adress for mainframe. 
<p align="center">
<img src="https://i.imgur.com/GFBA1ok.png" height="50%" width="50%" alt="Unexpected ping mainframe success"/>. 



