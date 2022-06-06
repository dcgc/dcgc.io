
Day 1
- Product demo - Thomas G.
	- Third party pieces?
	- Fraud and Compliance module is optional
    	- Fircosoft 3rd party
	- Qliksense - 3rd party - working on fedramp
    	- Isn’t mandatory
    	- Verify info going to Qlik? Any at all
	- Session inactivity -30 minutes default - logoff - configureable for the customer
- How many people have access to the back end? (Support, product managers, external partners, etc.)
- Support portal - needs deeper dive
- Do we need to use DCs other than AWS? Prefer not to because of additional requirements and scope - Bobby investigating
- Can they use existing management plane or does it need to be separate?
- DNS provider? Verify (DNSmadeeasy.com)
- CentoS not supported due to FIPS…use Redhat instead, possible Amazon Linux2 in FIPS mode
- Possible issues with redhat according to Olivier from years ago trying it
- Stable architecture, change to containers needs to be discussed, take significant changes into consideration
- Discussion on the version where we build this app due to changes triggering significant
- AWS piece, get started on now? Bobby
- Keycloak usage or AD
- Waiver for comms with banks because banks use old tech not FIPS compliant, what banks are we connecting too?
- Google Fedramp version because of inbound email to the Kapp
- DNS must be DNSSEC by fedramp mandate
- If Army sponsors, what are their requirements?
- If it turns out we need to go minimal function on Kapp, then we need to go with Army requirements to get AO

Day 2
- Have to use DISA STIG instead of CIS level 1 because of Army DOD
- JIRA not fedramp, ServiceNow does have a fedramp version
- Users must be identified via username if they are contractors or foreign nationals for DoD
- Okta and google workspace to extend boundary because of Okta use
- Banner needed for all login points
- Chris to find out from Army how they are handling treasury
- Bank connections for Army and other customers
- Army doesn’t in-house payment, may not need SWIFT
- No Fireapps at this point
- PCC change process will need to be more rigorous
- SoD doc we can send. Check to see
- Document all ports into and out of secure zone monthly

Day 3
- Max.gov site registration
- 3 months before 3PAO assessment so we can show evidence of work
- Show remediation as well before assessment
- No high findings going into assessment
- No spam protection for google account for Kapp other than Googles built-in protection
- Who owns the google account for Kapp?
- NTP sources? Bobby checking
- Maintain audit logs for 1 year, 90 days online, 1 year offline
- Application logging - loginsight, is it fedramp ready?
- FIPS140-2 within boundary, incoming and outgoing connections
- All comms within the boundary must be encrypted
- IR Training - content? Incident spillage training? Both components
- Report to US-CERT for fedramp

Day 4
- Prioitize incident response training in addition to roles based trading
- Timeline is important for training and fedramp within 10 days and annually
