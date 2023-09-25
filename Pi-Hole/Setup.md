Download Rasberry PI OS, and configure on memory card. 


## Change name
You'll need to change the hostname into two file locations
The first location is here. After open the file set the name of the Pi
```
sudo nano /etc/hostname
```
The second location is here. The host name will be to the right of the local address. 
```
sudo nano /etc/hosts
```

Reboot the Pi
```
reboot
```


## Enable SSH 
- Click on Start menu
- Preferences
- Interfaceds and Toggle SSH. </br>
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/8858594f-8f2a-455f-82ee-8647e8850799)



## PI Hole install
Run the following command in the terminal. This will install Pi-Hole and prompt you for settings following the instructions here as it is straightforward. 

```
curl -sSL https://install.pi-hole.net | bash
```
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/9a5d9996-f909-4020-b4b5-bdab7b322d9e)


## Configure Pi-Hole
Reconfigure Pi-Hole </br> 
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/ce57168c-ee77-498a-8c15-b31ac77af681)


A warning will pop up telling you to configure a static IP. </br>
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/97a47db2-2cfb-41fa-8e94-41fa25efc409)

Select the interface that you want to configure with a static IP address. </br>
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/7559c634-4598-4669-b8f8-6dd9670a3af4)

Set Static IP </br>
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/cdd3166d-7dc1-42a2-b906-e1c9d3e792f6)

Select Upstream DNS provider </br>
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/2636c94a-1b8e-4929-8516-607122039f6e)

Select third-party lists and add blocker lists</br.
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/e497875d-8b01-4611-83d0-d5c106780865)

Enable Admin web interface
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/3fc02095-38f0-4e69-9e19-08033e4202d5)

Install lighttp and PHP modules
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/29095926-afc3-400d-a72f-5c9ac6bcec9e)

Enable query logging
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/778f3fd4-685f-4bf7-838c-4993d34cc615)

Privacy mode, I recommend the Anonymous mode
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/4b20b6fb-aecc-4485-a502-0b7e20680f4d)

Setup finished not the password that is given to you
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/bdcf72e8-dc98-4139-a98c-c2318fcd5f1d)

## Web page
To navigate to the web page
HTTP:\\ip-addres\admin
Enter the password that you received at the end of the install. 

![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/cc41119e-6c83-476f-933a-5f42a7069751)

Update lists
in the terminal, run the following command to update the available lists
```
pihole -g
```
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/05a52c74-bf0f-4f19-840d-56d4dead09cf)


Adding lists
[The Firebog](https://firebog.net/) is the number one voted site for lists by Reddit users; you select from Suspicious lists, Adverting lists, Tracking and telemetry Lits, and Malicious lists.
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/0c43e8a3-b7b6-4e55-8108-e2347aeb4735)

Click on a list you want to add to your Pi-Hole, and copy the link, then you'll add the list in the Pi-Hole add list page. 
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/95f51660-9aa7-4db7-bca0-e91a502d30b8)


## Configure Router
Next, you'll need to set the Pihole as the active DNS server through your router.

Select a list
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/920e72e1-5f27-4b05-a754-8b6c6e8b0863)


## Manually set the IP address
It's best to set a static IP for this device, 

Activate DHCPCD
```
sudo service dhcpcd start
sudo systemctl enable dhcpcd
```

Next, edit the DHCPCD configuration file; you'll want to move the hashtag at the start of the line as it memos the line. 
```
sudo nano /etc/dhcpcd.conf
```

![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/3ddf3ee5-9226-42af-b3d8-02d41b14d09d)

