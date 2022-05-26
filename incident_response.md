# Incident Response

OODA Loop: observer, orient, decide, and act. When engaging an enemy, try to ensure that you are not always reacting. Pause, analyze, incorporate information from the battlefield, and then integrate new knowledge into the next course of action. The OODA method works.

FoW: Fog of War. In a crisis, no one knows what is going on and everyone wants to know. The successful IR team and its leader will keep informed and let SME's do their jobs. Control the fog.

Friction: In a tough and tense situation, contention and hostility can occur. Incident response is a team sport. Be patient and calm.

Unity of Command: Ensure there is a solid, realible, and well known decision making process in place. The group should be an odd number to prevent deadlocks. Achieve decision making in a timely manner.

# **Six Steps of Incident Response**

## **Step One: Preparation**

 <table><tbody><tr><td>

**Preparation Step (Be Ready)**

</td><td>

**Key activity: Actively conduct pre-incident planning, per system (a recurring processs)**

</td></tr><tr><td>

NTP

</td><td>

Enable NTP for all devices that can use. Ensure Windows clients are synchronized with AD. Decide on GMT offset or a consistent time zone across the organization.

</td></tr><tr><td>

Decide on critical policy issues

</td><td>

Implement logon warning banner, agreed with Legal and Human Resources.

 Determine how IR team engages with Law Enforcement: process, who will engage, and how to engage.

 Media liaison also needed.

 Survey HR for policies that support IR.

 Establish policy so that the IR team has the “right access and monitor”. The IR team should establish elevated access accounts, kept in secured storage, for emergencies.

 Ensure IR team relates to the compliance hotline and “abuse” email handle for all registered domains.

</td></tr><tr><td>

Establish central logging capability

</td><td>

Establish a protected logging aggregation point (likely a Linux server) which has multiple terabytes storage.

 Ensure systems detect on incident and that they report both locally and to the central server.

 IR team strongly encouraged to use syslog-ng because of its filtering options. In particular, there are many Windows events such as machine logon that can reasonably be discarded. Syslog-ng provides a filtering syntax which can accommodate discarding low value log data.

</td></tr><tr><td>

Identity and user account management issues

</td><td>

It is highly preferred to follow the “one user, one account rule”. Standardized names across many systems aren’t always implemented, though. Most organizations have central directories, but there are often system specific accounts whose account names may not agree with the main directory but are assigned to the same person. Beware of inconsistent naming conventions. It may be possible to add an account attribute, such as employee ID to accounts.

</td></tr><tr><td>

Service or system account management

</td><td>

Establish generic, shared, service and system account ownership. If possible, update the description or comment field with the responsible person’s account name. Decide early if, and how, the IR team can access these accounts if it becomes necessary. Document who has knowledge of these accounts and passwords.

 Establish procedures for password rotation process and where service/system account credentials are stored. Always rotate them when and account holder terminates employment.

</td></tr><tr><td>

Jump bag contents

</td><td>

Sanitized drives

 Incident forms, bound notebook, pens.

 Printed copy of IR team call tree.

 Common and tools (and a leatherman!).

 Linux distros of note include SIFT and Kali Linux on CD and bootable USB.

 Flashlight with batteries removed to prevent corrosion.

 Checklists for memory/drive image tools usage. Network taps and “snagless” LAN cables. Earplugs for datacenters. Spare clothes.

</td></tr><tr><td>

OOB notification capability

</td><td>

IR teams need secure communication capability that cannot be monitored by an attacker or insider. For example, everyone on the IR team should have a cellphone and a secondary external email account.

</td></tr><tr><td>

Helpdesk or ServiceDesk

</td><td>

Continual training on first call initial incident data collection.

 First line that have valuable eyes and ears for IR team.

 Define an intranet incident form or incident specific ticket which ServiceDesk (or an end user) can use to better document and gather initial incident information.

</td></tr><tr><td>

Work out IR team issues

</td><td>

Determine IR team membership and rotation. Budget to conduct continual training. Decide on response process, initial triage SLA.

 Periodically conduct some form of IR drill.

 Provide a secured analysis room with locking cabinets to secure evidence and tools.

</td></tr><tr><td>

Key decisions

</td><td>

