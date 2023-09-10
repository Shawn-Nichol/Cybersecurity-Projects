<H2>Windows Agent</H2>

To deploy Agents on a Windows computer, you'll need to select the Agents option in the drop-down menu next to Wazuh. 
![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/47f7c0b2-4d92-42a1-8e63-5357ddbf70c5)

Next, select Deploy agent. </br>
![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/f5a688be-e3a7-40ec-bea1-414f9166a29f)

Select the following settings
1. OS, in this case, windows
2. Version number
3. Architecture, for windows (i386/x86_64 is the only option). </br>
![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/46d3be62-4107-4572-ab4b-0f3c324373a5)

4. Enter the IP address or FQDN
  
5.  Assign Agent name and group. </br>
![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/178e9a80-a8fe-4752-ae44-d3bf82aff94b)

6.  Install and Deploy agent
Copy the generated code and run it in Powershell as administrator. </br>
![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/5daa0a65-f7ee-4777-b2b4-014c77750c9c)

7. Start Agent
```
NET START WazuhSvc
```
