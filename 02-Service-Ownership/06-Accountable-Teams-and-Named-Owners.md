# Accountable Teams and Named Owners

> Durable service ownership belongs to an accountable team. Named individuals make communication and coordination possible, but the organization must preserve ownership when people sleep, take leave, change roles, or leave the organization.

## Section Purpose

A production service needs more than a username in a repository, a name in a spreadsheet, or the person who remembers how it works.

It needs a durable ownership arrangement that answers:

- Which team remains accountable for the service outcome?
- Which person currently coordinates technical ownership?
- Which business owner can make or escalate business decisions?
- How can another team reach the owner?
- Who provides backup when the primary contact is unavailable?
- Which specialists hold important knowledge?
- What happens during leave, transfer, reorganization, or staff turnover?
- How is the record verified?
- Which contact information is safe to publish?

This section establishes teams as the durable ownership unit and people as named role holders within that unit.

The practical output is an accountable-owner record.

This section identifies accountable parties and continuity requirements. It does not fully define decision rights, on-call design, escalation policies, service catalogs, or ownership transfer. Later sections address those subjects in depth.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain why durable ownership should rest with a team.
2. Define an accountable team for a production service.
3. Distinguish the accountable team from technical, business, and contact roles.
4. Define primary and secondary contacts without making one person the service owner.
5. Record subject-matter expertise without creating permanent dependency on specialists.
6. Identify the risks of individual ownership.
7. Design continuity for leave, staff turnover, and organizational change.
8. Establish time-bounded temporary ownership.
9. Verify that an ownership record represents a working capability.
10. Prevent ownership records from depending on outdated usernames.
11. Protect personal and internal information in public repositories.
12. Produce a complete accountable-owner record.

---

## 1. The Durable Ownership Principle

Every production service should have one clearly accountable team.

That team remains answerable for the service across:

- Normal operation
- Planned change
- Degradation
- Incidents
- Recovery
- Maintenance
- Organizational change
- Deprecation
- Retirement

Named people may perform particular duties. The accountable team preserves the obligation when those people change.

A durable ownership statement is:

> The Payments Reliability team is accountable for the payment authorization service. The current technical owner and contacts are recorded as role holders and reviewed regularly.

A weak statement is:

> Ask Jordan. Jordan built it.

The first creates organizational continuity. The second creates personal dependency.

---

## 2. What Accountability Means

Accountability is continuing answerability for an outcome.

For a service, the accountable team must ensure that somebody can:

- Explain the service purpose and users
- Maintain ownership information
- Understand important dependencies
- Coordinate reliability work
- Support production decisions
- Participate in incidents
- Maintain recovery capability
- Escalate unresolved risk
- Preserve operational knowledge
- Manage the service through its lifecycle

Accountability does not mean that the team performs every task itself.

Platform, security, database, network, product, vendor, or support teams may contribute. Those contributions do not remove the need for one team to remain answerable for the service outcome.

---

## 3. Team Accountability Versus Individual Responsibility

| Concept | Meaning | Example |
| --- | --- | --- |
| Team accountability | Continuing answerability for the service | Identity Services team owns authentication |
| Individual responsibility | Assigned work performed by one person | Engineer updates the recovery procedure |
| Role ownership | A defined responsibility attached to a role | Technical owner coordinates architecture decisions |
| Contact designation | A route for communication | Primary contact receives non-urgent ownership questions |
| Expertise | Specialized knowledge about part of the service | Database specialist advises on replication |

One person may hold several roles. The record must still distinguish them.

The person responsible for an action is not automatically the accountable owner of the complete service.

---

## 4. Why the Team Is the Ownership Unit

Production services usually outlive individual assignments.

Teams provide:

- Multiple people who can learn the service
- Coverage across working hours and leave
- A place for work to be prioritized
- Management and staffing responsibility
- Knowledge transfer
- Peer review
- Continuity during turnover
- A stable organizational identity

A team can still fail as an owner. A team name alone proves nothing.

The team must have knowledge, authority, staffing, access, and operational capacity appropriate to the service tier.

---

## 5. One Accountable Team

A service should have one accountable team at a given point in time.

Many teams may contribute, but phrases such as these are unsafe:

- Jointly owned by everyone
- Shared between five teams
- Owned by engineering
- Owned by whoever is on call
- Owned by the cloud team and application team

Shared work is normal. Split answerability is not.

When ownership spans several teams, record:

1. The team accountable for the end-to-end service outcome.
2. The teams accountable for defined components or capabilities.
3. The boundaries between them.
4. The escalation path for disputes and gaps.

---

## 6. Accountable Team

The accountable team is the durable organizational group answerable for the service throughout its lifecycle.

The record should include:

- Canonical team name
- Stable team identifier
- Organizational unit
- Team manager or accountable lead role
- Team contact channel
- Support route
- Service relationship
- Effective date
- Review date
- Evidence of acceptance

Prefer a stable team identifier over a display name alone. Team names can change during reorganizations.

---

## 7. Accountable Team Capabilities

An accountable team should be able to demonstrate:

- Service knowledge
- Access to relevant source and configuration
- Access to production evidence appropriate to its role
- Authority to request or make necessary changes
- Ability to coordinate incident response
- Ability to obtain specialist support
- Maintained operating documentation
- Recovery knowledge
- Work prioritization
- Sufficient staffing
- Continuity arrangements

If the named team cannot influence the service, it is a directory entry, not a functioning owner.

---

## 8. Accountable Team Acceptance

Ownership should not be assigned silently.

The receiving team should acknowledge:

- The service boundary
- The service lifecycle state
- The criticality tier
- Known obligations
- Known risks
- Required access
- Current documentation
- Outstanding gaps
- Effective date

Acceptance may be recorded through an approved ownership record, service-catalog workflow, or other controlled mechanism.

A manager should not assign a critical service to a team that lacks the capacity to operate it without also recording and funding the remediation plan.