1.  Decide on “Watch and Learn” or “pull the Plug” decision criteria and time box.

 2.  Decide on “Contain and Clean” stance with the desired evidence preservation level.

 3.  Understand applicable data breach requirements (regulatory/legal)

 4.  Determine process for handling and reporting criminal activity.

 5.  Understand the organizations stakeholders and their expectations. For example, the shareholders, supports, adversaries, and participants or partners in organizations value chain.

 6.  Ensure that IR team understands and supports organization priorities.

 7.  Fully understand the IR operating model, roles, front line responders, and forensics capability.

</td></tr><tr><td>

Preparation step exit criteria

</td><td>

Preparation is a continual process.

 For example, ensure each new system is prepared for IR. Review preparation activities periodically.

</td></tr></tbody></table>  

**Step Two: Identification**

 <table><tbody><tr><td>

**Identification Step (Calmly Document)**

</td><td>

**Key Activity: Short Cycle; be sure there is an incident; maintain chain of custody.**

</td></tr><tr><td>

Initial determination

</td><td>

Perform “event” intake: gather initial information to determine incident potential.

 Make a decision to proceed if the event may be an incident. Start IR document.

</td></tr><tr><td>

Assignment

</td><td>

Assign initial handler. When possible, use a team of two. Note start time in the IR log.

</td></tr><tr><td>

Survey identification points

</td><td>

Perimeter, DMZ assets, internal systems, line of business applications, notification from external sources.

</td></tr><tr><td>

Understand limitations

</td><td>

There is no “one size fits all” process.

 IR team must know “normal” conditions to find incidents. Any system baseline can be very helpful here.

</td></tr><tr><td>

Run through system checklists

</td><td>

As explained later in this handbook, review the OS, network device, and application specific logs for any suspicious activity.

 Analysis should be guided by checklists to help provide a uniform and consistent response process.

</td></tr><tr><td>

Perform internal vs. external system and network consistency check

</td><td>

When a system isn’t consistent with respect to its local reported network activity (netstat) and it’s observed on network actual activity (tcpdump), the IR team has strong evidence that the incident is serious because something is hiding on the local system (a rootkit potential). Netstat vs. network activity vs. nmap scan vs. process vs. memory analysis should all “match up”.

</td></tr><tr><td>

Key decision

</td><td>

1.  Is the “event” an actual “incident”?

2.  Do we watch and learn? If so, how long? Or do we pull the plug?

</td></tr><tr><td>

Identification step exit criteria

</td><td>

The assessment process has determined the event(s) constitutes a real “incident”, therefore activate the IR process and continue.

</td></tr></tbody></table>   

**Example Assessment Questions**

- Is the “event” explainable, plausible, a mistake, a human error, a system error, or some other explainable occurrence?

- What is “normal”, and has the situation deviated enough to be abnormal?

- How widely used/deployed is the system, platform, or application that is affected? What is the needed uptime or business impact?

- What is the value of the system/data and the uptime to the organization?

- Is it possible to remotely exploit the vulnerability?

- Is the vulnerability from a configuration error?

- Or programming type error?

- Is there a vulnerability in an underlying library?

- Is there publicly available or reported exploit code or method that can be used against the system?

- Are there compensators currently in place (in fact deployed)?

**Step Three: Containment**

 <table><tbody><tr><td>

**Containment Step (Control Pain)**

</td><td>

**Key activity: System and environment modification occurs in response**

</td></tr><tr><td>

Characterize the incident, which drives follow on activity

</td><td>

The type of incident will determine actions taken. Some example and possible actions:

 DoS/DDoS – control WAN/SP

 Virus Infection – contain LAN/System

 Remote compromise – firewall, net trace, update ACL

 Data loss – user activity, data breach

 System held hostage – recover from backup and harden

 Website Defacement – repair, harden

 Internal / employee – monitor, HR

 Domestic Espionage – evidence, civil tort

 International Espionage – Government support

 Other policy violation – evidence support

</td></tr><tr><td>

Notification Role

 Government: Public Affairs Officer

 Corporate: Media Liaison

 Academic: University media relations office

</td><td>

Various parties may require notification. Internal parties include management, HR, Legal, public relations, system, or business owner who is responsible for the affected system(s). Use caution, depending on type, because the attacker may be an insider.

 Always follow “need to know” principle.

 Log notifications in the IR document.

 Remain factual and avoid speculation.

</td></tr><tr><td>

Immediate action

</td><td>

“Stop” the attacker through some form of access control technique. For example, disable affected account(s), change account passwords, implement a router ACL, or create a firewall block rule.

 Avoid changing volatile state data or the system state early on. Once volatile information is collected, then system changes can occur based on business priority.

 Maintain low profile - avoid any tip off.

