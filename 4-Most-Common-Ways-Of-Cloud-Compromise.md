<img width="431" alt="Screenshot 2024-01-26 at 11 56 32 PM" src="https://github.com/redskycyber/Cloud-Security/assets/157662722/f4e8bef4-ff4f-4567-b63f-f4bd5177b120">

Below is my summary of the 4 most common ways that Cloud environments are compromised:

# 1. Exposed Keys/Secrets/Credentials:
Keys, secrets, and credentials serve as authentication methods for the cloud admin console. Similar to poor password practices, these keys/secrets/credentials are frequently abandoned or leaked in source code,  repositories, and exposed to the public. Threat actors utilize scrapers to actively monitor the web for known key, secret, and credential formats, gobbling them up even if exposed for just a moment. 
Ex. [Tool + Search Query] https://grep.app/search?q=aws_secret

# 2. Public-facing, Unauthenticated Access to Data:
Some of the most significant data leaks in cloud history involve publicly accessible S3 storage buckets or storage blobs that were inadvertently misconfigured to allow read access from the public internet. While buckets were public by default in the early days of the cloud, the ongoing threat of data exposure persists due to the complexities of cloud configuration or engineers negligently opening permissions. 
Ex. [Tool] https://github.com/sa7mon/S3Scanner

# 3. Compromised Infrastructure Leading to Key/Secrets/Credentials:
When infrastructure within a cloud environment is compromised, threat actors often perform enumeration as part of their methodology to discover additional information. Frequently, due to poor security practices, keys, secrets, and credentials are left unprotected, providing a direct pathway into admin console authentication. One example, in the case of Server-Side Request Forgery (SSRF), attackers manipulate requests sent by the server to access unauthorized information or services hosted on metadata endpoints. https://book.hacktricks.xyz/pentesting-web/ssrf-server-side-request-forgery/cloud-ssrf

# 4. Overly Permissive Accounts:
Finally, once a credential set is compromised for cloud access, Identity and Access Management (IAM) is often misconfigured or provides excessive permissions, making further exploitation trivial. Gaining full control of a cloud environment becomes effortless when wildcard (*) permissions are implemented, the principle of least privilege is not enforced, and when policies are not granularly defined. Examples of IAM Privilege Escalation: https://cloud.hacktricks.xyz/pentesting-cloud/aws-security/aws-privilege-escalation/aws-iam-privesc

For those looking for a better understanding of successful hacks in Cloud environments, check out this amazing free repository of headline AWS breaches and their root causes, which has helped me become a stronger practitioner:

https://github.com/ramimac/aws-customer-security-incidents
Repo by Rami McCarthy

Reading through the articles in this repository was one of the first steps I took on my offensive security journey to understand what to look for during Cloud Penetration Testing.
