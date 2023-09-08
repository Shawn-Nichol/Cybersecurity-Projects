<H2>Virtual Box install</H2>

Down load the lastest version of the OVA file from [Wazuh](https://documentation.wazuh.com/current/deployment-options/virtual-machine/virtual-machine.html)
![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/1a46aca5-a16f-4403-81e9-5073dd0c8156)


Compare the file hash to the one posted [here](https://packages.wazuh.com/4.x/checksums/wazuh/4.5.2/wazuh-4.5.2.ova.sha512). This can be done with powershell. 
```
# Known SHA-512 hash
$knownHash = "8b3f8da204879d66435ab02f675f4e2a92feef1f476547e7f5b5f0378e13f89dcc6d9961ba94469957b02047bce455e937c135320f1a2212a45bea6255094b99"

# Specify the file path
$filePath = "C:\Users\Shawn\Downloads\wazuh-4.5.2.ova"

# Calculate the SHA-512 hash of the file
$hash = Get-FileHash -Algorithm SHA512 -Path $filePath

# Compare the calculated hash with the known hash
if ($hash.Hash -eq $knownHash) {
    Write-Host "File is valid. The SHA-512 hash matches the known hash."
} else {
    Write-Host "File is not valid. The SHA-512 hash does not match the known hash."
}
```
After the integrity of the file has been confirmed, we'll proceed to install Wazuh on a virtual box instance. 
- File, select Import Appliance
- Select OVA that was recently downloaded.
  
![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/8b36b057-bf43-4c4a-9d99-bace68f8be8b)

- Appliance setting can be left as default. 

![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/e507802e-ff1a-4ca3-a48d-d8e8935f7722)

- Wait for the appliance to finish importing

![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/181f2068-ed03-485d-8fd9-10ae0ebbfca4)

<H2>Start The Wazuh SIEM </H2>


![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/f3ecc96a-9636-4bb6-8d66-3136afc83231)

Here you will be prompted by wazuh-server login. 
Default User: Wazuh-User
Default Password: wazuh

![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/853bd9ac-27c8-499e-bc8e-04b9de04bf91)

To get the IP of the server type 
```
ip a
```
<H2>Access the Wazuh Dashboard</H2>
URL: https://wazuh-server IP
user: admin
Password: admin