---

## 9. Technical Owner

The technical owner is the named role responsible for coordinating the technical stewardship of the service.

Typical responsibilities include:

- Maintaining technical context
- Coordinating architecture decisions
- Confirming operational documentation
- Identifying technical risks
- Connecting specialists and delivery teams
- Supporting readiness and lifecycle reviews
- Ensuring unresolved gaps reach the accountable team

The technical owner is not necessarily:

- The original author
- The most senior engineer
- The repository administrator
- The permanent incident commander
- The only person allowed to change the service
- Personally accountable for every failure

The accountable team remains the durable owner.

---

## 10. Technical Owner Selection

A technical owner should have:

- Sufficient service knowledge
- Time to perform the role
- Access to relevant information
- A clear relationship with the accountable team
- Authority to coordinate technical work
- Ability to identify when specialist review is required
- A named substitute

Do not select a technical owner only because that person created the service years ago.

Current knowledge, authority, availability, and team membership matter more than historical association.

---

## 11. Technical Owner Is a Role, Not a Hero

The role should improve coordination without concentrating all knowledge.

Unsafe signals include:

- Only one person can deploy
- Only one person understands the data model
- Every incident waits for the technical owner
- Reviews stop during the person's leave
- Documentation exists only in private notes
- Other engineers avoid learning the service

A good technical owner makes the team less dependent on any one person.

---

## 12. Business Owner

The business owner represents the organizational outcome, obligation, or risk supported by the service.

Depending on the service, the role may be held by:

- Product leadership
- Business process ownership
- Operational leadership
- Data ownership
- Risk ownership
- An internal service sponsor

Typical responsibilities include:

- Confirming the business purpose
- Explaining critical user or business outcomes
- Participating in criticality decisions
- Confirming contractual or regulatory context
- Prioritizing business tradeoffs
- Escalating resource or risk decisions
- Supporting deprecation and retirement decisions

The business owner does not replace technical accountability.

---

## 13. Business Owner for Internal Technical Services

An internal platform or infrastructure service may not have a traditional product owner.

It still needs an organizational sponsor or outcome owner who can answer:

- Why does this capability exist?
- Which teams depend on it?
- What harm follows from failure?
- Which investment level is justified?
- Who can accept business consequences?
- Who can approve retirement?

Calling a service purely technical does not remove business consequences.

---

## 14. Technical and Business Ownership Must Connect

Technical and business owners view different parts of the same service.

| Technical owner contributes | Business owner contributes |
| --- | --- |
| Architecture and failure evidence | User and business consequence |
| Dependency and recovery knowledge | Priority and risk context |
| Technical feasibility | Business timing and obligations |
| Engineering recommendations | Authorized business decisions |
| Implementation coordination | Sponsorship and escalation |

Neither role should make decisions outside its authority.

The accountable team should know how to reach the business owner when technical risk requires a business decision.

---

## 15. Primary Contact

The primary contact is the normal entry point for ownership communication.

The primary contact may be:

- A team channel
- A role mailbox
- A service desk queue
- A named coordinator
- A service-catalog contact route

Prefer a durable team route as the main contact. A named person may be listed as the current coordinator.

The primary contact should not be confused with the emergency incident route.

---

## 16. Secondary Contact

The secondary contact provides a verified alternative when the primary route is unavailable, inappropriate, or unresponsive.

The secondary contact should:

- Belong to or formally support the accountable team
- Understand when to respond or escalate
- Have access to the ownership record
- Be reviewed with the primary contact
- Avoid sharing the same single point of failure where possible

For example, two individual email addresses in the same time zone do not provide meaningful continuity for a global critical service.

---

## 17. Contact Routes by Purpose

One address rarely fits every need.

| Purpose | Appropriate route |
| --- | --- |
| General ownership question | Team channel or role mailbox |
| Planned integration | Intake queue or technical contact |
| Security concern | Approved security reporting route |
| Active production incident | Operational escalation route |
| Business decision | Business owner or delegated role |
| Data request | Approved data governance route |
| Public inquiry | Public support or security contact |

Do not publish an internal emergency number as a general contact.

---

## 18. Subject-Matter Experts

A subject-matter expert, or SME, provides deep knowledge about a defined area.

Examples include:

- Database replication
- Identity protocols
- Network routing
- Cryptographic key management
- Regulatory reporting
- Capacity behavior
- Vendor integration
- Legacy runtime behavior

SMEs support the accountable team. They do not automatically own the service.

---

## 19. Record Expertise by Domain

Do not create one undifferentiated list of experts.

Record:

- Expertise domain
- Person or team
- Expected contribution
- Contact route
- Availability constraints
- Backup specialist
- Knowledge source
- Last verification date

This prevents teams from contacting a database expert for an application policy decision or treating a former contributor as the complete service owner.

---

## 20. Specialist Dependency Risk

SME records can reveal concentration risk.

Warning signs include:

- One specialist supports many critical services
- No second person understands the technology
- The specialist sits outside the accountable organization
- Access depends on a personal account
- The specialist is not part of incident preparation
- Knowledge exists only through memory
- Contractual availability is unclear

The response may include pairing, documentation, training, access review, vendor support, or replacement of an unsustainable dependency.

---

## 21. Individual Ownership Risks

Assigning a service to one person creates predictable failure modes.

These include:

- Absence during an incident
- Loss of knowledge during turnover
- Unreviewed decisions
- Excessive cognitive load
- Unsafe production access concentration
- Delayed changes
- Burnout
- Informal procedures
- Hidden risk acceptance
- Personal blame for system conditions
- Inability to provide sustained coverage

Individual commitment is valuable. Individual dependency is unsafe.

---

## 22. The Bus-Factor Test

A practical continuity question is:

> How many people can become unavailable before the team can no longer operate or recover this service?

Do not treat the answer as a vanity number.

Evaluate specific capabilities:

