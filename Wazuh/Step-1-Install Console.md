# Wazuh Console Install on Virtual Box

![VirtualBox](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/1a46aca5-a16f-4403-81e9-5073dd0c8156)

## Download the Wazuh Virtual Machine

Before installing Wazuh on VirtualBox, download the Virtual Machine (OVA) file from the official website. Make sure to compare the file hash to ensure its integrity.

1. [Download the OVA file](https://documentation.wazuh.com/current/deployment-options/virtual-machine/virtual-machine.html):
2. Calculate the SHA-512 hash of the downloaded file using PowerShell (optional but recommended):

   ```PowerShell
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

## Import the Wazuh Virtual Machine

After confirming the integrity of the OVA file, you can proceed to install Wazuh on a VirtualBox instance:

1. Open VirtualBox.

2. Click "File" in VirtualBox and select "Import Appliance."

3. Choose the OVA file you downloaded.

![VirtualBox Import](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/8b36b057-bf43-4c4a-9d99-bace68f8be8b)

4. Leave the appliance settings as default.

![Appliance Settings](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/e507802e-ff1a-4ca3-a48d-d8e8935f7722)

5. Wait for the appliance to finish importing.

![Import Progress](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/181f2068-ed03-485d-8fd9-10ae0ebbfca4)

## Start The Wazuh SIEM

A VirtualBox window will open, prompting you to enter the Wazuh server login credentials:

- Default User: Wazuh-User
- Default Password: wazuh

Note: Changing the default username and password after the initial login is advisable for security reasons.

![Wazuh Login](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/853bd9ac-27c8-499e-bc8e-04b9de04bf91)

To find the IP address of the server, use the Wazuh server terminal and run:

```shell
ip a
```

## Access the Wazuh Dashboard

Open a web browser and navigate to the URL: `https://wazuh-server-IP` (replace `wazuh-server-IP` with the IP address you found earlier).

Log in to the Wazuh Dashboard:

- User: admin
- Password: admin

Note: For security purposes, change the default username and password after the initial login.
