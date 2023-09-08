##Integrity Monitoring Module
The Integrity Monitoring module monitors all important files and registry keys to help identify suspicious behavior.

![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/ad314cdf-9657-4c52-8a6d-2f80157c2137)

1. Edit the `ossec.conf` file, which can be found on the agent's computer in the following directory: `C:\Program Files (x86)\ossec-agent`.

2. Scroll down to the section labeled "32-bit programs."

![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/93a2f4ee-b73a-4d74-ab79-1e6007585b2a)

3. To monitor the integrity of a folder, add a new directory with the following parameters:
- reatime="yes"
- report_changes="yes"
- check_all="yes"
Close out the directory and add the path to the folder you want to monitor. 
```
<directories realtime="yes" report_changes="yes" check_all="yes">C:\Users\Shawn\Documents</directories>
```
Save the file and restart the wazuh service.
```
restart-service -name wazuh
```

Add a text file to the folder, and you'll notice a new entry in the events. 

![image](https://github.com/Shawn-Nichol/Wazuh/assets/30714313/8f634ff5-9bf7-4dc9-9cb5-af8bb7cb3447)