| Capability | People able to perform it | Evidence |
| --- | ---: | --- |
| Explain architecture |  |  |
| Deploy safely |  |  |
| Roll back |  |  |
| Diagnose common failure |  |  |
| Restore data |  |  |
| Rotate critical credentials |  |  |
| Contact dependencies |  |  |
| Retire the service |  |  |

The team may have broad knowledge in one area and a dangerous single point of failure in another.

---

## 23. Team Continuity

Team continuity means preserving ownership capability as people and structures change.

It requires:

- Shared service knowledge
- Documented roles
- Named substitutes
- Reviewed access
- Team-owned communication routes
- Maintained operational artifacts
- Regular exercises
- Workload capacity
- Planned handover
- Management oversight

Continuity is an operating capability, not a document stored after onboarding.

---

## 24. Minimum Knowledge Distribution

The required knowledge distribution should match service criticality.

For a high-criticality service, several people should be able to:

- Explain the critical user outcome
- Identify major dependencies
- Interpret key production evidence
- Perform safe mitigation
- Use recovery procedures
- Escalate business and security concerns
- Verify restored behavior

Lower-tier services may use lighter arrangements, but no production service should depend on an unreachable former employee.

---

## 25. Team-Owned Access

Production capability should not depend on personal ownership of:

- Cloud accounts
- DNS registrations
- Source repositories
- Package registries
- Certificates
- Encryption keys
- Vendor accounts
- Monitoring systems
- Deployment credentials
- Backup locations

Use organization-managed accounts, role-based access, controlled recovery procedures, and auditable administration.

Named people may receive access through approved roles. They should not personally own the production asset.

---

## 26. Team-Owned Documentation

Operational knowledge should live in an approved, discoverable location accessible to the accountable team.

Avoid:

- Personal drives
- Private chat history
- Unshared notebooks
- Links tied to one employee account
- Unversioned local files
- Documentation only a former contractor can edit

The record should identify the maintained source for architecture, operations, recovery, and service ownership information.

---

## 27. Ownership During Planned Leave

Before planned leave, a role holder should transfer active responsibilities.

The handover should cover:

- Substitute role holder
- Active incidents or investigations
- Planned changes
- Current risks
- Time-sensitive obligations
- Pending decisions
- Required access
- Relevant contacts
- Return date

The accountable team does not change merely because the technical owner is on leave.

---

## 28. Ownership During Unplanned Absence

The team should not require a handover to survive an unexpected absence.

Controls include:

- Secondary contacts
- Shared documentation
- Role-based access
- Team queues
- Maintained escalation routes
- Cross-trained responders
- Manager awareness
- Periodic recovery exercises

If an unexpected absence makes the service unmanageable, the ownership model was already incomplete.

---

## 29. Ownership During Staff Turnover

When a role holder leaves, the team should trigger an ownership continuity review.

Review:

- Role reassignment
- Access removal
- Credential rotation where required
- Pending approvals
- Open risk decisions
- Documentation gaps
- Private knowledge or files
- Vendor relationships
- Repository permissions
- Emergency contacts
- Ownership record accuracy

Offboarding should not simply delete the username and leave the field blank.

---

## 30. Knowledge Transfer During Turnover

Knowledge transfer should produce evidence.

Useful evidence includes:

- Updated service overview
- Recorded walkthrough
- Reviewed architecture map
- Successful deployment by another engineer
- Recovery exercise
- Access validation
- Open-risk register
- Dependency contact confirmation
- Acceptance by the new role holder

A meeting called handover is not proof that another person can operate the service.

---

## 31. Ownership During Reorganization

An organizational change can invalidate hundreds of records at once.

A reorganization plan should identify:

- Services moving between teams
- Services remaining with renamed teams
- Split or merged teams
- New management ownership
- Contact-route changes
- Access changes
- Capacity gaps
- Conflicting claims
- Orphan risks
- Effective dates

Do not assume that moving a repository automatically transfers service accountability.

---

## 32. Team Rename Versus Ownership Transfer

A team rename changes the label of an existing owner.

An ownership transfer changes the accountable team.

The distinction matters because a transfer requires:

- Scope agreement
- Capability review
- Acceptance
- Access changes
- Knowledge transfer
- Risk acknowledgement

A stable team identifier helps distinguish a rename from a true transfer.

---

## 33. Temporary Ownership

Temporary ownership is a time-bounded accountability arrangement used while a durable owner is established or restored.

Possible reasons include:

- Organizational transition
- Acquisition integration
- Incubation
- Emergency reassignment
- Team dissolution
- Pending service retirement

Temporary ownership must never mean nobody owns it yet.

---

## 34. Requirements for Temporary Ownership

A temporary ownership record should include:

- Temporary accountable team
- Reason
- Start date
- Expiry date
- Required obligations
- Known limitations
- Risk owner
- Permanent-owner plan
- Review cadence
- Escalation authority
- Exit criteria

An expiry date without a transition plan only predicts the next ownership gap.

---

## 35. Temporary Owner Authority

The temporary owner needs enough authority to keep the service safe.

It must be clear whether the team may:

- Approve changes
- Restrict changes
- Mitigate incidents
- Request engineering work
- Access recovery systems
- Escalate risk
- Begin retirement

Temporary accountability without authority creates delay and hidden risk.

---

## 36. Preventing Permanent Temporary Ownership

Controls should detect temporary arrangements that never end.

Use:

- Expiry alerts
- Mandatory periodic review
- Leadership visibility
- Named permanent-owner candidate
- Tracked remediation work
- Restrictions on indefinite extension
- Formal exception approval

Repeated extensions indicate an organizational decision that should be made explicitly.

---

## 37. Orphaned Services

An orphaned service has no functioning accountable team.

Signals include:

- Owner field is empty
- Owner is a departed employee
- Named team no longer exists
- Every contacted team denies ownership
- No team can access production
- No team accepts the operational obligations
- Service remains active after its project ended

