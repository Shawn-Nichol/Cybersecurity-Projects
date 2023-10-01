## Step 1 Install OpenVAS on Kali Linux ##
First, update your operating system to ensure you have the latest packages.
```
sudo apt update && sudo apt upgrade -y
```

Next, install OpenVAS. Please note that this step might take some time.
```
sudo apt isntall openvas
```

After installation, set up GVM by running the following command:
```
sudo gvm-setup
```

If you encounter a PostgreSQL error, follow these steps to resolve it:
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/fc58b412-a095-40c0-b7aa-f6ce147ea506)

1. Check what version of postgresql you are running
 ```
   ls /etc/postgresql/
 ```
  ![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/a63a59c4-ca76-4ae2-9d3a-9a67910fbea1)

2. Remove the unwanted PostgreSQL version (replace '15' with the version number you want to remove):
 ```
  sudo  /usr/bin/pg_dropcluster --stop 15 main 
```
3. Verify that the unwanted PostGreSQL cversion ahs been removed
  ls /etc/postgresql/
 ```
  ![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/6e4e7097-0c0c-4b6c-875b-ce8d4132bed1)
```

Once resolved, run the setup command again. Please be aware that this process may take a couple of hours to complete:
```
sudo gvm-setup
```
</br>
![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/06dd9bbf-b826-4206-afc0-c2af25f311ed)

Upon completion, you will receive an admin password.




## Step 2 Configuring OpenVAS
Verify that the installation is working properly by running:
```
sudo gvm-check-setup
```

Start GVM
```
sudo gvm-start
```

You can now access the OpenVAS web interface using a web browser at the following address: https://localhost:9392/login

![image](https://github.com/Shawn-Nichol/Cybersecurity-Projects/assets/30714313/2b30ae6f-b279-43d4-ad17-4c2ef1466d81)


**Change password**
To change your password, follow these steps:

1. Navigate to User Profile > My Settings.
2. Click on Edit.
3. Change the password as desired.
Now, your OpenVAS installation is set up and configured, and you can use the web interface to manage your security scans.












