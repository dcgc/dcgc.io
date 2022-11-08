---
layout: page
title: Vulnerability Management
categories: notes
permalink: /vm/
---

# Vulnerability Management

![VM](https://dcgc.io/vm.png)

## Definitions

- **Vulnerability**: Flaw or weakness in a system that can be exploited
- **Security** Audit: Assess the adequacy of controls and evaluate compliance
- **Vulnerability** Assessment: Description and analysis of vulnerabilities in a system
- **Red Team**: Team that tests the controls in an environment to identify vulnerabilities
- **Penetration Testing**: Circumvent the security features of a system to demonstrate risk
- **Vulnerability Management**: Ongoing, repeatable processes for identifying, remediating, or accepting risk
- **Risk**: Possibility of loss or injury



## General Purpose Guidelines

- Automated VM Program

- False Positive Reduction (Falses Positives are tuning opportunities)

- False Negative Identification

- We discover vulnerabilities, verify their presence and determine their potential business impact throughout the vulnerability management lifecycle.

- Instead of point solutions and single systems, consider everything at large scale.

- Automation is key.

- Handling risks, presenting ratings, and empowering triage are further concerns central to VM.

- Vunerability Management is an extension of performing Threat Modeling.

- Introduce vulnerability assessment methodology.

- Enterprise class organizations have greater requirements to automate.

- Significantly higher volumes of traffic and transactions per capita than small to mid-size organizations.

- Relatively higher investment and reliance on IT in enterprises.

- Building for resilience

- Logging and active monitoring

- Security, functionality, convenience, performance **[You can only pick 3]**
  
- Documentation is important.

- Writing consistent and coherent policies.

- Implement controls that flow from actual policies.

- Engineering processes that make sense.

- Not impending functionality.

- Getting business requirements.

- Going from individual snapshots to continuous assessment.

- VM needs to be a compelling story that describes a realistic and probable scenario. 

- Enterprises have their own momentum, which can work for or against you. It depends on organizational culture.

- Vulnerability Assessment can include:
  - Checklist
  - Threat Risk Assessment
  - Certification and Accreditation
  - Procedural and Documentation review
  - Personnel Interviews
  - Audit and Compliance validation
  - Configuration review
  - Architectural review
  - Security assessment
  - Pentest


- CSC 4 Continuous Vulnerability Assessment and Remediation

- CIS Critical Controls:
  - Inventory of Authorized and Unauthorized Devices
  - Inventory of Authorized and Unauthorized Software
  - Secure Configurations for Hardware and Software
	- Continuous Vulnerability Assessment and Remediation


- Vulnerability Assessment Framework
  - Examples: NIST, OSSTMM, FISMA/FedRAMP, NERC CIP, PTES, PenTest Framework, ISSAF

VA Methodology steps:
1- Engagement Planning
2- Threat Modeling
3- Discovery
4- Scanning
5- Validation
6- Remediation
7- Reporting

!Last 3 steps can be an iterative loop.
!Report loops back to engagement planning.

- Methodology broken down into modules
- Output from one module is the input to the next module
- Most tools do not follow this methodology precisely.
- For each module or several modules, we need to run several tools.
- Each tool may have a different output format or use a proprietary database.
- Correlation and analysis can be time consuming.


Output from module > database import
Database queries > inputs to next module
Reporting module > ticketing
Tickets > Vulnerability Management and mitigation
Close the loop back to the test team process
Re-test where necessary.


- The key is not running the scanners, but analysis, correlation, documentation and problem solving.
- Organizations can automate security testing and reporting processes, particularly consultants and enterprises.
- The key is analysis and database utilization.
- These can be built with Free/Open Source Software tools and commercial offerings.
- Should be done with proper planning, tools, methodology, processes and expertise.


Step 1: Engagement Planning
Consider: 
	VA and VM on corporate acquisition.
	Rapid implementation of VM program post compromise.
	When the legal team suddenly levies a compliance concern.

Charter & Authority:
	Corporate accounting, Legal, Risk (offices of stakeholders)
Permission & Legal
Resourcing
Scope
Rules of engagement
Project planning
Scanner architecture
Risk acceptance

Step 2: Intelligence and Threat Modelling
	Gathering Intelligence
	Identify and prioritize what are the most likely threats the organization or 			 
  specific assets may face
	Who are the most likely threat sources/actors?
	What are their most likely targets/critical assets/functions?
	What are the most probable and likely to succeed attack vectors?
	How likely are the mitigation controls able to detect/respond?
	Level of sophistication and resourcing required to pull attacks off
	Now you have a threat model, develop a roadmap to mitigate.

Purpose: gathering information on the target organization, typically from the internet
Inputs: organization name, URL, IP addresses or ranges, industry or organization type.
Outputs: URL, IP address ranges, emails, buzz, technologies used, resumes, names, hostnames. E.g., attack trees, MITRE Att&ck Groups.
Data types: free form text, graphics, statistics.

Other sources of intelligence based on industry and nationality. Intelligence should indicate likely threat actors and current attack techniques that are working.


Step 3: Discovery
	Purpose: determine which systems are live and map the network (passive, active). Hosts are identified as live through various stimuli
	Inputs: URL, hostnames, domain names, IP addresses, ranges
	Outputs: Whois, DNS, IP addresses or hostnames of systems which are likely to be 
  live.
	Tools: Ping, Nmap, IKE-scan, Fierce Domain Scanner, Traceroute, ICMP, ...
	Data Types: text files, XML files.
This phase validates documentation, network diagrams, and open source information.

Step 4: Scanning
Major considerations are scanner placement and impediments to testing as firewalls and load balancers.
Various strategies and techniques are used to scan endpoints and network elements across the enterprise.
Organizations must balance accuracy vs efficiency.
Testing must reflect the overall security roadmap and provide actionable results along with metrics.

Purpose: identify known or unknown vulnerabilities in the identified technologies
Inputs: IP addresses, ports, services, applications
Outputs: listing of potential vulnerabilities
Tools: scanners such as Nessus, NexPose, Burp, W3AF...
Data Types: text files, XML files, databases

Concerns include:
	Strategic problems (enterprise) - full host vs available services (e.g., web).
	Scanner placement/architecture
	TCP
	UDP
	L7
	Scanning around/through defensive systems - DLC, LB, IPS/IDS, FW
	Multiple subnets & large networks
	Scanning in Lab vs Dev environments (critical or dangerous systems)
	Passive Vulnerability identification
	Assessing hardened hosts and high security zones

Step 5: Validation 
Purpose: assign confidence value and validate potential vulnerabilities
Inputs: listing of all potential vulnerabilities
Outputs: listing of validated vulnerabilities and confidence rating values. Also, unvalidated findings.
Tools: scripting and manual validation.
Outputs: text files, graphics, XML files, database entries, databases.

Some vulnerabilities may require exploitation, pillaging or pivoting to ascertain impact. To meet compliance and audit requirements identified earlier.
One major issue we face when performing enterprise assessments are collaboration tools and data management.
E.g., LAIR, MagicTree, Dradis, Archeron

Step 6: Remediation

Loops back into other enterprise functions:
	Change management
	Configuration management
	Architectural changes
	Ticketing system
	Framework to tie into other systems

Changes must be prioritized based on risk assessment and cost-benefit analysis that has C-level approval.

Step 7: Reporting

Purpose: Assign risk and priority ratings to confirmed vulnerabilities post mitigation
Inputs: List of validated vulnerabilities 
Outputs: Analysis results
Tools: People brain power
Outputs: text files, database entries
Wordsmithing

Tie into other enterprise processes
Perform analysis
Write findings reports
Executive summary for larger issues
Follow up and loop back


Asset Classification:
- Data classification
- Asset based on server criticality
- System functionality based and dependencies

Management Programs and Lifecycles:
- Asset Management
- Data Classification Management
- IT Management
- VA Management
- Configuration Management
- Change Management
- SDLC
- Incident Response
- Problem Management


Logistics:
- Planning out the logistics and timelines of assessments
- Planning is critical part of process
- Assigning resources
- Project management
- Budgeting

Estimates:
- A VM analyst is required to make sense of the scan results, must prioritize
- Planning + scan time + processing time + analysis + reporting = assessment time
- Don't forget time developing processes and automation

Scanning Speed:
- Balance accuracy with efficiency
- Can be accurate, but it takes too long
- Can be more efficient, but you will miss things
- Objectives of assessment must be clear (specific)
- You cannot scan every host, every port, every check enabled
- Prioritize which hosts/segments to scan more or less
- Fine tune scanning options

VA Maturity Levels:
0 - Do not perform
1 - Perform scanning occasionally on an ad-hoc basis
2 - Perform scanning regular basis, but do nothing with the results
3 - Regular VA and mitigation across organization with VM
4 - Integrated Threat Modeling, Threat Intel, VA with VM and PenTest.

Scanning Strategy:
- Architectural considerations
- Geographical and latency
- Cultural/political issues
- Security devices that hinder testing (hacking naked)
- Speed VS thoroughness & accuracy VS efficiency
- Authenticated VS Unauthenticated Scans
- Safety and excluded systems
- Network scanning nodes
- Other protocols, application scanning and cloud

Testing:
- Every active test consists of stimulus and response, and monitoring to verify the response or lack of.
- Passive techniques only monitor.
- Testing consists of modules.
- Each module has an input and an output
- You must monitor closely for responses
- Testing must be appropriate to the target.
- Testing is of limited value if nothing is fixed.

Automation:
- Consistent results over time
- Scheduling and trending
- Streamlined and more efficient
- Process maintained by support/operational group
- Allows teams to concentrate on what is not automated.
- Requirements:
	- Process
	- Scriptable
	- Tool
	- Database
	- Correlated
	- Analyzed
	- Mitigation
	- Metrics
	- Severity

Team-based operations
	- A good team needs to feel empowered to work together as opposed to in individual silos.
- Adversarial organizations like to play the blame game.
- TPI (Two person integrity) concept is also a central component of the developer SCRUM model, code review. These constructs promote communication within the team. Ensures everyone is involved with each component of the overarching tactical-level mission objective. Also, by sharing all the tactics and tricks of the trade, everyone gets better enabling consistent team growth.

Concept of Operations:
- TTP (Tactics, Techniques and Procedures) - Authoritative
	- Tactics: Employment and ordered arrangement of forces in relation to each other. 
    Represent a specific desired END state.
	- Techniques: Non-prescriptive ways or methods used to perform missions, functions 
    or tasks. MEANS used to achieve a tactical objective.
	- Procedures: Standard, detailed steps that prescribe how to perform specific 
    tasks. Specific WAYS to perform a technique.
- SOP (Standard Operating Procedures) - Prescriptive
	- Precise set of procedures to optimally implement given TTP within their circumstances.
	- Because of myriad of TTP it can be difficult or even counterproductive.
	- 

Identify level of actions to pursue:
- Strategic (high level organizational objectives)
- Operational (logistical connective tissue enabling tactical/strategic objectives)
- Tactical (operational objectives acted upon by the security team)

Knowledge Management Systems

Onboarding/Training SOPs

Effects based adjustment to ensure impactful TTP

Intelligence Sources:
	- HUMINT (Interpersonal intelligence)
	- GEOINT (Geospatial intelligence (satellite))
	- MASINT (Measurement/Signature Intelligence (from radar signatures, nuclear detonation 			 
    signatures))
	- OSINT (Open-source intelligence)
	- SIGINT (Cell phone signal, tapping phone line intelligence)
	- ALL SOURCE (Intelligence Other)

Addressing Risk:
	- Vulnerability:
		- SANS 20 Critical Controls
		- Patching and mitigation
		- Assessment
	- Impact:
		- Incident Response
		- Data Loss Prevention
	- Threat:
		- Cyber Threat Intelligence


Threat Intelligence: analyzed information about hostile intent, capability, and opportunity of an adversary. The focus is on the threat, an agent or actor with intent to cause harm.


Architecture: Intelligence Consumption
	- Build better defensible environments
	- Address important vulnerabilities
	- Have a better and more secure development program

Collection Management Framework (CMF) is a view of sources of data, what is available in the data, and how that data is processed and leveraged. Analysts who do not understand their collection on a technical level cannot satisfy IR's against it or realize the limitations.


Threat Modeling: representation of an idea, an object or system. It can show: structure, relationships, behaviors.
	- It can help prioritize security efforts
	- Avoid intelligence fatigue by focusing efforts
	- Identify knowledge gaps to generate IR's
	- Models are not static - you will have to update them over time


Begin Threat Model:
	- Whiteboard (brainstorm)
	- Visual Diagram (BPM, UML, etc.)
	- Spreadsheet (fuck no)
	- Automated Threat Modeling tool (YES!)

Threat Model Methodologies:
	- STRIDE
	- PASTA
	- Trike
	- ATT&CK
	- VAST

Approaches:
	- Data Flow Diagram
	- Process Flow Diagram


Target-Centric Intelligence Analysis
	- Non-linear approach to the intelligence cycle
	- Builds a conceptual model of a "target"
	- Used as a foundation for further analysis


Python is the defacto language for penetration testers, it is not the language of choice for defenders, blue teamers, or VA personnel. Python does not come installed by default on the systems that these groups most commonly operate: Windows computers. 

PowerShell versions:
v5 - Windows 10
v4 - Windows 8.1, Server 2012 R2
v3 - Windows 8, Server 2012
v2 - Windows 7, Server R2
v1 - Windows Server 2008

PowerShell v2 is the safest but it is missing some nice features
PowerShell v3 is supported by Windows 7+ and 2008+

Some software only exposes advanced options via PowerShell and not via the GUI

PowerShell scripts .ps1 do not execute because it is designed to prevent accidental execution due to phishing or trojan style attack. No special syntax or header necessary to create a script.

Default Execution Policy: Restricted (no scripts allowed)
Other options:
	- AllSigned (only signed scripts can be run)
	- RemoteSigned (remote scripts must be signed, local scripts do not have to 
    be signed)
	- Unrestricted (unsigned scripts can be run)
	- Bypass (nothing is blocked; no warnings; no prompts)

PS /Users/dcgc/Desktop> Get-ExecutionPolicy
Unrestricted

PS /Users/dcgc/Desktop> Set-ExecutionPolicy Bypass
Set-ExecutionPolicy: Operation is not supported on this platform.

PS /Users/dcgc/Desktop> Update-Help                                             PS /Users/dcgc/Desktop> Get-Help about_execution_policies                       Get-Help: Get-Help could not find about_execution_policies in a help file in this session. To download updated help topics type: "Update-Help". To get help online, search for the help topic in the TechNet library at https://go.microsoft.com/fwlink/?LinkID=107116.     


PS /Users/dcgc/Desktop> $dir_desktop = Get-ChildItem /Users/dcgc/Desktop
PS /Users/dcgc/Desktop> dir
dir               DirectoryService  dirExist          dirname           
PS /Users/dcgc/Desktop> $dir_desktop

    Directory: /Users/dcgc/Desktop

..........

PS /Users/dcgc/Desktop> Write-Host $dir_desktop
/Users/dcgc/Desktop/[07-2020] ultimate-aws-certified-sysops-administrator-associate /Users/dcgc/Desktop/A Cloud Guru - AWS Certified SysOps Administrator - Associate 2020 /Users/dcgc/Desktop/Polish A2 /Users/dcgc/Desktop/SEC460 - Enterprise................

https://ss64.com/ps/syntax-variables.html
https://ss64.com/ps/syntax-arrays.html
https://ss64.com/ps/syntax-datatypes.html
https://ss64.com/ps/syntax-scriptblock.html
https://ss64.com/ps/syntax-comments.html
https://ss64.com/ps/syntax-args.html

$_ -> Special variable (Current Pipeline Object)
	- Used in script blocks, filters (Where-Object), ForEach-Object and the 
    Switch statement
	- Can be omitted in certain circumstances (PowerShell v3 and higher)

Cmdlet is command. Structure: Verb-Noun

Cmdlet families:
	Get-Service
	Start-Service
	Stop-Service
	Restart-Service

Get VS Read
Get verb is used to retrieve a resource (file)
Read verb is used to get information from a source (file)

Alias: 
	gci - Get-ChildItem
	ls - mirrors ls from Bash
	dir - mirrors dir from CMD
	cat - mirrors cat from Bash
	type - mirrors type from CMD
	cp - mirrors cp from Bash (Copy-Item)
	copy - mirrors copy from CMD (Copy-Item)

Set-Alias -Name as -Value Select-String
OR
Set-Alias as Select-String


Some parameters in the cmdlet are "Positional", meaning the parameter name is optional and the name is implied.

Get-Service -Name eventlog -> is the complete
Get-Service eventlog -> is the positional

Parameter names can be shortened:

Get-ChildItem -Filter *.exe   -   OK
Get-ChildItem -Fi *.exe				-   OK
Get-ChildItem -F *.exe				-   NOT OK  |  Ambiguous, it also matches 'Force' parameter


PowerShell Objects: properties, methods and events

FileInfo object = File in Windows
Properties:
	Name (RW)
	Length (RO)
Methods:
	Delete
	Encrypt
Events:
	N/A

PS /Users/dcgc> Get-Process

PS /Users/dcgc> Get-Process | Get-Member

Pipeline links one cmdlet with another (like Bash)

PS /Users/dcgc> (Get-Process ProtonVPN).Kill()

PS /Users/dcgc> Get-Process | Where-Object { $_.CPU -gt "0.00" } | Sort-Object -Property ProcessName   
	
PS /Users/dcgc> Get-Help Get-Process

PS /Users/dcgc> Get-Help Get-Process -Full 
PS /Users/dcgc> Get-Help Get-Process -Examples

PS /Users/dcgc> Get-Command -Noun Process
PS /Users/dcgc> Get-Command -Module  
PS /Users/dcgc> Get-Command -Verb Get     

PS /Users/dcgc> Get-ChildItem
PS /Users/dcgc> dir
PS /Users/dcgc> ls 

PS /Users/dcgc> Set-Location Desktop
PS /Users/dcgc> cd Desktop



Discovery:
	Active: scanning
	Semi-Passive: normal traffic, no scanning
	Passive: no traffic to target; no interaction with target; you can interact with 
  intermediate systems (SW, RT and FW; Tap and/or sniffer to analyze traffic)


CAM Table:
CatOS (Old Catalyst): sh cam dyn [#VLAN_ID]
IOS: sh mac add
JunOS: sh ethernet-sw table br

net-snmp net-snmp-utils

snmpwalk is simply a shorthand way to use multiple GETNEXT requests without having to type lots of different commands.  

SNMPv3

snmpwalk -v3 -l <noAuthNoPriv|authNoPriv|authPriv> -u <username> [-a <MD5|SHA>] [-A <authphrase>]
    [-x <DES|AES>] [-X <privaphrase>] <ipaddress>[:<dest_port>] [oid]

# snmpwalk v3 example with authentication and encryption
snmpwalk -v3 -l authPriv -u UserMe -a SHA -A AuthPass1 -x AES -X PrivPass2 192.168.1.1:161 1.3.6.1.2.1.1

# snmpwalk v3 example with authentication, but no encryption
snmpwalk -v3 -l authPriv -u UserMe -a SHA -A AuthPass1 192.168.1.1:161 1.3.6.1.2.1.1 

# snmpwalk v3 example with no authentication and no encryption but you still needs a username
snmpwalk -v3 -l noAuthNoPriv -u UserMe 192.168.1.1:161 1.3.6.1.2.1.1

# Using OID dot1dTpFdbAddress and SNMPv3 context name to get mac addresses in VLAN 32
snmpwalk -v3 -l authNoPriv -u UserMe -a MD5 -A AuthPass1 -n vlan-32 192.168.1.1 dot1dTpFdbAddress


SNMPv2

snmpwalk -v2c -c <community> <ipaddress>[:<dest_port>] [oid]

# Using OID system (1.3.6.1.2.1.1) to get basic system information about host
snmpwalk -v2c -c public 192.168.1.1:161 1.3.6.1.2.1.1


Filter outbound traffic with web proxying. Necessary traffic should be analyzed and logged.
With proxy, we can learn more about the initiator of the traffic.


PowerShell Host Names from IIS

Import-Module WebAdministration
Get-Website

Get-WebBinding | Select-Object -ExpandProperty bindingInformation


PowerShell Host Names from Apache and Nginx

Get-Content ###/httpd.conf | Select-String -Pattern ServerName,ServerAlias

Get-Content ###/nginx.conf | Select-String server_name


Bash Host Names from Apache and Nginx

grep -e ServerName -e ServerAlias ###/httpd.conf

grep server_name ###/nginx.conf


dcgc@dcgcs-MacBook-Air ~ % nslookup -type=ns ytmnd.com             
Server:		2001:730:3ed2::53
Address:	2001:730:3ed2::53#53

Non-authoritative answer:
ytmnd.com	nameserver = auth3.ns.sargasso.net.
ytmnd.com	nameserver = auth1.ns.sargasso.net.
ytmnd.com	nameserver = auth2.ns.sargasso.net.

Authoritative answers can be found from:

dcgc@dcgcs-MacBook-Air ~ % nslookup ytmnd.com  
Server:		2001:730:3ed2::53
Address:	2001:730:3ed2::53#53

Non-authoritative answer:
Name:	ytmnd.com
Address: 216.18.188.175


dcgc@dcgcs-MacBook-Air ~ % nslookup ytmnd.com 2001:730:3ed2::53
Server:		2001:730:3ed2::53
Address:	2001:730:3ed2::53#53

Non-authoritative answer:
Name:	ytmnd.com
Address: 216.18.188.175


dcgc@dcgcs-MacBook-Air ~ % nmap --script dns-brute ytmnd.com
Starting Nmap 7.91 ( https://nmap.org ) at 2021-01-23 11:19 CET
Nmap scan report for ytmnd.com (216.18.188.175)
Host is up (0.15s latency).
Not shown: 998 filtered ports
PORT    STATE SERVICE
80/tcp  open  http
443/tcp open  https

Host script results:
| dns-brute: 
|   DNS Brute-force hostnames: 
|     wiki.ytmnd.com - 216.18.188.140
|_    *A: 216.18.188.175

Nmap done: 1 IP address (1 host up) scanned in 91.56 seconds


Check DNS naming patterns: www-01, www-02, www-03.

DNS Names from Certificates

dcgc@dcgcs-MacBook-Air pentools % python3 GetCertNames.py -t 216.18.188.175
216.18.188.175 443 ytmnd.com
216.18.188.175 443 *.ytmnd.com
216.18.188.175 443 ytmnd.com


Import-Module .\CertInfo.ps1
Get-SSLNames ytmnd.com


Recon-ng:
	- Data stored in a SQLite database

Maltego:
- Transform: taking data and getting additional information

TCP SYN to port 80:
	- If reply is SYN-ACK, host exists, is accessible, and is listening on TCP/80
	- If reply is RST or ICMP Port Unreachable, host could be online and accessible, but port 80 is effectively closed.
	- If there is no reply:
		- Host could be offline and not responding
		- Host could not exist
		- Traffic to Host could be filtered by a FW
		- Host may not respond to traffic on the port
		- Packet could've been lost in transmission

Port Selection Trade-Off:
	- More Ports:
		- Better coverage
		- Slower
		- Maybe too slow and new systems come online or existing ones change
	- Fewer Ports
		- Faster
		- Worse coverage
		- What did we miss?

Option 1: Choose a subset of all the ports
Pros:
	- Faster than all ports
	- Deterministic speed increase
	- Can be tailored to your environment to increase efficiency and accuracy
Cons:
	- What about the missing ports? 
	- All packets are sent to hosts that are offline


Option 2: Select few ports on all systems, full scan of a random subset of hosts
Pros:
	- Faster than all ports
	- Deterministic balance between scan types
	- Might find something in full scan sample that would be missed by the other 
  techniques
Cons:
	- Is the random sample a good sample?


Option 3 (Multiple Stages): Scan a few ports, if it responds scan more ports
Pros:
	- Faster than all ports
	- Can be tailored to your environment to increase efficiency and accuracy
Cons:
	- Might miss a host that isn't listening on one of the few ports
	- May not have enough time to scan all ports in stage 2


If I can't scan all ports:
	- Common ports
	- OS in use
	- OS common ports in listening
	- Is there common service, e.g., backup agent, remote administration
	- Critical services


TCP Common Ports (Nmap)
nmap-services file contains service names, open frequency and additional comments on all ports

cat ###/nmap-services | grep -vE '^E' | grep /tcp | sort -r -k3 | head -n 20


Split Scanning
	- TCP uses 3-way handshake
	- Host A sends a TCP SYN packet using the source address of host B
	- Host B receives responses (SYN-ACK, RST)
	- "SYN Cookie" is used to authenticate the response is valid
	
Distributed Scanning
	- Multiple systems scan independently
	- Results from individuals scans can be combined
	- Nmap XML results can be combined with 3rd party scripts


Nmap Host Discovery:
	- SYN on TCP/80
	- ACK on TCP/443 (bypasses non-stateful firewall)
	- ICMP Echo Request (Ping)
	- ICMP Timestamp

If the remote host responds (e.g., ACK, RST, ICMP Unreachable, ICMP Echo Response), then Nmap knows the remote system is online. Then, it will perform the next portion of the scan.

If the host target is on the same subnet, then Nmap uses ARP to discover if host is up. 


Windows Host:
	- 135 End Point Mapper
	- 137 NetBIOS Name Resolution
	- 139 NetBIOS Session Service
	- 445 Server Message Block (SMB) over TCP/IP
	- 3389 Remote Desktop Protocol (RDP)

Linux host:
	- 22 Secure Shell SSH
	- 111 Portmapper

Services:
	- 1433, 1434 MSSQL
	- 1521, 1630 Oracle
	- 50000, 50001 DB2
	- 3200, 3300 SAP
	- 5432 Postgres
	- 3306 MariaDB, MySQL
	- 9088, 9089 Informix
	- 502 Modbus
	- 20000 DNP3
	- 44818 Ethernet/IP

Sometimes services are run on non-standard ports.
	- Connect and wait for response.
	- Probe the remote service
	- Attempt to establish TLS/SSL connection wait for a response
	- Attempt to establish TLS/SSL connection then probe

Nmap flags:

-PS[ports] -> Check the ports, no space between PS and port list
-PE -> Ping (ICMP Echo Request)
-sL -> List Scan, simply list targets to scan
-sn -> Ping Scan, disable port scan
-Pn -> Treat all hosts as online (skip host discovery)
-PS/PA/PU/PY[portlist] -> TCP SYN/ACK, UDP or SCTP discovery to given ports
-PE/PP/PM -> ICMP echo, timestamp, and netmask request discovery probes
-PO[protocol list] -> IP Protocol Ping
-n/-R -> Never do DNS resolution/Always resolve [default: sometimes]
--dns-servers ,serv1,[,serv2],...> -> Specify custom DNS servers
--system-dns -> Use OS DNS resolver
--traceroute -> Trace hop path to each host
-sV -> determine service type
-sC -> runs 'default category Nmap scripts
--script [name] -> runs mentioned Nmap script 

Nmap scripts:
	- Scripts can in one or more categories
	- Scripts can be run by name or category
	- Categories:
			auth
			broadcast
			brute
			default
			discovery
			dos
			exploit
			external
			fuzzer
			intrusive
			malware
			safe
			version
			vuln

Nmap server test:
Name:	scanme.nmap.org
Address: 45.33.32.156

map done: 1 IP address (1 host up) scanned in 41.02 seconds
dcgc@dcgcs-MacBook-Air ~ % nmap -sV -PS80,443,8080,8000 45.33.32.156
Starting Nmap 7.91 ( https://nmap.org ) at 2021-01-23 16:50 CET
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.20s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE    VERSION
22/tcp    open  ssh        OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13 (Ubuntu Linux; protocol 2.0)
80/tcp    open  http       Apache httpd 2.4.7 ((Ubuntu))
9929/tcp  open  nping-echo Nping echo
31337/tcp open  tcpwrapped
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel


dcgc@dcgcs-MacBook-Air ~ % nmap -PS80 --script http-title,http-enum 45.33.32.156
Starting Nmap 7.91 ( https://nmap.org ) at 2021-01-23 16:56 CET
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.19s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
80/tcp    open  http
| http-enum: 
|   /images/: Potentially interesting directory w/ listing on 'apache/2.4.7 (ubuntu)'
|_  /shared/: Potentially interesting directory w/ listing on 'apache/2.4.7 (ubuntu)'
|_http-title: Go ahead and ScanMe!

Nmap done: 1 IP address (1 host up) scanned in 66.76 seconds


dcgc@dcgcs-MacBook-Air ~ % nmap -PS80 --script http-title,http-enum -oA 45.33.32.156
Starting Nmap 7.91 ( https://nmap.org ) at 2021-01-23 16:59 CET
WARNING: No targets were specified, so 0 hosts scanned.
Nmap done: 0 IP addresses (0 hosts up) scanned in 0.34 seconds


dcgc@dcgcs-MacBook-Air ~ % cat 45.33.32.156.gnmap 
# Nmap 7.91 scan initiated Sat Jan 23 16:59:17 2021 as: nmap -PS80 --script http-title,http-enum -oA 45.33.32.156
# Nmap done at Sat Jan 23 16:59:18 2021 -- 0 IP addresses (0 hosts up) scanned in 0.34 seconds

dcgc@dcgcs-MacBook-Air ~ % cat 45.33.32.156.nmap 
# Nmap 7.91 scan initiated Sat Jan 23 16:59:17 2021 as: nmap -PS80 --script http-title,http-enum -oA 45.33.32.156
WARNING: No targets were specified, so 0 hosts scanned.
# Nmap done at Sat Jan 23 16:59:18 2021 -- 0 IP addresses (0 hosts up) scanned in 0.34 seconds

dcgc@dcgcs-MacBook-Air ~ % cat 45.33.32.156.xml 
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE nmaprun>
<?xml-stylesheet href="file:///usr/local/bin/../share/nmap/nmap.xsl" type="text/xsl"?>
<!-- Nmap 7.91 scan initiated Sat Jan 23 16:59:17 2021 as: nmap -PS80 -&#45;script http-title,http-enum -oA 45.33.32.156 -->
<nmaprun scanner="nmap" args="nmap -PS80 -&#45;script http-title,http-enum -oA 45.33.32.156" start="1611417557" startstr="Sat Jan 23 16:59:17 2021" version="7.91" xmloutputversion="1.05">
<scaninfo type="connect" protocol="tcp" numservices="1" services="80"/>
<verbose level="0"/>
<debugging level="0"/>
<runstats><finished time="1611417558" timestr="Sat Jan 23 16:59:18 2021" summary="Nmap done at Sat Jan 23 16:59:18 2021; 0 IP addresses (0 hosts up) scanned in 0.34 seconds" elapsed="0.34" exit="success"/><hosts up="0" down="0" total="0"/>
</runstats>
</nmaprun>




Masscan:
	- When sending SYN to listening service, a SYN-ACK will be sent back
	- Since Masscan uses it's own TCP stack, the kernel doesn't know why it 
    received a response
		- Linux will send a RST packet and kill the connection
		- Windows will not
	- Masscan is designed to use a dedicated IP address

Masscan flags:
--ports -> Define ports
--rate -> number of packets per second
--source-ip -> define source IP (it can be a VIP, for example)

--output-filename -> define filename for output file
--output-format -> define output format
OR
-oL [filename] -> List format
-oJ [filename] -> JSON format
-oG [filename] -> Grepable format
-oB [filename] -> Binary format
-oX [filename] -> XML format
-oU [filename] -> Unicornscan format

--readscan [binary file] -> input binary file from Masscan and output it to the format you want

-c [file] -> input configuration file for flag definition

# Scan Test
rate =  0.01
output-format = xml
output-filename = scan.xml
ports = 22,23,25,80,443
range = 192.168.5.1-192.168.5.50
retries = 0
http-user-agent = Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/44.0.2403.89 Safari/537.36
ping = false
banners = true


dcgc@dcgcs-MacBook-Air ~ % sudo masscan --ports 0-1024  45.33.32.156

Starting masscan 1.3.0 (http://bit.ly/14GZzcT) at 2021-01-23 16:06:33 GMT
 -- forced options: -sS -Pn -n --randomize-hosts -v --send-eth
Initiating SYN Stealth Scan
Scanning 1 hosts [1025 ports/host]
Discovered open port 80/tcp on 45.33.32.156                                    
Discovered open port 22/tcp on 45.33.32.156


dcgc@dcgcs-MacBook-Air ~ % sudo masscan --ports 0-1024 --rate 1000 --source-ip 192.168.0.87  45.33.32.156

Starting masscan 1.3.0 (http://bit.ly/14GZzcT) at 2021-01-23 16:12:15 GMT
 -- forced options: -sS -Pn -n --randomize-hosts -v --send-eth
Initiating SYN Stealth Scan
Scanning 1 hosts [1025 ports/host]
Discovered open port 22/tcp on 45.33.32.156                                    
Discovered open port 80/tcp on 45.33.32.156    


dcgc@dcgcs-MacBook-Air ~ % sudo masscan --ports 0-1024 --rate 1000 --source-ip 192.168.0.87  --output-filename test.mass --output-format binary  45.33.32.156

Starting masscan 1.3.0 (http://bit.ly/14GZzcT) at 2021-01-23 16:14:02 GMT
 -- forced options: -sS -Pn -n --randomize-hosts -v --send-eth
Initiating SYN Stealth Scan
Scanning 1 hosts [1025 ports/host]
dcgc@dcgcs-MacBook-Air ~ % cat test.mass 
masscan/1.1
s:1611418442
`
 KL-! ?6masscan/1.1% 

                        
_____________________________________________________________________


Vulnerability Assessment is the intersection between Pentest and Audit


Threat: An agent or actor that can cause harm
Vulnerability - A flaw someone can exploit to cause harm
Exploit - Code or technique that a threat uses to take advantage of a vulnerability


Exploit Types (technique focused)

Overflow/Underrun Exploits:
	- Buffer Overflow
	- Buffer Underrun/Underflow
	- Heap Spraying
	- Format Strings
Injection Attacks
	- Code Injection (SQL, PHP, Ruby, Python, Perl, etc.)
	- Command Injection
Web Application Attacks
	- CSRF, XSS, SQLi, etc.

Exploit Subtypes (result focused)

Remote Code Execution
Memory Corruption
Buffer Over-Read
	- Heartbleed
File Inclusion
Information Disclosure
Session Management Errors
Cryptographic Implementation Errors


Detect the following on a system (to start with):
	- Software version number
	- Accepted protocol version numbers
	- Service authentication (yes/no)
	- Service configuration settings


General Purpose Vulnerability Scanners
	- Nessus
	- Qualys
	- Nexpose
	- OpenVAS
	- SAINT
	- Retina

Application Specific Vulnerability Scanners
	- Nikto
	- Acutenix
	- Burp Suite
	- WPScan
	- IBM Appscan
	- VOIPAudit

Scanning
	- Asset Discovery
	- Scanning
	- Service Detection

Vulnerability Testing
	- Banner Grabbing
	- Vulnerability Correlation
	- Validate Vulnerability


Scanning (Asset Discovery) - Chain of Events
e.g.,	IP -> Trigger Scan -> Port Discovered -> Triggers Service Detection -> Port 
			-> Trigger Access Service

Scanning (Vulnerability Testing) - Chain of Events
e.g., Banner Grab -> Acquire service version -> Trigger CVE Correlation - CVE ->
			No known exploits -> NEXT_PHASE Credential Login -> Access without auth ->
			Trigger CVE validation -> NEXT_PHASE Vulnerability Validation -> W/R/D data
			-> Trigger CVE Report

Scanning (Reporting) - Chain of Events
	- Do not over-rely on reports.
	- To get true understanding, we must go deeper.


Mitigation blueprint is an accurate measurement of unrealised risk that must be taken.

Vulnerability assessors are responsible for identification, measurement and triage of cybersecurity exposure.


Risk Management Culture: developing an organizational risk management culture is iterative and cumulative.

Risk Identification: Threat Assessment and risk ratings enable true network security insight

Mitigation: Develop a mitigation blueprint in order to Control the risk

The discipline of risk management is focused on loss avoidance.

Business Risk:
	- Information Security Risk
	- Strategic Risk
	- Compliance Risk
	- Operational Risk
	- Financial Risk
	- Reputational Risk
	- Personnel Safety Risk

Organizational Risk = Probability x Impact

Risk = Threat Probability x Vulnerability Magnitude

Severity ≠ Risk

Severity rating is unbiased, simple, fast, easy to justify. But it does not include probability or impact metrics.


Risk Rating Systems:
	- CVSS
	- OWASP
	- OCTAVE
	- PTES
	- STRIDE
	- DREAD (Microsoft)
	- Infocon


Qualitative Analysis
	- Risk Assessment
	- Brainstorming
	- Risk Rating Scales

Quantitative Analysis
	- OSSTMM RAV
	

Infocon Rubric
A score of 6 or greater moves Infocon up to Yellow, and 10 or greater moves us to Orange.

How we score the Infocon status:
+2 Slammer-like impact on Internet wide operations
+2 Remote arbitrary code execution
+2 No vendor patch or effective mitigation is available
+2 Active exploitation of vulnerability
+1 Affects current version of up to date software
+1 Affects widely deployed software
+1 Relatively easy to exploit
+1 Proof of concept code is available
+1 Affects current version of up to date software
+1 Affects a Microsoft OS or Adobe application
+1 Wormable
-1 Affects obscure or obsolete OS or application
-1 Requires user intervention to run
-1 IDS/IPS rules or other detective controls are available
-1 Major anti-virus vendors can detect and clean malware
-1 Mainstream media and everyone else has already covered issue
-1 Vendor has released an advisory/bulletin/announcement (and decent workaround)


NSE Nmap Categories (script.db):
	- Auth
	- Broadcast
	- Brute
	- Default
	- Discovery
	- DOS
	- Exploit
	- External
	- Fuzzer
	- Intrusive
	- Malware
	- Safe
	- Version	
	- Vuln


Rapid7 Nexpose has integration with Metasploit

It is BAD practice to provide scanner reporting as a central component fo a Vulnerability Assessment. GOOD assessors use their tools as tools. They are not valid replacements for operators and provide only the barest launching point for true risk evaluation.

Overuse of built-in vulnerability scanner reports is the #1 hallmark of BAD security assessment.


Baseline Scan:
	- Initial scan.
	- Conducted prior to developing a holistic security plan.

Scheduled Scan

Event/Change based assessment:
	- Triggered based on set of predefined conditions.


Application Specific Methodology

1. Injection
2. Weak Authentication
3. XSS
4. Insecure Object References
5. Security Miscofiguration
6. Sensitive Data Exposure
7. Missing Access Controls
8. Cross Site Request Forgery
9. Known Vulnerabilities
10. Unvalidated Redirects



Nikto is not a web application scanner and is more focused on issues affecting the webserver (it is a web server scanner).

Nikto supports injection tests for XSS and SQLi but the discovery of these should be performed in conjunction as these modules are rarely effective.

Nikto is a scanner that is between General Purpose Scanner and Application Specific Scanner.

-mutate[#CONDITION_NUMBER] Flag
Test directories and structures against the target application

1 - Test all files with all root dirs
2 - Guess for password file names
3 - Enumerate users via Apache (/~ user type requests)
4 - Enumerate users via cgiwrap (/cgi-bin/cgiwrap/ user type requests)
5 - Attempt to brute force sub-domain, assume parent domain as hostname
6 - Attempt to guess dir names from supplied dictionary file


-Tunnint[#CONDITION_NUMBER] Flag
Control test types and conditions to limit false positives and unintended service outages.

Some of the conditions for this flag can launch real attacks and actively exploit target, be careful!

0 - File Upload
1 - Interesting File / Seen in logs
2 - Misconfiguration / Default File
3 - Information Disclosure
4 - Injection (XSS/Script/HTML)
5 - Remote File Retrieval, in web server root directory
6 - Denial of Service, without launching DoS attack
7 - Remote File Retrieval, in server wide
8 - Command Execution / Remote Shell
9 - SQL Injection
10 - File Upload


CMS Common Privilege Escalation:
XSS -> Admin impersonation by stealing cookie -> PHP Tradecrafting in Plugin Editor -> Access www-data in server -> Privilege Escalation -> Pillage, Passwords and pivoting -> Access granted.

CMS Scanners.

SSL/TLS attacks categories:
	- Subverting trust model
	- Attacking protocol implementation
	- Cracking encryption directly 

VoIP attacks categories:
	- Eavesdropping
	- Denial of Service
	- Spoofing

SIP, RTP, RTCP, MGCP, IAX, Skinny (SCCP), Skype, Lync

VoIP Protocol Stack
	- SIP (trunks): signaling portion of the session. Performs session establishment and modification functions.
	- RTP (communication / data transmission): handles all voice and video content transmitted as part of the call.
	- SDP (call setup): it is the payload within SIP. Contains codec and media format (e.g., H.232).

Other infrastructure appliances (network, VM, etc.) are ofter overlooked and seen as "dumb". These are prone to misconfigurations. Automatic, Plug-and-play configs can lead to information disclosure and even exploitation.

SNMP security risks:
	- Public Community Strings
	- Egregious Info Disclosure

Often scanning efficiency/efficacy is limited when testing infrastructure appliances:
	- Instead of external scanning consider config audit
	- Common Configuration Errors:
		- Default Passwords
		- Poor Auth Controls
		- Weak Credential Storage
		- Insecure Mgmt Methods

SSH should be used and Update/TFTP controls should be implemented.


Wireless Secure Implementation Guideline:
	- WPA2 Enterprise
	- Require "Certificate and Password" Auth
	- Control Wireless Footprint (5GHz band easier)
	- Secure physical access to AP's
	- L2 controls: Wireless VLAN and Port Security.



Vulnerability Validation
Input: Threat Assessment, vulnerability Report
Output: Vulnerability Assessment, Remediation Plan

Excess data is excessive noise, managing information and drilling into impact enables us to translate gibberish and gain true understanding

Goals of Vulnerability Validation

Tactics Snapshot
	- Manual validation of vulnerability scanning results
		- false positive reduction techniques
		- enterprise scripting enhanced with WinRM
	- Mass Data Mgmt
	- Assigning confidence values
	- constructing and maintaining a vulnerability knowledge base
	- triage: assessing the relative importance of vulnerabilities against strategic risk


Assign confidence values
Reduce false positives and false negatives
Understand the sources of vulnerabilities to enable upcoming remediation

Some vulnerabilities require exploitation, pillaging and/or pivoting to ascertain impact.

All potential vulnerabilities -> Confidence -> validated vulnerabilities wirg confidence rating values
Tools: manual validation, scripting

Adding tools to tool belt is important but each tool has limitations.
	- Tools mischarecterize findings
	- Tools assume vulnerabilities based on version lookup that have been mitigated or eliminated through technical controls

Validation enhances triage which in turn provides a prioritized ranking of flaws to remediate.

Validation categories:
	- Prioritization
	- Scope

Validation techniques:
	- second opinion: retest finding with new tool or technique (reduction of FP)
	- replication (manual) testing: manually recreate assessment technique to confirm result (like manually launching PoC payload as opposed to Scanner sending the custom payload itself, automatically)
		- takes time and provides optimum control and understanding of result
		- focus on exploitation result and attempt to prove exploitation is possible

Vulnerability result:
	- system
	- vulnerability
	- impact

Don't consider results from automated scanners that correlate system details/version to vulnerability. 
RCE, SQLi are examples of vulnerability categories that are limited by scan.


Test file sharing:
net use (SMB)
mount (NFS)
Windows Explorer (net; cmd; etc)
Web Browser (client web browser)

Authenticated scans can be heavy, slow and kill performace
Compare auth vs unath scan results
perform manual auth checks alongside traditional scan to optimize performance

credential scanning - benefits:
	- non-disruptive to operations
	- limited network resource consumption
	- direct host interrogation to validate patching for vulnerabilities
	- fewer FP

credential scanning - pitfalls
	- scanner has elevated access permission, can be a target for exploitation
	- attacker can compromise security appliance to do privilege escalation
	- vendors usually ignore this risk and provide configuration procedures

Issues for security policy procedure to include in development phases:
	- understanding documenting environment
	- using principle of least privilege (POLP)
	- using principle of least service

Balance scanning between time, effort and expense.

Type of credentials:
	- network
	- application

Service accounts
	- shared ceredentials can be used in multiple sites
	- site-specific credentials can only be used in the site for in which they are configured

Service account AD:
	- account logs in remote (WMI and/or CIFS) but it is not Guest
	- account must read registry, file info related to OS files and installed software
	- account must be within domain or a local administrator account

Administrative AD accounts:
	- default Administrator account
	- account created later that have administrative privileges directly or by admin group.

Win2k3 AD:
	- Service admin account govern maintenace of delivery of directory services (e.g., mgmt of DC and AD).
	- Data admin account govern data stored at directory service, on domain member sersers, workstations in the domain.

Authenticated scans should be executed at least once a month on covered devices.

Best practices - Credential Scanning:
	- Create temporary account dedicated to auth scans, for more granular control.
	- confirm scanner-account is able to auth to covered devices.
	- do not user clear text protocols.
	- consider MitM attacks between target and scanner appliance.
	- disable scanner-account once the auth scan is completed.
	- automate tasks of enable/disable scanner-account (via scripts or in the scan profile itself)
	- restrict IP from which we can login to the scanner-account.
	- failed logon attempts should not happen (automated service account)
		- enable immediate lockout
SSH keys (PEM) can be used for login.

Search locked out AD accounts
PS C:\> Search-ADAccount -LockedOut

Get all hotfixes on the local PC
PS C:\> Get-HotFix

Get all hotfixes on multiple computers that start with a search string
PS C:\> Get-HotFix -Description "Security*" -ComputerName "Server01", "Server02" -Cred "Server01\admin01"

Create a text file that contains the computer names that are missing a security update
PS C:\> $A + Get-Content "servers.txt"
PS C:\> $A | ForEach { if(!(Get-HotFix -Id "KB957095" -ComputerName $_)) { Add-Content $_ -Path "Missing-kb953631.txt"}}

Get the most recent hotfix on the local PC
PS C:\> (Get-HotFix | sort installedon)[-1]

Original command port listing
PS C:\> netstat -ano

WinRM invocation port listing
PS C:\> Invoke-Command -computer \\IP COMMAND

Combined port listing
PS C:\> Invoke-Command -computer \\IP -scriptblock { netstat.exe -ano }

Retrieve System Information
PS C:\> Get-WmiObject -class Win32_OperatingSystem

Kill or enumerate processes
PS C:\> ps -name EMET_Agent | % {taskkill /F /PID $_.Id}

Check for MS17-010
PS C:\> Get-Hotfix -Id KB4012212,KB4012215,KB4015549
PS C:\> Get-Hotfix -ComputerName DC01, WS05, DoesNotExist -Id KB4012212


PS C:\> Invoke-Command -computer DC2 -ScriptBlock {Is C:\}
PS C:\> Invoke-Command -computer DC2 -ScriptBlock {Get-Culture}
PS C:\> Invoke-Command -computer DC2 -ScriptBlock {ipconfig}



Enterprise Security Knowledge Base: baselines, configurations, lessons learned.

Mind Mapping: technique to assist learning and improves information retention and enhances creative problem solving.

Feynman Technique:
1 - Pick a topic.
2 - Imagine you are teaching the topic to class.
3 - Hit the books as you get stuck.
4 - Simplify and use analogies.

Network topology/layout - incorporate external data into your knowledge-base
It is a body of knowledge share between business units.
Contribute to it:
	- advanced discovery and enumeration techniques
	- running services, open ports
	- powerful information IT department configuration management processes

Simplistic Asset Inventory:
	- In addition to raw data we should track pertinent details about the systems we discover.
		- Tracking list displaying how far along we are
		- Findings table enabling rapid prioritization of validation, triage and remediation actions

Example table:
__________________________________________________________
| Target IP | Hostname | Ports | Vulnerabilities | Notes |
––––––––––––––––––––––––––––––––––––––––––––––––––––––––––
|			|		   |	   |				 |		 |
––––––––––––––––––––––––––––––––––––––––––––––––––––––––––

Include in each asset:
	- Discovery method
	- tools used
	- techniques or commands used
	- assessor name and timestamp

Cataloging enables trend identification:
	- enables to identify common issues that result in the greatest pain points
	- forms components of what can become a team memvber onboarding process

Components:
	- Threat Model
	- Asset Inventory
	- Critical Asset Prioritization List
	- Vulnerability Database

You start centralizing vulnerability information, asset information and other information on a Wiki (Confluence) and on a Ticket Management System (Jira)

Acheron - RESTful vuln assessment
1- Collection & Normalization of Vulnerability Data
2- Search
3- Automate & Analyze
4- Data Management
5- Terminal Extensibility

"Data is to be used not observed"
- Principal benefit of performing data management within operational frameworks is the relative simplicity of transforming new data into immediate action.
- Metasploit DB is a nontraditional alternative for data mgmt

Developing a Collaboration Workflow:
- Good teams make themselves
- Great teams remake themselves

Fundamental trust, positivity, and mutual respect provide a solid base to begin building

In all good teams every member has a place, a contribution, and a goal.

Teaming Concept:
	- Blue Team: tasked with defense overall
	- Red Team: evaluate and grow blue team's capacity to perform defense, with adversary emulation
	- Green Team: remediation of security vulnerabilities
	- Black Team: Hunt team; focused on cyberspace trapping and adversarial deception.
	- White Cell: enable teaming event by acting as the intercessor between red and blue teams, validating findings and ensuring system availability.
	- Gray Cell: simulates unwitting user or occasionally an insider threat. Adds realism to the network exercise and facilitates blue team growth by aiding red team exploitation.
	- Purple Team: newer concept focused on a direct collaborative relationship between blue and red functions.
		- Not adversarial
		- often formed of members from both blue and red
		- simulation over exploitation
		- Types of Purple Teaming:
			- Egress Testing: attack detection capabilities and network security control implementation failures; minimize available outbound communication channels (ports, protocols, hosts, processes)
				- Use representative host, user
				- Test using accounts with different group relationships
				- Test w/ TCP and UDP
				- If control is successful annotate this and disable the control to continue testing layered security
				- It can be simple port scanning:
					- On nmap use scanme.nmap.org to enumerate available channels
				- It can be socket port binding:
					- Netcat, Powercat, PowerShell
				- Only admins should have access to network mgmt ports/protocols
				- SCADA, sensitive systems should be restricted to include access to HTTP/S
				- Processes should be restricted (e.g., Windows Firewall)
				C:\> netsh advfirewall firewall add rule name="Block Skype" dir=in action=deny program="C:\program\skype.exe" enable=yes
			- C2 Testing: executes code simulating communication over arbitrary channels (pivot testing, lateral communication methods, air gap testing and bypasses)
				- Three-fold goal:
					- Which techniques work/didn't work?
					- If work, blue team detect? What tools/techniques used in detection? Defensive tactics receive increase emphasis in future?
					- If work, but not detected, why? What attacker with this access can do? What can he do further?
			- Pivot Testing
			- Shot Validation
				- positive/negative shot validation of adversarial C2 tactics, blue team MUST be involved
			- Detection Collaboration

Collaborating between each other:
	- VA like C2 and Egress Testing is Purple.
	- VA team is expected to have degree of solidarity with net admin and sysadmin
		- Unfolds an opportunity to take advantage of that as a force multiplier

Triage leads naturally into remediation:
	- Objective of triage is to identify what the defenders can do to make the biggest differnce in their circumstances.
	- This requires a duality of consideration in:
		- Effort: effort required for defender to apply fix or actively defend; how difficult would be for an attack to use an exploit successfully
		- Impact: fallout if attacker exploited this; defending has third order effects; is it worth defending


AD Design and permission model can have flaws and attackers use this to their leverage:
	- Traffic for AD is not blocked by firewalls and can lead to quick escalation paths.
	- Possible to solely use issues in AD and privileged account flaws to gain complete control of AD-integrated environments.

AD terminology:
	- Objects are OU's.
	- Group Policy: configures users and computers by admins.
	- DC's: servers that run AD Domain Services.
	- Any user or computer can authenticate to any DC it can reach in the forest.
	- DC replicate info via LDAP
		- Using DCSync call
		- DC in same AD site replicate every 5 min
		- DC in different AD site replicate every 180 minutes
	- DC's are multi-master DB servers
	- Five named "roles" exist to reduce conflicts in changed data

Kerberos:
	- Client
	- KDS (Key Distribution Server) / DC
	- Server(s)

Domain Controllers:
	- No local accounts
	- Controlling any RW (read-write) DC = full compromise of that forest (and any other "downstream" / trusting domains or forests)
	- Password hashes are stored in %windir%\ntds\ntds.dit
	- Need to be combined with HKEY_LOCAL_MACHINE\System registry hive to retrieve plaintext credentials
	- Associated with one domain, but multiple domains can be in one AD "forest"
	- Domains are used as replication boundary (DC replicate within same domain), but domains are not a security boundary.


KRB_AS_REQ (Authentication Server Request): client authenticates to DC using client NTLM hash
KRB_AS_REP (Authentication Server Reply): DC replies with TGT (has portion encrypted with krbtgt password hash)
KRB_TGS_REQ (TGS Request): client send TGT to DC and requests access to specific service on AD-joined machine
KRB_TGS_REP (TGS Reply): DC responds to client with TGS (service ticket; portion encrypted with password hash of service the client is trying to connect to)
KRB_AP_REQ (Application Server Request): client connects to service on AD-joined machine.

GPO
- GPO targeted by OU or WMI Filters
- WMI Filters allow testing conditions like group memebership, chassis or OS type.
- Any mistake in GPO permissions can effectively allow admin rights on targeted machines.

GPP
- Preferences, not settings
- GPP change by user
- GPO cannot be changed or overridden by user
- GPP pre-configure user environment but doesn't prevent user from changing things

Kerberoasting: requesting tickets for services; ticket encrypted with password hash
	- account mapping can be enumerated by asking DC for list of SPN (Service Principal Names)
	- Service doesn't need to be accessible:
		- Firewalled
		- Offline
		- Deprecated
	- allows offline cracking of passwords (hashcat)


Golden Ticket: compromised krbtgt NT hash allows attacker to create arbitrary tickets for everything; long-term persistence method
	- allows attacker who previously compromised DC to maintain access (persistence method)
	- krbtgt account hash never rotates by default
	- Change krbtgt twice (at least 10-24 hours between each change or you will break the domain)


Silver Ticket: compromised service account password or hash allows user to generate arbitrary tickets for that service.
	- use machine account password hash to maintain persistence to machine (persistence method)
	- uses COMPUTER_NAME$ AD account


Simple mitigation of password attack is a strong password policy:
	- Often strong is confused with hard
	- 2FA is superior

Maximum password age is no longer recommended by NIST

Windows Password Collection:
	- Local System Collection (needs system-level/nt authority access): hash collection via SAM (use hashdump feature from meterpreter RAT; achieve similar affect); mimikatz plaintext credentials through LSASS memory access (integrated into numerous backdoors across many formats).
	- Network-based collection: kerberoasting; llmnr (DNS) and nbns (NetBIOS) (used for windows hostname resolution) poisoning (spoofing name resolution requests); causes victim to expose their NetNTLMN hash
	- Domain-based collection: NDTS.dit extraction; it contains domain password hashes but can't be accessed directly while AD is running. Workarounds are: stopping AD or using VSSOwn (Volume Shadow Copies); using ntdsutil to create IFM (Install From Media) backup; DCSync, using Domain Replication to extract password across network

Password audit:
Ask Admin or team managing DC's to get copy of NTDS.dit file/archive that contains the password hashes. For an attempted cracking of the hashes, we are doing password auditing.

To extract the hashes from the NTDS.dit file, use Impacket:
secretsdump.py

client.ntds user/password hash:
	domain\username:LMhash:NThash:::

When doing password audit, only guess passwords that don't match current strength requirements. If the password gets cracked, it needs to be changed.

AD Password filter:
	- Disallow previous comprosmised passwords
	- disallow variations of company name
	- set it up on DC's

SCCM: requires agent install via:
	- gold image
	- PSExec
	- Group Policy

GPO: applied in cascading fashion; more general policy can be overriden by more specific policy. applied in group members or OU within AD. Specific policies have incresead priority: OU > Domain > Site
GPO Best practices: 
	- avoid use of enforced GPO, blocked inheritance OU
	- use WMI filter as necessary
	- keep each GPO focused on one task

Cyberspace trapping: aggressive strategy for defense.
	- Objective: not block attacks
		- blocking all attacks, leaves fewer options to identify attacks you cannot
		- poison root of their methodology
		- follow effects of this
	- engaging adversaris by tactic instead to tooling, is not static bypass-able defense like AV signatures
	- when opponent is uncertain they are vulnerablem they are deceived as weak.

Deception and Obfuscation VS Remediation:
	- hiding vulnerability is not fixing a vuln, no matter level of obfuscation; risk acceptance
	- defense techniques on lateral movement as opposed to forward movement, are likely to catch an attacker off-guard.
	- Test manually findings, to valiade them.
	- Be aware of risks you accept and add to environment; they may not be sufficiently mitigating.