An orphaned service is a production risk, not a catalog-cleanup problem.

---

## 38. Handling an Orphaned Service

When an orphan is found:

1. Confirm that it still runs or affects production.
2. Identify users and dependencies.
3. Determine criticality and current exposure.
4. Assign an authorized temporary accountable team.
5. Restrict unsafe change if necessary.
6. Restore minimum access and documentation.
7. Decide on permanent ownership, transfer, or retirement.
8. Record the decision and evidence.

Do not assign the service to the person who discovered it without authority and acceptance.

---

## 39. Ownership Verification

Ownership verification confirms that recorded owners still exist, accept the role, and can perform it.

Verification should answer:

- Does the team exist?
- Does the team acknowledge accountability?
- Are the contacts reachable?
- Are named role holders current?
- Can the team access required systems?
- Does the team understand the service?
- Can it locate operational and recovery information?
- Does it know the service tier and obligations?
- Are gaps recorded and owned?

---

## 40. Verification Is More Than Confirmation

Sending a message that asks, Are you still the owner, produces weak evidence.

A stronger review samples capability.

For example:

- Contact route receives and answers a test request
- Team identifies the service purpose and boundary
- Another engineer locates the runbook
- Access is checked
- Recovery responsibility is named
- Current risks are reviewed
- Team confirms acceptance

The depth of verification should match the service tier.

---

## 41. Verification Cadence

Set a maximum review interval by criticality and change rate.

Example policy:

| Service condition | Suggested maximum interval |
| --- | --- |
| Tier 0 | Quarterly and after material change |
| Tier 1 | Every six months and after material change |
| Tier 2 | Annually and after material change |
| Tier 3 | Annually or on lifecycle review |
| Tier 4 | On lifecycle review and before continued production use |
| Temporary owner | Monthly or before expiry |

These are governance examples, not universal requirements.

---

## 42. Event-Driven Verification

Do not wait for the calendar when ownership may have changed.

Trigger review after:

- Team reorganization
- Manager change
- Technical owner departure
- Business owner departure
- Service transfer
- Criticality reclassification
- Acquisition
- Major architecture change
- Vendor replacement
- Ownership dispute
- Failed escalation
- Incident exposing an ownership gap
- Deprecation or retirement decision

---

## 43. Verification Evidence

Record:

- Verification date
- Reviewer
- Method
- Team acceptance
- Contact test result
- Access result
- Documentation result
- Gaps found
- Remediation owner
- Due date
- Next review date

Avoid recording verified without explaining what was checked.

---

## 44. Failed Verification

Failed verification requires action proportional to risk.

Possible actions include:

- Correcting contact information
- Assigning a substitute
- Restoring access
- Escalating an ownership dispute
- Naming a temporary owner
- Restricting change
- Scheduling knowledge transfer
- Reclassifying lifecycle state
- Retiring the service

A failed ownership check on a critical service should not remain an administrative ticket with no production consequence.

---

## 45. Preventing Ownership by Outdated Usernames

Usernames are identifiers, not durable ownership models.

They become unsafe when:

- The person leaves
- The account is renamed
- The identity provider changes
- The account is suspended
- A contractor engagement ends
- A personal account owns organizational assets
- The username is reused

Record the accountable team first. Treat individual usernames as current role-holder references only.

---

## 46. Stable Identifiers

Use identifiers that survive ordinary changes.

Useful fields include:

- Service identifier
- Team identifier
- Organization identifier
- Role identifier
- Current identity-provider subject for access systems
- Effective and end dates

Display names help people read the record. Stable identifiers help systems maintain relationships.

Never expose internal identifiers publicly without reviewing their sensitivity.

---

## 47. Role Addresses and Team Channels

Durable routes may include:

- Team email aliases
- Role mailboxes
- Managed chat channels
- Service desk queues
- Catalog-based contact actions
- Approved paging services

Each route needs an owner, membership process, and test method.

An abandoned group mailbox is no better than an outdated username.

---

## 48. Contact Route Lifecycle

Contact routes also need lifecycle management.

Review:

- Membership
- Moderation
- Delivery behavior
- External access
- Retention
- Escalation behavior
- Ownership
- Decommissioning

When a team changes, update contact routes as part of the same change, not as later cleanup.

---

## 49. Repository Ownership Files

Repository files such as `CODEOWNERS` can support code review and routing.

They do not prove complete service ownership.

A repository ownership file may tell you:

- Who reviews paths
- Which team maintains code
- Which group approves changes

It may not tell you:

- Who owns the runtime service
- Who owns data and dependencies
- Who handles incidents
- Who can recover production
- Which business owner accepts consequences
- Whether one repository supports several services

Use repository ownership as evidence within the broader service record.

---

## 50. Public Repository Privacy Considerations

Public repositories require a reduced public contact model.

Do not publish sensitive details such as:

- Personal phone numbers
- Private email addresses
- Employee schedules
- Internal paging endpoints
- Private chat channels
- Incident bridge links
- Escalation trees
- Organizational identifiers that reveal sensitive structure
- Vendor account identifiers
- Production account names
- Security control details
- Staff leave information

Public transparency does not require operational exposure.

---

## 51. Safe Public Ownership Information

A public repository can usually publish:

- Maintainer team or project name
- Public contribution route
- Public support route
- Approved security reporting policy
- Public governance information
- Generic organization contact
- Links to public documentation

Keep detailed operational ownership in an access-controlled system.

---

## 52. Separate Public and Internal Records

Use two views when necessary.

### Public View

Contains information appropriate for contributors and users.

### Internal Operational View

Contains named role holders, internal contacts, escalation routes, access evidence, coverage details, and risk information.

The public view may reference the existence of an internal owner record without exposing it.

---

## 53. Security Reporting

Public projects should provide a controlled security reporting route.

Prefer:

- A `SECURITY.md` policy
- A monitored security mailbox
- A vulnerability-reporting platform
- Clear response expectations

