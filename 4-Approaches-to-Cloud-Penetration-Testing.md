# 4 Approaches to Cloud Penetration Testing
There are 4 types of cloud penetration tests you can perform, each providing different results and impact. Understanding them can assist you in better scoping your cloud penetration test to meet stakeholder requirements. What are the pros and cons of each?

## 1. Unauthenticated External Penetration Test

**Starting Point:** External threat actor with unauthenticated Internet access.

This assessment mirrors an external network penetration test but is tailored to assets and services hosted on the Cloud. The engagement starts without any credentials or keys for the Cloud environment. The primary objective is to assess the external presence, uncover vulnerabilities, and actively exploit them to demonstrate the potential consequences of an unauthenticated threat actor. A top priority is gaining access to the Cloud environment, either through the discovery of Cloud credentials or by compromising an external host or service.

**Pros:** \
[+] Most common cloud targeting scenario, as most threat actors will start from this same perspective. \
[+] Least prerequisites required. \
[+] Lowest cost. 

**Potential Drawbacks:** \
[-] May not result in cloud user, network, or console compromise, leaving credentialed access to the environment un-assessed. 

## 2. Uncredentialed Internal Network Assumed Breach Penetration Test (device compromise, no additional access provided)
*Worth defining, but not the recommended approach, as there is far more to cloud infrastructure than just the network portion.*

**Starting Point Assumed Role:** Internal network device without credentials.

In this scenario, a virtual machine is provisioned within the Cloud environment, with VNet or VPC access to other servers, workstations, or databases in scope, where testers can remotely access. Similar to an internal penetration test, exposed ports and services are mapped across live devices, and vulnerabilities are identified and exploited to prove impact.

This approach can be performed, but it resembles a traditional penetration test. It doesn’t include access to the management console, unless that access is discovered during the assessment - so the next approaches are definitely more thorough and recommended. If someone asks for this approach, respectfully guide them to the more impactful approaches of #3 or #4.

**Pros:** \
[+] The internal cloud network is assessed for vulnerabilities. 

**Potential Drawbacks:** \
[-] This assessment derives from a traditional Internal Network Penetration test methodology and focuses only on a portion of cloud infrastructure and that is the internal cloud network. \
[-] The more realistic and thorough attack scenario of credentialed console compromise will be left unassessed if not discovered.

## 3. Credentialed Console Assumed Breach Penetration Test (user management and CLI programmatic access to the Cloud console)
**Starting Point Assumed Role:** Starting from the perspective of an internal employee or cloud engineer with developer credentials, or from that of a service account, this scenario reflects a situation in which these credentials were externally exposed or compromised.

These credentials are leveraged to probe the Cloud environment from an external attack location, seeking vulnerabilities, a foothold on a system, privilege escalation opportunities, and lateral movement pathways.  By identifying, linking, and exploiting these vulnerabilities, the objective is to illustrate the extent of the compromise's impact on the environment. This assessment moves beyond the external perspective, to assess cloud specific services and their integrations.

**Pros:** \
[+] Identifies and exploits vulnerabilities within the Cloud environment. \
[+] Most common breach scenario of a user’s or service’s Cloud credentials.

**Potential Drawbacks:** \
[-] May not result in compromise of a network connected asset in the cloud, leaving the network and VM portions of the environment only assessed from the admin console. \
[-] You may be limited based on what roles are provided in the assumed breach. This is only a drawback if the conversation is not had with a stakeholder, and adequate permissions are not provided. 

A recommended approach is looking at the overall composition of users within the cloud environment, and choosing roles and permissions that are most prevalent, or most likely to become compromised.

## 4. Credentialed Internal Network and Console Assumed Breach Penetration Test  (Internal device compromised, user credentials provided)
Starting Point Assumed role:  Internal Employee - Infrastructure or Application User, equipped with internal device access (VM, VDI, or EC2 Instance) and Cloud credentials, this scenario elevates the “traditional” penetration test in approach #2 to a more comprehensive level.

This is the most exhaustive among the Assumed Breach types, as it not only establishes a starting point within the cloud network but also provides user credentials. These credentials can serve as a pivot to access the Cloud console and explore other potential areas of compromise, including Cloud services.

In this scenario, a standard virtual machine is provisioned within the Cloud environment, accompanied by Cloud keys that align with the designated user's typical access level. These keys can be utilized through the Cloud CLI or management console.

In real-world compromise scenarios, this particular situation is highly prevalent when a server, web application, or external asset situated on an organization's perimeter falls victim to a breach. This scenario operates on the assumption that such a compromise has occurred and aims to illustrate the consequences of exploiting vulnerabilities from this compromised entry point where credentials are obtained.

**Pros:** \
[+] Recommended Approach for most realism and impact. \
[+] Covers network and console service exploitation. \
[+] Most thorough coverage. \
[+] Discovers internal vulnerabilities and exploitation paths to help proactively mitigate.

**Potential Drawbacks:** \
[-] This is the most resource intensive cloud assessment that requires the most prerequisites and the most time to perform. 