</td></tr><tr><td>

Initial data collection: what to gather early

</td><td>

Collect network trace, logs, system volatile info, and memory image.

 If needed, make a forensic disk copy for later or parallel analysis. This process may interrupt the environment based on forensic capabilities. Always confirm with the business on down time windows.

</td></tr><tr><td>

Immediate isolation

</td><td>

System or network segment isolation may be necessary. Pulling the plug sacrifices volatile data. Be cautious about damage to applications and databases. Pulling the plug is not the standard today. Rather, memory image and online disk image, then targeted shutdowns to avoid data loss.

</td></tr><tr><td>

Longer term actions

</td><td>

If the system cannot be taken offline, many actions are possible, but must be fully documented based on a valid business case. For example, network monitoring activity can occur in parallel post initial perimeter containment while the IR team continues with the Eradication step and a hardened replacement system is brought up.

</td></tr><tr><td>

Key decisions

</td><td>

1.  Case specific best method to stop intruder (attacker, malware) and control the situation

 2.  What is the risk to continuing operation?

 3.  What actions are necessary to mitigate?

</td></tr><tr><td>

Containment step exit criteria

</td><td>

The attackers’ ability to affect the network is effectively stopped.

 The affected system(s) are identified.

 Compromised systems volatile data collected, memory image collected, and disks are imaged for analysis.

</td></tr></tbody></table>  

Step Four: Eradication

 <table><tbody><tr><td>

Eradication Step (Clean Up)

</td><td>

Key activity: remove attacker’s presence from the environment

</td></tr><tr><td>

Root Cause Identification (RCI)

</td><td>

Using identification and containment information, determine root cause, and execution path to remove the attacker.

</td></tr><tr><td>

Determine rootkit potential

</td><td>

Rootkits modify the system by lying to the user. Hence, the system is not trustable. If a rootkit is suspected, wipe the disk, reformat, and restore from most recent ‘clean’ backup. Then update the system and applications, patch the OS, and otherwise harden necessary services. Once these sub steps are completed, return the system to production.

</td></tr><tr><td>

Improve defenses

</td><td>

Improve perimeter, DMZ, network, OS and application findings - everywhere

</td></tr><tr><td>

Perform vulnerability analysis

</td><td>

Perform network wide VA scan. Search for other potential weaknesses and remediate. Follow a high to low priority.

</td></tr><tr><td>

Key decisions

</td><td>

Has the environment been hardened to reduce a potential recurrence?

</td></tr><tr><td>

Eradication step exit criteria

</td><td>

The IR team and the business are confident that network and systems are configured to eliminate a repeat occurrence.

</td></tr></tbody></table>  

Step Five: Recovery

 <table><tbody><tr><td>

Recovery Step (Return to Normal)

</td><td>

Key activity: return validated system(s) to operation

</td></tr><tr><td>

Validation

</td><td>

Verify systems, applications, and databases are operating; no signs of compromise

</td></tr><tr><td>

Restore operations

</td><td>

Coordinate the restore operation time window with the business

</td></tr><tr><td>

Implement Monitoring

</td><td>

There are many opportunities to “monitor” the system for repeat events.

 For example, specific Snort IDS rules, OS integrity check tools, increase router logging, configure supplemental system and application logging, or automate a security point system.

 Also, new alerts within the SIEM system.

</td></tr><tr><td>

Key decisions

</td><td>

Any sign of repeat events?

</td></tr><tr><td>

Recovery step exit criteria

</td><td>

No evidence of repeat events or incidents

</td></tr></tbody></table>  

Step Six: Lessons Learned (or Follow Up)

 <table><tbody><tr><td>

Lessons Learned Step (Communicate)

</td><td>

Key Activity: document event, actions, and remediation plan (samples later)

</td></tr><tr><td>

Write follow up report, conduct

 Lessons Learned meting

</td><td>

IR team works up full report of the event, reviews with the relevant subject matter experts and business, gain signature on follow up recommendations.

</td></tr><tr><td>

Key Decisions

</td><td>

Is management satisfied the incident is closed?

</td></tr><tr><td>

Lessons Learned Exit Criteria

</td><td>

Management is satisfied the incident is closed.

 There is an action plan to respond to operational issues which arose from this incident. For example, instrumentation, logging, or helpdesk procedures.

</td></tr></tbody></table>
