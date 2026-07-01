# WireShark

## Overview
In this challenge, I used Wireshark to investigate an ARP spoofing attack and identify the attacker's activity by filtering network traffic and analyzing ARP packets.

## Question 1

<img width="808" height="224" alt="Screenshot 2026-06-25 171640" src="https://github.com/user-attachments/assets/4b852dc8-0b2a-468a-a940-337de22d84c4" />

## Step 1 find the the Treat actor 
first I filtered arp requests to see if i could see any anomalies,
This let me view only Address Resolution Protocol packets and look for unusual activity.

<img width="1878" height="841" alt="Screenshot 2026-06-25 170048" src="https://github.com/user-attachments/assets/a06f7eb1-418a-42c1-86bf-3cdf8c7f93a0" />

I noticed one MAC address was sending a large number of ARP requests to many different IP addresses on the network.

<img width="1912" height="396" alt="Screenshot 2026-06-25 171237" src="https://github.com/user-attachments/assets/b384ed3e-5a78-4aac-aa40-3a6c359a5d66" />

I then filtered the traffic to show only ARP requests from that MAC address.

arp.opcode == 1 && arp.src.hw_mac == 00:0c:29:e2:18:b4

arp.opcode == 1 Shows only ARP request packets.

arp.src.hw_mac == 00:0c:29:e2:18:b4  Shows only packets sent by that MAC address.

<img width="1915" height="949" alt="Screenshot 2026-06-25 171619" src="https://github.com/user-attachments/assets/7cec9d9d-c5c0-4918-af3c-0f2ee6a2d3d5" />

and then we can see in the bottom right under packets displayed 284 giving us the answer to the first question. 

## question 2
<img width="796" height="160" alt="Screenshot 2026-06-26 111225" src="https://github.com/user-attachments/assets/ff057e94-e049-420f-9fae-daa1cab419e3" />