Do not direct vulnerability reports to an individual's social account or publish an internal emergency route.

---

## 54. Personal Data Minimization

Collect only the personal information required for the ownership purpose.

Ask:

- Is a person's name necessary?
- Could a role or team address work instead?
- Who can see this field?
- How long should it remain?
- How will it be removed after a role change?
- Does local privacy policy restrict publication?

Ownership discoverability should not become uncontrolled staff profiling.

---

## 55. Contractors and External Providers

A contractor or vendor may perform important work, but organizational accountability should remain explicit.

Record:

- Internal accountable team
- Vendor responsibility
- Contract owner
- Support route
- Coverage commitment
- Access boundaries
- Escalation process
- Exit and knowledge-transfer requirements

The vendor contact should not be the only owner recorded for an organizational service.

---

## 56. Open Source Maintainers and Production Owners

An open source maintainer owns or governs a software project.

The organization that deploys that software owns its production use.

Upstream maintainers are not accountable for:

- Your configuration
- Your deployment
- Your data
- Your capacity
- Your dependency choices
- Your incident response
- Your recovery plan

Record upstream support as a dependency, not as the accountable production team.

---

## 57. Ownership and Service Criticality

Section 5 defines service criticality and tiering. The tier should affect the strength of the ownership arrangement.

Higher-tier services normally require:

- Stronger team coverage
- More than one qualified technical role holder
- More frequent verification
- Tested escalation
- Broader specialist continuity
- Tighter temporary-ownership limits
- Stronger evidence of operational capability

The tier does not change the core rule. Every production service needs a functioning accountable team.

---

## 58. Ownership and Lifecycle State

Ownership applies throughout the lifecycle.

| State | Ownership expectation |
| --- | --- |
| Proposed | Sponsor and candidate accountable team identified |
| In development | Building team and future production owner recorded |
| Pre-production | Accountable team accepts readiness work |
| Production candidate | Contacts and obligations verified |
| Active production | Full ownership model operates |
| Maintenance | Accountability and support remain explicit |
| Deprecated | Owner manages migration and risk |
| Retirement pending | Owner controls shutdown and evidence |
| Retired | Owner confirms decommissioning |
| Archived | Record custodian preserves required evidence |

Deprecated does not mean unowned.

---

## 59. Ownership and Service Boundaries

The accountable team must know what it owns.

The record should connect to:

- Service boundary
- User or consumer boundary
- Data ownership
- Runtime responsibility
- Dependency responsibilities
- Shared-component agreements

If two teams use different service boundaries, both may claim or reject the same production responsibility.

Resolve the boundary before treating the owner field as complete.

---

## 60. Ownership and Service Taxonomy

Service type can influence which roles participate.

Examples:

- A customer-facing service may need product and support ownership.
- A data service may need a data owner and steward.
- A security service may require security authority.
- A shared platform may need consumer governance.
- A batch service may need deadline and business-process ownership.

Taxonomy informs the model. It does not replace the accountable team.

---

## 61. Common Ownership Models

### Product Team Ownership

The team that builds the service also owns its production outcome.

### Product Team With SRE Support

The product team remains accountable while SRE owns defined reliability capabilities.

### Platform Team Ownership

A platform team owns a shared service and its consumer obligations.

### Dedicated Service Team

A specialized team owns one or several related high-impact services.

### Temporary Transition Team

A time-bounded team stabilizes, transfers, or retires a service.

Each model must still name one accountable team.

---

## 62. Ownership Anti-Patterns

Common anti-patterns include:

- The original author owns it forever
- The last person who changed it owns it
- SRE owns everything in production
- The platform team owns every workload on the platform
- The manager is the only owner
- A distribution list is treated as accountability
- Two teams are jointly accountable with no boundary
- The repository owner is assumed to own the service
- A vendor is the only named owner
- A deprecated service has no owner
- Temporary ownership has no expiry

These patterns confuse contact, contribution, infrastructure, and accountability.

---

## 63. Ownership by Original Author

The original author may have valuable knowledge.

That history does not create permanent accountability.

Risks include:

- The person moves to another team
- Architecture changes after authorship
- Work is never transferred
- The author becomes a bottleneck
- Current management cannot prioritize the work

Preserve knowledge through the team. Reassign roles when organizational responsibility changes.

---

## 64. Ownership by Repository Administrator

Administrative permission proves control over repository settings.

It does not prove accountability for:

- User outcomes
- Runtime behavior
- Data
- Incidents
- Recovery
- Cost
- Lifecycle decisions

The administrator may be a platform contributor while another team owns the service.

---

## 65. Ownership by On-Call Team

An on-call team provides urgent response coverage.

It may or may not be the accountable team.

If a central response team receives alerts but cannot change architecture, prioritize fixes, or accept risk, it is a responder, not the complete owner.

Record both the accountable team and the operational response arrangement.

---

## 66. Ownership by Management Chain

A manager may be accountable for team capacity and organizational outcomes.

The ownership record should not rely only on a senior executive's name.

The operational team must still be discoverable and capable of acting.

Use management escalation to support ownership, not replace it.

---

## 67. Shared Components

A service may depend on components owned by other teams.

Record:

- End-to-end accountable team
- Component owner
- Support expectation
- Change relationship
- Failure escalation
- Recovery dependency
- Known limitations

The service owner cannot transfer end-to-end accountability simply by listing every dependency owner.

---

## 68. Multiple Services Per Team

One team may own several services.

Validate that:

- Each service is listed separately
- Criticality is assessed per service
- Contacts remain usable
- Workload is sustainable
- Specialists are not overcommitted
- Ownership does not hide inside a generic team label

A team with fifty named services may need portfolio review even when every record is technically complete.

---

## 69. Multiple Teams Per Service

Complex services often require many teams.

Use an accountability map:

