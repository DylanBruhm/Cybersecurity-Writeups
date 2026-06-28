# WireShark

## Overview
In this challenge you got to navigate wireshark to anwer the questions

## Question 1

<img width="808" height="224" alt="Screenshot 2026-06-25 171640" src="https://github.com/user-attachments/assets/4b852dc8-0b2a-468a-a940-337de22d84c4" />

## Step 1 find the the Treat actor 
first I filtered arp requests to see if i could see any anomalies

<img width="1878" height="841" alt="Screenshot 2026-06-25 170048" src="https://github.com/user-attachments/assets/a06f7eb1-418a-42c1-86bf-3cdf8c7f93a0" />

then we find the mac address
<img width="1912" height="396" alt="Screenshot 2026-06-25 171237" src="https://github.com/user-attachments/assets/b384ed3e-5a78-4aac-aa40-3a6c359a5d66" />
then we filter 
arp.opcode == 1 && arp.src.hw_mac == 00:0c:29:e2:18:b4

arp.opcode == 1 → Only ARP requests.
arp.src.hw_mac == 00:0c:29:e2:18:b4 → Only requests sent by that MAC address.
