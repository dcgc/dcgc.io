---
layout: page
title: DevOps
categories: notes
permalink: /devops/
---

Requirements:

- DevOps
- Cloud Computing: Azure
- Experience with Metrics: Grafana, Prometheus
- Experience with Logging: Splunk
- Experience with Tracing: Jaeger, OpenTracing, OpenCensus
- Strong understanding of Site Reliability Engineering (SRE) concepts
- Understanding of SLIs, SLOs and SLAs from the service level to the business level
- Understanding of various types of proactive monitoring needs of production systems including infrastructure monitoring, synthetic monitoring & application performance monitoring
- Experience with APM: Dynatrace, New Relic, App Dynamics, DataDog to analyze application performance
- Agile methodologies such as Scrum with focus on Continuous Integration and Deployment
- Good understanding of data architecture concepts
- Software documentation (Confluence)
- Project Management Tool (Jira)
- Excellent planning and communication skills
- Team player with willingness to collaborate

# Prelude to DevOps - the Need for Speed

Competition and business innovation is driving the need for speed:
- First to market, short product cycles, fail early - rapid iteration, feedback
- Large Waterfall projects with heavy upfront planning - too slow, expensive
- Formal IT change control to manage risk - even slower, more expensive
Speed is critical for security too:
- Security needs to identify and respond to new attacks and threats quickly
- Slow change means Vulnerability Windows are left open for too long
Agile and Lean development - deliver faster, more often but…
- Smaller teams, smaller projects, more results-focused and iterative
- Fast-moving Agile/Lean teams run into a roadblock at IT Operations
	
In business, success is often about slashing the time it takes from having a brilliant idea and getting it into the hands of customers before a competitor does — or finding out that the brilliant idea wasn’t actually good at all, and coming up with another, better idea or canceling it before the business loses too much money or customers (“fail early“). This drives product and service development to become faster and more responsive, more agile.

Heavyweight Waterfall software development has been giving way to lighter-weight, incremental Agile development approaches for some time now. Agile development methods like Scrum have become extremely popular, as organisations look for ways to speed up delivery of software products and reduce the risk of
software development project failures.

But last-moving Agile teams— and the business Product Owners who are sponsoring their work and driving their priorities have become frustrated with delays in getting completed software into production and into the hands of users. In many cases, they are creating working software faster than operations can accept it. Operations have become a roadblock to business progress.

The inability of development and operations to turn around changes quickly creates other problems for many organisations when it comes to security. Security vulnerabilities are often left open for too long even though
most security patches are simple to fix and implement. This gives attackers more opportunities to find and exploit vulnerabilities.

IT, which includes security specialists, developers, and operations, has to look at the complete value chain, from when an idea is created or a problem is found, so, when it gets delivered to production. They need to find ways to make learning and change easier, faster and cheaper to try out new ideas and to fix problems, without introducing new bugs or causing outages. This is what DevOps tries to achieve.

# Walls of Confusion

Organisational and cultural barriers exist in most organisations between development and operations — in addition to barriers between the rest of the organisation and the lnfoSec and compliance groups. These are known as the “Walls of Confusion“. People on opposite sides of the wall have different goals and priorities and competing incentives, use different tools and follow different practices, speak different languages, and often have completely different cultures:

- Development: rapid delivery of features = Agile and Lean methods, small co-located teams, Continuous Integration, sticky notes on a wall

- Operations: firefighting vs. stability and efficiency = ITIL, standardisation of technology, configuration
management, ticketing systems

- Security and Compliance: managing vulnerabilities, evidence of controls = stage gates, point-in-time audits, pen testing, spreadsheets, and checklists

# Take down Walls of Confusion

- Agile: break down the barriers between development and the business/customer

- DevOps: break down the barriers between development and operations

- DevOpsSec: break down barriers with security and compliance

DevOps breaks down the ”walls of confusion”, the communications and cultural barriers between developers and operations. in the same way that Agile development tries to break down communications barriers between the business and developers. Getting rid of hand-offs and discontinuities between organisations, as well as the
inefficiencies and misunderstandings and conflicts that come with a “throw it over the wall" style hand-off.

These walls of confusion are broken down by building cross-functional teams which own responsibilities for a service, from requirements and planning through to design, construction, deployment, and running in production. In some organisations, this might mean embedding Operations engineers and InfoSec professionals into development teams, or permanently flattening development and operations, and restructuring the organisation around end-to-end service delivery instead of functional lines.