| Scope | Accountable team | Supporting teams |
| --- | --- | --- |
| End-to-end service outcome | One team | All contributors |
| Application component | One component team | Platform, security |
| Shared platform | Platform team | Infrastructure providers |
| Business process | Business owner | Product, operations |

Do not place several teams in one accountable-team field.

---

## 70. Ownership Disputes

An ownership dispute occurs when teams disagree about accountability or boundaries.

Resolve it using:

- Service boundary evidence
- User outcome
- Change authority
- Budget and staffing responsibility
- Operational capability
- Management structure
- Existing agreements
- Lifecycle history

Assign a temporary accountable team when production risk cannot wait for the dispute.

---

## 71. Decision Authority Is Related but Separate

Accountability without authority is ineffective.

However, this record should not attempt to encode every production decision.

It should identify the roles that can route or escalate decisions about:

- Technical change
- Business risk
- Security action
- Data handling
- Emergency mitigation
- Retirement

A later section should define detailed decision rights and escalation boundaries.

---

## 72. Ownership Does Not Mean Unlimited Access

Owners need appropriate capability, not unrestricted permanent privilege.

Use:

- Least privilege
- Role-based access
- Time-bounded elevation
- Peer approval where required
- Auditing
- Emergency access procedures
- Separation of duties

The ownership record may reference access capability without publishing credentials or sensitive permission details.

---

## 73. Ownership Capacity

A team must have time and staffing to meet its obligations.

Assess:

- Number and criticality of owned services
- Operational workload
- On-call burden
- Planned engineering work
- Required expertise
- Time-zone coverage
- Leave coverage
- Current vacancies
- External dependencies

Naming an overloaded team does not transfer the risk away.

---

## 74. Ownership Health Indicators

Useful ownership-health indicators include:

- Percentage of production services with an accepted accountable team
- Percentage with verified primary and secondary contacts
- Percentage reviewed within policy
- Number of orphaned services
- Number of expired temporary assignments
- Number of critical services with one qualified specialist
- Failed ownership escalations
- Ownership gaps found during incidents
- Services assigned to nonexistent teams

These indicators measure ownership capability, not service reliability itself.

---

## 75. Automation and Ownership Records

Automation can detect stale information.

Possible checks include:

- Team identifier no longer resolves
- Named role holder is inactive
- Contact route rejects messages
- Review date expired
- Temporary assignment expired
- Repository team differs from service record
- Active deployment lacks an owner
- Service moved lifecycle state without verification

Automation should create review work. It should not silently choose a new accountable team.

---

## 76. Authoritative Source

Choose one authoritative source for each ownership field.

Otherwise, different systems may disagree.

Define:

- Where the canonical accountable team is stored
- Which systems receive synchronized copies
- Who may change the record
- How conflicts are detected
- How history is retained
- How public views are derived

A copied README field may help discovery but should not silently override the controlled record.

---

## 77. Ownership Record Quality

A high-quality record is:

- Specific
- Current
- Accepted
- Discoverable
- Verifiable
- Privacy-aware
- Connected to the service boundary
- Connected to criticality and lifecycle state
- Clear about temporary arrangements
- Supported by evidence

Completeness without accuracy is dangerous because it creates false confidence.

---

## 78. Minimum Accountable-Owner Record

At minimum, record:

- Service name and identifier
- Accountable team and stable identifier
- Technical owner role holder
- Business owner role holder
- Primary contact route
- Secondary contact route
- Relevant SMEs
- Effective date
- Last verification date
- Next review date
- Temporary status and expiry, if applicable
- Privacy classification
- Acceptance evidence

Critical services require deeper continuity and capability evidence.

---

## 79. Production Scenario: The Departed Creator

A scheduled settlement service was created by one engineer. The service inventory still lists that engineer's username two years after departure.

The job continues to run. Failures appear only at month end. No current team knows how to replay incomplete settlements.

### Ownership Analysis

- The username is not a functioning owner.
- The service has business and data-integrity consequences.
- The current organizational sponsor must be identified.
- An authorized temporary team should accept immediate accountability.
- Access, procedure, and replay knowledge require urgent reconstruction.
- A permanent accountable team must accept the service or retire it safely.

Changing the username alone would not fix the ownership failure.

---

## 80. Production Scenario: The Expert on Leave

A Tier 1 identity service has a named team and three contacts. Only one engineer knows how to rotate the signing key. That engineer begins six weeks of leave.

### Ownership Analysis

- The contact list overstates continuity.
- Key rotation is a single-person capability.
- A qualified substitute must demonstrate the procedure.
- Access and approvals must be verified before leave.
- Documentation and an exercise should produce evidence.
- The team remains accountable during the absence.

---

## 81. Production Scenario: Joint Ownership

An application team says the platform team owns production because the workload runs on its cluster. The platform team says it only owns the cluster.

### Ownership Analysis

- The platform team owns the shared platform boundary.
- The application team likely owns the application service outcome.
- Runtime responsibilities must be documented.
- Incident and change escalation must cross the boundary.
- One team must remain accountable for the end-to-end application service.

---

## 82. Production Scenario: Public Repository Exposure

A public repository lists employee mobile numbers, internal paging aliases, and a private incident channel in `OWNERS.md`.

### Ownership Analysis

- The repository exposes personal and operational data.
- The public record should use approved project, support, and security routes.
- Detailed contacts should move to an access-controlled record.
- Search history and repository history may require security and privacy review.
- Public maintainership and internal production ownership should be separated.

---

## 83. Production Scenario: Temporary Forever

A transition team accepted a legacy service for ninety days. Eighteen months later, it still owns the service. The original expiry date passed without review.

### Ownership Analysis

- The temporary control failed.
- The service has no approved durable destination.
- The team may lack capacity or authority for long-term ownership.
- Leadership must decide permanent ownership or retirement.
- Continued temporary ownership requires explicit risk acceptance and a new bounded plan.

---

## 84. Accountable-Owner Record Template

