# SOC Level 1 Write-Up

## Overview
Investigated suspicious SSH login attempts through a SIEM dashboard simulation on TryHackMe.

## Findings
Detected repeated SSH login attempts targeting port 22 from a suspicious external IP address. 
Investigated the IP address and there is known suspicious activity, originating from an external IP located in China.
Escalated the incident to the SOC team lead and blocked the IP address on the firewall for repeated SSH login attempts and known malicious activity.
<img width="978" height="936" alt="SusSSHLoginEx" src="https://github.com/user-attachments/assets/435ea289-1983-4c6f-9e77-28e91d49d866" />

<img width="1003" height="947" alt="IPSearch" src="https://github.com/user-attachments/assets/9fcc2bef-9631-4a2d-a18e-ab8424ca28a1" />


<img width="988" height="820" alt="blockedFirewall" src="https://github.com/user-attachments/assets/9c76edda-2d9a-447f-83ce-57b19ee4d9a1" />
