# SOC Alert Investigations

## Overview 

This repository contains 4 SOC alert investigations I completed during cybersecurity training. Each case includes the investigation process, evidence, findings, and recommendations. These write-ups show how I analyze alerts, identify threats, and document the results.

# Case 1 – Phishing Email
The first alert was a suspicious email claiming an Amazon package couldn't be delivered. The investigation focused on determining whether it was a legitimate email or a phishing attempt, and whether anyone clicked the external link.

<img width="1897" height="971" alt="Screenshot 2026-06-10 175105" src="https://github.com/user-attachments/assets/9211d393-c4e1-4328-aed4-0617e0fe019d" />

## Step 1 – Verify the Link
The first step was verifying the URL in TryDetectThis to see if it was a known malicious link. The results confirmed the URL was malicious, supporting the suspicion that the email was a phishing attempt.

<img width="1888" height="942" alt="Screenshot 2026-06-10 181927" src="https://github.com/user-attachments/assets/55bc6fe7-3b18-44c5-9758-43e6082c9d46" />

## Step 2 – Search for Similar Emails
Next, I searched Splunk for the sender email address urgents[@]amazon[.]biz to determine if any other emails had been sent from the same sender. The search returned only one matching event, indicating no additional emails from this sender were found in the environment.

<img width="1912" height="867" alt="Screenshot 2026-06-10 183717" src="https://github.com/user-attachments/assets/ce4d8cc7-8f23-41ad-a789-8a32b9944e5a" />

## Step 3 – Check Firewall Logs
Next, I searched Splunk for the URL to see if there were any firewall events related to the link. The search returned one result showing the connection was blocked by the firewall, preventing access to the malicious URL.

<img width="1911" height="997" alt="Screenshot 2026-06-10 183952" src="https://github.com/user-attachments/assets/81711514-6a32-4cdb-a948-502825108583" />

## Final Report
Alert Type: Phishing Email

Time of Activity:
- 06/10/2026 21:48:12 – The phishing email was received by h.harris[@]thetrydaily[.]thm.
- 06/10/2026 21:49:26 – A connection attempt to the malicious URL was detected and blocked by the firewall.

Affected User:
- h.harris[@]thetrydaily[.]thm
- Affected Host: 10.20.2.25

Reason for Classifying as True Positive: 
- The email was confirmed to be a phishing attempt after the URL was identified as malicious using TryDetectThis. Firewall logs also showed a connection attempt to the URL, confirming the email was interacted with.

Reason for Escalating the Alert: 
- Although the firewall blocked the connection, the alert was escalated to verify the affected host and confirm no files were downloaded or other suspicious activity occurred.

Recommended Actions:
- Escalate the alert for a follow-up investigation.
- Check the affected host to make sure no files were downloaded or malicious activity occurred.
- Remove the phishing email from the user's mailbox.
- Continue monitoring for any related activity.

List of Attack Indicators:
- Sender: urgents[@]amazon[.]biz
- Subject: Your Amazon Package Couldn't Be Delivered – Action Required
- Malicious URL: hxxp://bit[.]ly/3sHkX3da12340
- Destination IP: 45.148.10.131