Another important step in breaking down these walls is by getting developers, testers, and operations to share common tools: for tracking problems, for managing source code and configuration information, for collaboration and messaging…

DevOpsSec is about extending this to include security and compliance - so that security and compliance are not imposed from outside.

# Basics of DevOps - Agility and Collaboration

Extend Lean and Agile ideas, practices and values to operations
- Cross-functional, collaborative teams
- Lightweight practices and face-to-face discussion over paperwork
- CI/CD - extend Continuous Integration, deliver changes to directly to production using automated pipelines
- Identify and eliminate delays and bottlenecks - fast and effective is what counts
- Get feedback from productive use - not about projects - constant change and learning, iteratively drive design decisions.

DevOps is about developers and operations working closely together to make rapid. iterative changes to systems quickly and inexpensively. This includes changes to applications and rapid provisioning and configuration of infrastructure - in public or private clouds.

DevOps is based on a few key ideas:

- Extending Agile values and practices from development to operations: iterative incremental change, automated testing, collaboration, introspection, and continuous improvement.

Cross-functional teams involving development, operations, and lnfoSec: breaking down the “walls of confusion“ between these groups, getting them to work closer together, and sharing end-to-end responsibility for getting changes into production 8:, ensuring that they work correctly.

- Continuous Delivery and Continuous Deployment: building on Agile Continuous Integration to automatically move changes to production.

- Infrastructure as Code: software-defined configuration changes to infrastructure, using tools like Puppet, Chef, CFEingine, Saltstack, or Ansible.

- Metrics drive change and improvement: use data from production to understand what works, what doesn‘t, what needs to be improved. An emphasis on experimentation and metrics-driven feedback.

Agile development teams, once they start moving fast and iterating, often run into a roadblock in operations when it comes to deploying the new features that they‘ve developed. This roadblock prevents them from getting meaningful feedback and creates artificial delays delivering value.

DevOps extends Agile and Lean ideas and ways of working into operations: small learns collaborating to solve problems in an open environment, working iteratively and incrementally; minimising waste and delay; and leveraging automation to solve operations problems such as provisioning, configuring, hardening, updating, and patching infrastructure.

# Basics of DevOps - Shared Ownership and Accountability

Development and Operations share end-to-end of systems:
- No hand off from development team to operations: “You Build It, You Run it”
- Developers on call, and developers in production
- NoOps - leverage cloud platform services and APIs (Netflix model)
- Monitoring and metrics - use data to increase transparency and drive decision making (data science, experiments)
- Post Mortems and Shared Learning/Improvement - honesty and trust, learn from mistakes.

“You build it. you run it“ (than Amazon‘s CTO Werner Vogels).

In some cases. for example at Netflix. which leverages Amazon‘s AWS for its operational platform. developers are effectively responsible for all of the work of setting up, deploying, running, monitoring and supporting the applications that they develop. This is what Netflix calls ”NoOps“.

High velocity and low cost of change enables DevOps organisations to run continuous experiments, respond to customers, pivot quickly:

- High-performing DevOps organisations deploy 46x more frequently, with 440x shorter lead times (<1 hour vs <1 month).

- Velocity of delivery is increasing year over year: even low performers shipping between once per week and once per month now on average (instead of once per every 1-6 months in 2016).

- High-performers recover from failures 96x faster.

- DevOps leaders spend 50% less time remediating security issues.

- Also leads to higher employee satisfaction: 2x more likely to recommend their employer as a great place to work.

DevOps Security is not priority:
- Only 20% do security in development/delivery.
- 38% still depend on pen testing or other pre-production gate reviews.
- 25% rely on network defenses.
- 17% are doing nothing for security.

Security is someone ele’s problem:
- DevOps is bringing developers, testers and ops together, but not security.

DevOps is not:
- prescriptive recipe
- position or job
- tool or product
- running systems in the cloud
- end-run around supported IT processes
- the same in every org

DevOps is not just about running systems in the cloud although DevOps has changed and is changing the way that systems are run in the cloud. It is not about creating “DevOps teams“ or adopting a “DevOps” toolset (which is how many yendors are repackaging IT configuration management and release management products).