Copy and complete this template for each production service.

```markdown
# Accountable-Owner Record

## Record Control

- Service name:
- Service identifier:
- Record version:
- Record owner:
- Created date:
- Last updated date:
- Last verified date:
- Next review date:
- Information classification:
- Authoritative record location:

## Service Context

- Service purpose:
- User or consumer outcome:
- Service boundary reference:
- Primary service classification:
- Secondary classifications:
- Lifecycle state:
- Criticality tier:
- Production environments covered:

## Accountable Team

- Canonical team name:
- Stable team identifier:
- Organizational unit:
- Team manager or accountable lead role:
- Team contact route:
- Team support route:
- Effective date:
- Acceptance status:
- Acceptance date:
- Acceptance evidence:

## Technical Owner

- Role title:
- Current role holder:
- Organizational identity reference:
- Team:
- Contact route:
- Effective date:
- Named substitute:
- Substitute verification date:
- Responsibilities:
- Limitations:

## Business Owner

- Role title:
- Current role holder:
- Organizational unit:
- Contact route:
- Effective date:
- Delegated substitute:
- Business outcome represented:
- Decision or escalation scope:

## Primary Contact

- Contact type:
- Contact route:
- Intended purpose:
- Coverage or response expectation:
- Route owner:
- Last tested date:
- Test result:

## Secondary Contact

- Contact type:
- Contact route:
- Intended purpose:
- Activation condition:
- Coverage or response expectation:
- Route owner:
- Last tested date:
- Test result:

## Subject-Matter Experts

| Domain | Person or team | Expected contribution | Contact route | Backup | Last verified |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |

## Supporting Teams

| Scope or capability | Accountable supporting team | Relationship | Contact route | Escalation route |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

## Continuity

- Minimum qualified role holders required:
- Current qualified role holders:
- Known single-person dependencies:
- Leave coverage:
- Unplanned-absence coverage:
- Staff-turnover procedure:
- Knowledge-transfer evidence:
- Access continuity evidence:
- Documentation location:
- Recovery responsibility:
- Continuity gaps:
- Remediation owner:
- Remediation due date:

## Temporary Ownership

- Is ownership temporary:
- Temporary accountable team:
- Reason:
- Start date:
- Expiry date:
- Permanent-owner candidate:
- Transition plan:
- Review cadence:
- Known limitations:
- Risk owner:
- Exit criteria:

## Public Repository View

- Is any ownership information public:
- Approved public team or project name:
- Public contribution route:
- Public support route:
- Public security-reporting route:
- Internal details removed:
- Privacy review completed by:
- Privacy review date:

## Verification

- Accountable team exists:
- Team accepted ownership:
- Primary contact tested:
- Secondary contact tested:
- Technical owner current:
- Business owner current:
- Substitutes current:
- Required access available:
- Operational documentation located:
- Recovery responsibility confirmed:
- Criticality obligations understood:
- Gaps recorded:
- Verification method:
- Verified by:
- Verification date:

## Open Gaps and Actions

| Gap | Risk | Required action | Owner | Due date | Status |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |

## Approval

- Accountable team representative:
- Technical owner:
- Business owner:
- Approver, if required:
- Decision:
- Conditions:
- Effective date:
```

---

## 85. Practical Exercise: Build an Accountable-Owner Record

Choose one real or realistic production service.

### Step 1: Confirm the Service

Record:

- Service name
- Identifier
- Purpose
- Boundary reference
- Lifecycle state
- Criticality tier

### Step 2: Identify the Accountable Team

Confirm:

- The team exists
- It accepts accountability
- It has a stable identifier
- It can prioritize service work
- It has appropriate authority

### Step 3: Name the Supporting Roles

Identify:

- Technical owner
- Business owner
- Primary contact
- Secondary contact
- Required SMEs

Explain why each role exists.

### Step 4: Test Continuity

Assume the technical owner becomes unavailable for four weeks.

Determine:

- Who substitutes
- Which work can continue
- Which capability fails
- Which access is missing
- Which knowledge must be transferred

### Step 5: Test Staff Turnover

Assume one named role holder leaves immediately.

List:

- Records to update
- Access to revoke or transfer
- Knowledge to preserve
- Contacts to change
- Decisions that need reassignment

### Step 6: Verify Contact Routes

Test the primary and secondary routes using an approved non-emergency method.

Record:

- Time sent
- Time received
- Response
- Failure or ambiguity

### Step 7: Review Privacy

If the repository is public, produce separate public and internal views.

Remove personal and operationally sensitive information from the public version.

### Step 8: Record Gaps

For every gap, assign:

- Risk
- Action
- Owner
- Due date
- Status

### Step 9: Obtain Acceptance

Ask the accountable team and relevant role holders to confirm the record.

Do not mark ownership complete without acceptance evidence.

---

## 86. Exercise Acceptance Criteria

The exercise is complete when:

- The service is uniquely identified.
- The service boundary reference is present.
- One accountable team is named.
- The team accepts the role.
- A stable team identifier is recorded.
- Technical and business roles are distinguished.
- Primary and secondary contacts are usable.
- SMEs are linked to defined domains.
- Leave and turnover continuity are tested.
- Single-person dependencies are visible.
- Temporary ownership has an expiry and exit plan, if applicable.
- Public information contains no unapproved personal or operational details.
- Verification evidence is recorded.
- Every open gap has an owner and due date.

---

## 87. Accountable Ownership Review Checklist

### Accountable Team

- [ ] One accountable team is named.
- [ ] The team exists.
- [ ] The team accepted ownership.
- [ ] A stable identifier is recorded.
- [ ] The service relationship is explicit.
- [ ] The team can prioritize necessary work.
- [ ] Authority and access are sufficient.

### Named Roles

- [ ] A technical owner is current.
- [ ] A business owner or sponsor is current.
- [ ] Role responsibilities are clear.
- [ ] Named substitutes exist where required.
- [ ] Role holders belong to the correct organization.

