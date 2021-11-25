---
layout: page
title: Vulnerability Management
categories: notes
permalink: /vm/
---


VAF Phase 5 - Vulnerability Validation
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

