# Windows Agent Deployment Guide

This guide provides step-by-step instructions for deploying the Wazuh Agent on a Windows computer. The Wazuh Agent extends your security monitoring capabilities to Windows environments, helping you detect and respond to security threats effectively. This guide will walk you through the deployment process.

## Prerequisites

Before you begin, make sure you have the following:
- Administrator access on the Windows computer.
- Access to your Wazuh manager.

## Deployment Steps

1. **Access the Wazuh Agents Menu**

   - In your Wazuh manager, navigate to the "Agents" option in the drop-down menu next to Wazuh.

   ![Agents Menu](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/47f7c0b2-4d92-42a1-8e63-5357ddbf70c5)

2. **Select "Deploy Agent"**

   - Click on the "Deploy Agent" option.

   ![Deploy Agent](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/f5a688be-e3a7-40ec-bea1-414f9166a29f)

3. **Configure Agent Settings**

   - In the deployment wizard, configure the following settings:
     - OS: Choose "Windows."
     - Version Number.
     - Architecture: For Windows, select either "i386" or "x86_64."

   ![Agent Settings](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/46d3be62-4107-4572-ab4b-0f3c324373a5)

4. **Enter IP Address or FQDN**

   - Provide the IP address or Fully Qualified Domain Name (FQDN) of the Wazuh console.

5. **Assign Agent Name and Group**

   - Specify a unique Agent name and assign it to a group for better organization.

   ![Agent Name and Group](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/178e9a80-a8fe-4752-ae44-d3bf82aff94b)

6. **Install and Deploy the Agent**

   - Copy the generated code from the deployment wizard and run it in PowerShell as an administrator.

   ![Install Agent](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/5daa0a65-f7ee-4777-b2b4-014c77750c9c)

## Starting the Agent

To start the Wazuh Agent, open PowerShell as an administrator and run the following command:

```powershell
NET START WazuhSvc
```