### Contacts

- [ ] The primary contact matches its intended purpose.
- [ ] A secondary contact exists.
- [ ] Both routes were tested.
- [ ] Emergency and general routes are separated.
- [ ] Team routes are preferred over personal addresses.

### Expertise and Continuity

- [ ] SMEs are recorded by domain.
- [ ] Critical expertise has backups.
- [ ] Documentation is team accessible.
- [ ] Production assets are organization managed.
- [ ] Planned and unplanned absence are covered.
- [ ] Staff-turnover actions are defined.

### Temporary Ownership

- [ ] Temporary status is explicit.
- [ ] Start and expiry dates are recorded.
- [ ] Authority is defined.
- [ ] A permanent destination exists.
- [ ] Exit criteria are measurable.

### Verification

- [ ] Last verification is within policy.
- [ ] Verification tested capability, not only contact.
- [ ] Failed checks created actions.
- [ ] Reorganization and turnover triggers exist.
- [ ] The next review date is recorded.

### Privacy

- [ ] Public and internal views are separated where needed.
- [ ] Personal data is minimized.
- [ ] Internal paging and incident details are not public.
- [ ] Public security reporting uses an approved route.
- [ ] Outdated usernames are removed.

---

## 88. Knowledge Check

1. Why should a team be the durable ownership unit?
2. What is the difference between an accountable team and a technical owner?
3. What does a business owner contribute?
4. Why should the primary contact usually be a team route?
5. What is the purpose of a secondary contact?
6. Why is an SME not automatically the service owner?
7. Name four risks of individual ownership.
8. What evidence can prove knowledge transfer?
9. What must a temporary ownership record include?
10. Why is an expiry date alone insufficient?
11. What should happen when ownership verification fails?
12. Why is `CODEOWNERS` insufficient as a service ownership record?
13. How should public and internal ownership information differ?
14. Why should usernames not be the durable identity of an owner?
15. What is the difference between a team rename and an ownership transfer?

---

## 89. Knowledge Check Answers

1. A team can preserve knowledge, staffing, prioritization, access, and accountability as individuals change.
2. The accountable team remains answerable for the service. The technical owner coordinates technical stewardship as a current role holder.
3. The business owner explains organizational outcomes and consequences, supports prioritization, and routes authorized business decisions.
4. A team route survives ordinary leave and staff turnover better than one personal address.
5. It provides a tested alternative when the primary route is unavailable or unsuitable.
6. Expertise covers a defined domain. It does not automatically include authority or end-to-end accountability.
7. Examples include absence, knowledge loss, burnout, access concentration, delayed work, and unreviewed decisions.
8. Another engineer can complete a deployment, explain the architecture, use the runbook, or perform a recovery exercise.
9. It needs a temporary team, reason, dates, authority, obligations, risk owner, permanent plan, review cadence, and exit criteria.
10. It does not identify how permanent ownership will be achieved or what happens when the date arrives.
11. Correct the record and capability gap, escalate where required, and use a temporary owner or production restriction when risk warrants it.
12. It normally describes code-review routing, not runtime, data, incident, recovery, business, and lifecycle accountability.
13. The public view should use approved project, support, and security routes. Sensitive operational and personal details should remain controlled.
14. People leave, accounts change, and usernames can become invalid or reused. A stable team remains the durable owner.
15. A rename updates the label for the same team. A transfer moves accountability and requires acceptance, capability, access, and knowledge review.

---

## 90. Reflection Questions

1. Which production service still depends on the person who created it?
2. Which named team cannot actually change or recover its service?
3. Which owner field contains a former employee?
4. Which primary contact is not monitored?
5. Which secondary contact shares the same failure condition as the primary?
6. Which critical capability has only one qualified person?
7. Which technical owner has become a permanent bottleneck?
8. Which internal service lacks a business sponsor?
9. Which temporary assignment has exceeded its expiry?
10. Which public repository exposes information that should be internal?
11. Which team owns more services than it can sustain?
12. Which ownership record was confirmed but never capability-tested?
13. Which service would become orphaned during the next reorganization?
14. Which SME should transfer knowledge this quarter?
15. Which contact route should become a managed team route?

---

## 91. Key Takeaways

- Durable service ownership belongs to a team, not an isolated individual.
- One accountable team should remain answerable for each service outcome.
- Technical owners, business owners, contacts, and SMEs perform different roles.
- Named people support coordination but should not become permanent single points of failure.
- Team continuity requires shared knowledge, substitutes, access, documentation, and capacity.
- Planned leave should trigger handover. Unplanned absence should already be survivable.
- Staff turnover requires role, access, knowledge, contact, and record review.
- Temporary ownership needs authority, an expiry, review, and a permanent exit plan.
- Ownership verification must test real capability, not only confirm a name.
- Usernames and personal accounts are not durable ownership identities.
- Repository ownership files do not prove complete production ownership.
- Public repositories should expose approved public routes, not personal or sensitive operational information.
- An accurate, accepted, and verified owner record is an operational control.

---

## Related SRE World Sections

- [Identifying Production Services](./01-Identifying-Production-Services.md)
- [Defining Service Boundaries](./02-Defining-Service-Boundaries.md)
- [Service Taxonomy and Classification](./03-Service-Taxonomy-and-Classification.md)
- [Service Lifecycle States](./04-Service-Lifecycle-States.md)
- [Service Criticality and Tiering](./05-Service-Criticality-and-Tiering.md)
- [Production Responsibility](../01-SRE-Foundations/08-Production-Responsibility.md)
- [Service Ownership](../01-SRE-Foundations/09-Service-Ownership.md)

---

## Next Section

[Section 7: Ownership Responsibilities and Obligations](./07-Ownership-Responsibilities-and-Obligations.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is durable when the accountable team can still understand, operate, recover, and improve the service after every named person has changed.
