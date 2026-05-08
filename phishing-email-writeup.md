# phishing-email-writeup

## Overview

In this investigation, I analyzed a phishing email pretending to be from Netflix saying the account was on hold and needed updated payment information. Right away the sender address looked suspicious and the email was trying to create urgency to make the user click the “Update Account Now” button. I used ANY.RUN and VirusTotal to investigate the attachment and observe the activity that happened after the file was opened.

## Suspicious Email

<img width="946" height="892" alt="Screenshot 2026-05-08 000457" src="https://github.com/user-attachments/assets/98b538b8-bafd-4e66-a91b-b890e5af845d" />

## Source Message Analysis

After reviewing the email, I checked the source message to investigate where the email came from and look for more phishing indicators. The source message showed a suspicious domain, the originating IP address, which helped confirm the email was likely fake.

<img width="723" height="183" alt="Screenshot 2026-05-07 235010" src="https://github.com/user-attachments/assets/3f869945-4313-43c4-9b8b-80286782c6c5" />

## Attachment Investigation

After checking the attachment in ANY.RUN, I found the PDF file name along with the MD5 hash value. I then used the MD5 hash on VirusTotal later on to gather more information about the file and check if security vendors detected it as malicious.

<img width="1919" height="971" alt="susEmailEX2" src="https://github.com/user-attachments/assets/43111c42-21ae-4e22-a92e-fd62d9b4e616" />
<img width="517" height="112" alt="susemailEX3" src="https://github.com/user-attachments/assets/d3938c2e-5f59-4e4d-9cea-e5e09ce8d141" />

## Connections and Process Activity

Next, I checked the connections and Windows processes created after the attachment was opened. Most of the connections were marked as whitelisted, meaning they were likely normal system or application activity, but one connection was flagged as malicious. I also found a Windows process marked as “Potentially Bad Traffic” which showed suspicious network activity happening after the PDF was opened.

<img width="1110" height="538" alt="ex4" src="https://github.com/user-attachments/assets/ee9012dc-5de3-4f25-898d-4a295bf69fb4" />
<img width="1098" height="168" alt="ex5" src="https://github.com/user-attachments/assets/cff7f822-42c1-489d-a5c5-daefedb7f810" />

## Hash Investigation

After getting the MD5 hash from ANY.RUN, I searched the file hash on VirusTotal to gather more information about the attachment. VirusTotal showed the SHA256 hash along with multiple security vendors detecting the PDF file as malicious.

<img width="1885" height="842" alt="Screenshot 2026-05-07 234715" src="https://github.com/user-attachments/assets/eacfe044-dfa6-4282-8a42-c3976c914285" />
<img width="1884" height="959" alt="Screenshot 2026-05-07 234735" src="https://github.com/user-attachments/assets/2348ff0b-3674-4043-b48a-fb0710934178" />

## Conclusion

In this write-up, I investigated a phishing email pretending to be from Netflix along with the PDF attachment connected to it. I used the source message, ANY.RUN, and VirusTotal to look into the email, attachment hashes, connections, and Windows processes. During the investigation, I found multiple phishing indicators including suspicious domains, malicious detections, and suspicious network connections. This helped me better understand what can happen on a system after a phishing attachment is opened.
