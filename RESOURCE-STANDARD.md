# SRE World Resource Standard

## Purpose

This document defines the quality, relevance, classification, documentation, and maintenance requirements for every resource added to SRE World.

SRE World is a curated production reliability engineering knowledge base. It is not an unrestricted list of links, a general DevOps roadmap, or a directory of tools. Every accepted resource must help engineers define, measure, protect, operate, restore, or improve the reliability of a service.

Resource quality takes priority over resource quantity.

---

## 1. The SRE Relevance Test

Before adding a resource, ask:

> Does this resource help an engineer understand, measure, operate, protect, restore, or improve the reliability of a production service?

A resource must address at least one of the following areas:

- Service ownership
- Critical user journeys
- Reliability requirements
- SLIs, SLOs, or SLAs
- Error budgets
- Reliability measurement
- Observability and telemetry design
- Alerting engineering
- On-call operations
- Incident response
- Production troubleshooting
- Postmortems and organizational learning
- Toil reduction
- Safe operational automation
- Production readiness
- Change and release reliability
- Capacity planning
- Performance engineering
- Distributed systems failure
- Resilience engineering
- Disaster recovery
- Data, network, cloud, Kubernetes, or security reliability
- Reliability architecture
- SRE organizations, governance, maturity, or leadership

If a resource teaches only how to install, configure, or operate a product without connecting that work to a defined reliability problem, it does not qualify.

---

## 2. What Qualifies for SRE World

High-quality resources may include:

- Official SRE books and reliability guides
- Engineering articles written from production experience
- Public incident reports and postmortems
- Conference talks presented by practitioners
- Peer-reviewed research papers
- Systems research with clear reliability relevance
- Official standards and architecture guidance
- Technical books and substantial book chapters
- Practical courses with strong SRE depth
- Reliability case studies
- SLO and error budget examples
- Incident response procedures
- Runbooks, playbooks, checklists, and worksheets
- Failure-injection and resilience exercises
- Production troubleshooting scenarios
- Open-source projects created specifically for an SRE practice
- Original VERIQTA explanations, templates, labs, and analyses

A resource does not need to contain “SRE” in its title. Its content and production relevance determine whether it belongs.

---

## 3. What Does Not Belong

Do not add:

- General DevOps beginner roadmaps
- Learn Linux, Git, Docker, or Kubernetes from scratch courses
- General CI/CD tutorials
- Infrastructure-as-code tutorials without a reliability use case
- Cloud certification preparation
- Certification dumps or copied exam questions
- Product installation guides without operational context
- Generic “top SRE tools” articles
- Short definition-only posts
- Search-engine-generated listicles
- Promotional vendor pages with no transferable engineering value
- AI-generated summaries that have not been technically reviewed
- Copied articles, pirated books, or unauthorized course material
- Duplicate links that add no new perspective
- Broken links without a preserved archive or historical reason
- Content that encourages unsafe production practices
- Commands or automation without risk, rollback, and verification guidance
- Interview trivia disconnected from real production responsibility
- Resources included only because they are popular

These resources may belong in [DEVOPS WORLD](https://github.com/veriqta/DEVOPS-WORLD), but not in SRE World.

---

## 4. Source Priority

Use this order when selecting resources.

### Priority 1: Primary Production Sources

- Original public incident reports
- Engineering posts written by the organization that operated the system
- Original technical designs
- First-party reliability documentation
- Conference talks by engineers directly involved in the work

### Priority 2: Authoritative SRE and Systems Sources

- Google SRE publications
- USENIX and SREcon material
- ACM and IEEE publications
- Official standards
- Major cloud reliability architecture guidance
- Established resilience engineering publications

### Priority 3: Independent Practitioner Sources

- Experienced SRE and production engineering authors
- Detailed technical books
- Evidence-based case studies
- High-quality courses and workshops
- Technical communities with visible editorial standards

### Priority 4: Vendor Sources

Vendor material may be accepted when it:

- Teaches a transferable reliability principle
- Explains production behavior rather than marketing claims
- Includes technical depth, evidence, or reproducible examples
- Clearly distinguishes product capability from general practice
- Does not require the reader to adopt the vendor’s product to gain value

### Priority 5: Community Sources

Community material may be accepted after careful verification when it provides:

- A unique production scenario
- A strong practical explanation
- A useful open-source template
- An independently verifiable technical contribution

Primary and authoritative sources should replace secondary explanations when they provide equal or better coverage.

---

## 5. Required Resource Entry

Every external resource must use this structure unless a folder-specific standard requires additional fields.

```text
Resource ID:
Title:
Author or Organization:
Resource Type:
SRE Domain:
Experience Level:
Publication Date:
Last Verified:
Access:
Source Class:

Official or Permanent Link:
Alternative or Archived Link:

What It Covers:
Why It Is Valuable:
Production Relevance:
What It Does Not Cover:
Recommended Prerequisites:
Estimated Time:
Key Lessons:
Operational Risks or Limitations:
Related Resources:
Status:
```

Do not submit a bare link. Readers must be able to understand the resource’s purpose and limitations before opening it.

---

## 6. Field Definitions

### Resource ID

A permanent repository identifier. The ID must not change when a resource title or URL changes.

### Title

Use the original published title. Do not rewrite it for search ranking or promotion.

### Author or Organization

Name the person or organization responsible for the material. Do not list the website host as the author unless it created the content.

### Resource Type

Use one approved type from Section 8.

### SRE Domain

Use the most specific primary domain from Section 9. Add secondary domains only when they materially improve discovery.

### Experience Level

Use the level at which the content provides the greatest value. A resource may list two adjacent levels when necessary.

### Publication Date

Use the original publication date where available. If substantially revised, record the latest revision date separately.

### Last Verified

Record the date on which a maintainer confirmed that:

- The link works
- The title and author are correct
- The resource remains available
- The description reflects the content
- The classification remains appropriate

Use ISO format:

```text
YYYY-MM-DD
```

### Access

State whether the resource is free, paid, partially free, registration required, membership required, or archived.

### Source Class

Classify the source as primary, authoritative, practitioner, vendor, community, or historical.

### What It Covers

Summarize the actual scope. Do not copy the publisher’s promotional description.

### Why It Is Valuable

Explain the specific reason an SRE practitioner should use it.

### Production Relevance

Connect the material to production decisions, risks, failure modes, or operating responsibilities.

### What It Does Not Cover

State important gaps, assumptions, outdated sections, or areas requiring another resource.

### Recommended Prerequisites

List concepts the reader should understand first. Do not use this field to insert an unrelated tool roadmap.

### Estimated Time

Provide a reasonable reading, viewing, or completion estimate. Use a range when exact duration is unknown.

### Key Lessons

List the most important transferable conclusions. Avoid copying long passages.

### Operational Risks or Limitations

Identify advice that may be environment-specific, outdated, unsafe at scale, or dangerous if applied without validation.

### Related Resources

Link to complementary entries or relevant SRE World folders.

### Status

Use one approved status from Section 11.

---

## 7. Resource ID Standard

Use this format:

```text
SRE-[DOMAIN]-[TYPE]-[NUMBER]
```

Examples:

```text
SRE-SLO-BOOK-001
SRE-INC-POST-004
SRE-OBS-TALK-012
SRE-DIST-PAPER-006
SRE-DR-LAB-003
```

### Approved Domain Codes

| Code | Domain |
|---|---|
| `FND` | SRE Foundations |
| `OWN` | Service Ownership |
| `SLO` | SLIs, SLOs, and SLAs |
| `EB` | Error Budgets |
| `MET` | Reliability Measurement |
| `OBS` | Observability |
| `ALT` | Alerting |
| `ONC` | On-Call |
| `INC` | Incident Management |
| `TRB` | Troubleshooting |
| `PM` | Postmortems and Learning |
| `TOIL` | Toil and Automation |
| `PRR` | Production Readiness |
| `CHG` | Change and Release Reliability |
| `CAP` | Capacity Planning |
| `PERF` | Performance and Load |
| `DIST` | Distributed Systems Reliability |
| `RES` | Resilience Engineering |
| `DR` | Disaster Recovery |
| `DATA` | Data Reliability |
| `NET` | Network Reliability |
| `CLD` | Cloud Reliability |
| `K8S` | Kubernetes Reliability |
| `SEC` | Security and Reliability |
| `ARCH` | Reliability Architecture |
| `ORG` | SRE Organizations and Culture |
| `GOV` | SRE Maturity and Governance |
| `LDR` | SRE Leadership |
| `CASE` | Case Studies |
| `CAREER` | SRE Career Development |

### Approved Type Codes

| Code | Resource Type |
|---|---|
| `ARTICLE` | Article |
| `BOOK` | Book |
| `CHAPTER` | Book chapter |
| `COURSE` | Course |
| `DOC` | Documentation or guide |
| `LAB` | Practical lab |
| `PAPER` | Research paper |
| `POST` | Incident report or postmortem |
| `PROJECT` | Practical project |
| `TALK` | Conference talk or presentation |
| `TEMPLATE` | Reusable template |
| `TOOL` | SRE-specific tool or project |
| `VIDEO` | Educational video |
| `WORKSHOP` | Workshop or classroom exercise |

Numbers use three digits and begin at `001` within each domain and type combination.

Never reuse an ID after removing a resource. Mark it retired in the changelog.

---

## 8. Approved Resource Types

- Article
- Book
- Book chapter
- Case study
- Checklist
- Course
- Documentation or guide
- Incident report
- Lab
- Podcast episode
- Postmortem
- Project
- Research paper
- Runbook
- Standard
- Talk or presentation
- Template
- Tool or open-source project
- Video
- Workshop
- Worksheet

If a resource fits several types, choose the format readers will directly consume.

---

## 9. Approved SRE Domains

- SRE Foundations
- Service Ownership
- SLIs, SLOs, and SLAs
- Error Budgets
- Reliability Measurement
- Observability Engineering
- Alerting Engineering
- On-Call Engineering
- Incident Management
- Troubleshooting and Debugging
- Postmortems and Learning
- Toil and Automation
- Production Readiness
- Change and Release Reliability
- Capacity Planning
- Performance and Load
- Distributed Systems Reliability
- Resilience Engineering
- Disaster Recovery
- Data Reliability
- Network Reliability
- Cloud Reliability
- Kubernetes Reliability
- Security and Reliability
- Reliability Architecture
- SRE Organizations and Culture
- SRE Maturity and Governance
- SRE Leadership
- SRE Case Studies
- Production Incidents
- SRE Career Development

Choose one primary domain. Use cross-references instead of copying the same entry into multiple folders.

---

## 10. Experience Levels

### Foundation

Introduces SRE concepts accurately without assuming prior reliability experience. Foundation does not mean shallow or tool-focused.

### Practitioner

Supports engineers who participate in on-call, incident response, service measurement, troubleshooting, or production improvement.

### Senior

Addresses ambiguous failures, complex systems, multi-service risk, advanced design decisions, or cross-team operations.

### Staff

Addresses organization-wide architecture, technical strategy, reliability programs, and influence across multiple teams.

### Leadership

Addresses management, governance, staffing, reliability investment, organizational design, or executive communication.

### Research

Requires comfort with academic papers, formal methods, advanced systems concepts, statistics, or experimental evaluation.

Do not assign Foundation merely because a resource begins with definitions. Evaluate the depth of the complete resource.

---

## 11. Resource Status

### Active

The resource is available, maintained, and currently relevant.

### Stable

The resource is not frequently updated but remains accurate and valuable.

### Historically Important

Some details may be dated, but the resource remains important to the development of SRE or reliability engineering.

### Archived

The original project or publication is no longer maintained. The entry must explain why it remains useful.

### Superseded

A newer authoritative resource replaces it. Retain it only when comparison or history has value.

### Under Review

The resource requires technical, link, licensing, or classification review before full acceptance.

### Broken

The original link does not work. Provide an authorized archive where possible and create a maintenance issue.

### Retired

The resource no longer meets the standard. Record the removal in `CHANGELOG.md` and do not reuse its ID.

---

## 12. Access Classification

Use one of these values:

- Free
- Free with registration
- Partially free
- Paid
- Membership required
- Institution access required
- Archived access
- Unavailable

Do not label a free trial as free. Do not link to unauthorized copies of paid material.

---

## 13. Evaluation Criteria

Review each candidate against the following criteria.

### Relevance

- Does it address a defined SRE responsibility?
- Does it connect to production systems or user impact?
- Does it belong in the selected domain?

### Authority

- Does the author have relevant production, research, or standards experience?
- Is the organization responsible for the system or practice described?
- Are important claims supported by evidence or primary sources?

### Technical Accuracy

- Are definitions and calculations correct?
- Are limitations and assumptions visible?
- Are commands, configurations, and procedures valid?
- Does the guidance avoid unsafe generalization?

### Production Depth

- Does it explain failure modes and tradeoffs?
- Does it distinguish detection, mitigation, recovery, and prevention?
- Does it address scale, ownership, risk, or verification?
- Does it teach reasoning rather than only steps?

### Practical Value

- Can an engineer apply or test the material?
- Does it provide examples, exercises, patterns, or decision guidance?
- Does it improve operational judgment?

### Clarity

- Is the material understandable for its assigned level?
- Are important terms defined?
- Is the structure navigable?

### Currency

- Are time-sensitive details current?
- Are links, screenshots, APIs, or product instructions still valid?
- If dated, are the principles still valuable?

### Independence

- Does the resource provide engineering value beyond product promotion?
- Are conflicts of interest or commercial limitations clear?

### Safety

- Does it discuss risk before production changes?
- Does it include rollback or containment where necessary?
- Does it require verification after action?
- Does it avoid exposing secrets or encouraging unsafe privilege use?

---

## 14. Acceptance Standard

A resource should normally satisfy all mandatory conditions and most quality conditions.

### Mandatory Conditions

- Clearly relevant to SRE
- Technically credible
- Legally shareable
- Correctly classified
- Working or legitimately archived link
- Original description written for SRE World
- No undisclosed promotional intent
- No dangerous instructions presented without safeguards

### Strong Quality Signals

- Primary or authoritative source
- Evidence from production operation
- Clear tradeoffs and limitations
- Transferable engineering lessons
- Practical exercises or examples
- Failure and recovery analysis
- Suitable depth for its assigned level

### Automatic Rejection Conditions

- Pirated or copied material
- Certification dump
- Fabricated author, source, incident, or claim
- Malicious or deceptive link
- Plagiarized description
- Pure marketing content
- Generic DevOps tutorial with no SRE relevance
- Known unsafe guidance without warning or correction
- Resource submitted only to manipulate traffic or search ranking

---

## 15. Scoring Guide

Maintainers may score candidates from 0 to 2 in each category.

| Category | 0 | 1 | 2 |
|---|---|---|---|
| SRE relevance | Weak or absent | Indirect | Direct and substantial |
| Authority | Unclear | Credible secondary source | Primary or authoritative |
| Accuracy | Unverified | Mostly supported | Strongly verified |
| Production depth | Generic | Some operational context | Deep production reasoning |
| Practical value | Little application | Useful explanation | Directly applicable |
| Original contribution | Duplicate | Adds some perspective | Unique or exceptional |
| Currency | Outdated without value | Minor age concerns | Current or enduring |
| Safety | Unsafe | Incomplete safeguards | Risks and verification clear |

Interpretation:

- `14–16`: Strongly recommended
- `11–13`: Accept with normal editorial review
- `8–10`: Improve or justify before acceptance
- `0–7`: Reject

Scoring supports judgment. It does not replace technical review.

---

## 16. Link Verification

Before accepting a link:

1. Open the exact destination.
2. Confirm the page loads without an unexpected redirect.
3. Confirm the title, author, organization, and date.
4. Confirm the link points to the original or authorized source.
5. Check whether registration or payment is required.
6. Confirm that the description matches the actual content.
7. Prefer a stable canonical URL.
8. Remove tracking parameters.
9. Use HTTPS where available.
10. Record the verification date.

Do not use:

- Search-result links
- URL shorteners when the permanent URL is available
- Links containing personal session data
- Unauthorized mirrors
- Affiliate links without explicit maintainer approval and disclosure
- Links that force unrelated downloads

---

## 17. Duplicate Resources

Before adding a resource:

- Search by title
- Search by canonical URL
- Search by author and topic
- Check whether the same material appears in another format
- Check cross-references in related domains

When duplicates exist:

- Keep the original or most authoritative version.
- Prefer the latest complete revision unless history matters.
- Link to one canonical entry from multiple folders.
- Do not copy the full description across folders.
- Keep video and written versions separately only when each provides distinct value.

---

## 18. Vendor Content

Vendor resources require additional review because educational content may also promote a product.

Accept vendor material when:

- The engineering principle remains useful outside the product
- Technical claims are specific and supportable
- Product limitations are not hidden
- The material includes genuine architecture or production reasoning
- Equivalent primary guidance is unavailable or less useful

The entry must identify:

- Product-specific sections
- Transferable lessons
- Commercial or registration requirements
- Important omissions
- Alternative implementations where relevant

Reject vendor content that consists mainly of lead generation, unsupported comparisons, sales claims, or feature lists.

---

## 19. Public Incident Reports

Incident reports should link to the organization’s original publication whenever possible.

Every incident entry should include:

```text
Incident ID:
Organization:
Incident Date:
Publication Date:
Affected Service:
Failure Domain:
Trigger:
Customer Impact:
Duration:
Detection:
Contributing Conditions:
Mitigation:
Recovery:
Corrective Work:
Transferable SRE Lessons:
Original Report:
Last Verified:
Status:
```

### Incident Analysis Rules

- Separate confirmed facts from VERIQTA analysis.
- Do not invent missing technical details.
- Avoid blaming individuals.
- Distinguish the trigger from broader contributing conditions.
- Note where the organization did not disclose information.
- Do not claim a single root cause when the report describes interacting factors.
- Preserve the incident’s original terminology where precision matters.
- Add lessons only when supported by the report or clearly labeled as inference.

---

## 20. Research Papers

Research entries must include:

- Full paper title
- Authors
- Institution or publisher
- Publication venue
- Publication year
- DOI or official paper link
- Research question
- Method
- Main findings
- Limitations
- Production relevance
- Required background

Prefer the publisher, conference, institutional repository, or author-authorized version.

Do not treat a preprint as peer reviewed unless it was accepted by a peer-reviewed venue.

---

## 21. Books and Courses

### Books

Record:

- Author or editor
- Edition
- Publication year
- Publisher
- Free or paid access
- Relevant chapters
- Expected level
- Dated sections
- Why the book remains valuable

Link only to the publisher, author, official free edition, library catalog, or authorized bookseller.

### Courses

Record:

- Instructor and organization
- Syllabus
- Duration
- Cost and registration requirements
- Practical work
- Intended level
- Last verified date
- Whether the course is active

Do not recommend a course based only on its title, star rating, or enrollment count.

---

## 22. Videos, Talks, and Podcasts

Record:

- Speaker
- Speaker’s relevant role at the time
- Event or channel
- Publication date
- Duration
- Topic coverage
- Production context
- Important limitations
- Whether captions or transcripts are available

Prefer the official conference, organization, or speaker upload.

Do not include multiple recordings of the same talk unless the original is unavailable.

---

## 23. SRE-Specific Tools and Projects

SRE World is not organized around products. A tool or open-source project qualifies only when it directly supports an SRE practice.

Examples include:

- SLO definition or evaluation
- Error budget analysis
- Reliability testing
- Incident coordination
- Failure injection
- Production readiness assessment
- Capacity or performance analysis
- Automated remediation with safeguards

Every tool entry must include:

- Reliability problem solved
- Project owner
- Official documentation
- Official repository
- License
- Maintenance activity
- Supported environments
- Operational model
- Security considerations
- Failure modes
- Adoption risks
- Alternatives
- Exit or migration considerations

Do not add a general monitoring, cloud, container, or CI/CD product simply because SRE teams may use it.

---

## 24. Templates, Runbooks, Playbooks, and Checklists

Original operational material must be usable, reviewable, and safe.

### Templates

State:

- Intended decision or record
- Required inputs
- Owner
- Review frequency
- Completion criteria

### Runbooks

Include:

- Purpose and trigger
- Customer impact
- Preconditions and access requirements
- Safety warnings
- Diagnostic steps
- Expected evidence
- Mitigation options
- Escalation conditions
- Rollback or stop conditions
- Recovery verification
- Follow-up work

### Playbooks

Include:

- Scenario and scope
- Roles and responsibilities
- Decision points
- Communication requirements
- Containment options
- Recovery criteria
- Exit conditions

### Checklists

- Use verifiable items.
- Avoid vague instructions such as “ensure reliability.”
- Identify the responsible owner.
- Include exceptions and approval requirements where necessary.
- Do not use a checklist as a substitute for engineering judgment.

---

## 25. Labs and Production Scenarios

Every lab should include:

- Learning objective
- Environment assumptions
- Required access
- Cost warning where relevant
- Safety boundaries
- Initial system state
- Failure introduced
- User-visible symptoms
- Available evidence
- Expected investigation method
- Mitigation options
- Recovery verification
- Cleanup instructions
- Reflection questions

Labs must not require learners to experiment on systems they do not own or have permission to use.

Production scenarios should test decisions, not only command recall.

---

## 26. Technical Accuracy and Safety

Resource descriptions and original materials must:

- Distinguish fact from opinion or inference
- State important assumptions
- Avoid fabricated incidents, metrics, commands, and citations
- Explain destructive or high-risk operations
- Use least privilege
- Never include real secrets, credentials, or private data
- Avoid hardcoded credentials
- Include rollback or stop conditions where appropriate
- Include recovery verification
- Explain blast-radius concerns
- Warn when commands or procedures are environment-specific
- Prefer reversible actions during uncertain production conditions

Never present a restart, deletion, failover, rollback, scaling action, or automated remediation as universally safe.

---

## 27. Writing and Editorial Style

Use:

- Clear and direct language
- Short or medium sentences
- Accurate technical terms
- Descriptive headings
- Lists and tables when they improve navigation
- Concrete production examples
- Explicit risks and tradeoffs
- Relative repository links for internal content

Avoid:

- Promotional language
- Empty claims such as “best practice” without context
- Excessive emojis
- Decorative Unicode text
- Unexplained acronyms
- Copying publisher descriptions
- Long quotations
- Artificial keyword repetition
- Presenting one organization’s implementation as universal

Use the official capitalization of technologies and organizations. Use `SRE` and `Site Reliability Engineering` consistently.

---

## 28. File and Link Naming

Use descriptive Markdown filenames with hyphens:

```text
Designing-Availability-SLIs.md
Multi-Window-Burn-Rate-Alerts.md
Incident-Command-Checklist.md
Regional-Failover-Game-Day.md
```

Do not use:

```text
new.md
notes2.md
final-final.md
resource.md
random-links.md
```

Internal links should be relative:

```markdown
[Error Budgets](../04-Error-Budgets/)
```

External link labels should describe the destination. Do not use “click here.”

---

## 29. Attribution, Copyright, and Licensing

- Credit the original author and publisher.
- Link to the authorized source.
- Do not reproduce complete copyrighted articles, books, courses, or transcripts.
- Use short quotations only when necessary and permitted.
- Summaries must be written in original language.
- Preserve required license notices for reused open-source material.
- Confirm that contributed templates, code, diagrams, and datasets may legally be shared.
- Clearly identify original VERIQTA content.
- Do not imply endorsement by a linked author or organization.

When licensing is unclear, link to the source instead of copying the material.

---

## 30. Review Process

Each proposed resource should pass these stages:

```text
Candidate submitted
        ↓
SRE relevance review
        ↓
Source and link verification
        ↓
Technical and safety review
        ↓
Duplicate and classification check
        ↓
Editorial review
        ↓
Accept, revise, or reject
        ↓
Add verification date and changelog entry
```

### Review Outcomes

#### Accept

The resource meets the standard and may be merged.

#### Revise

The resource is valuable, but its description, classification, evidence, safety notes, or links require correction.

#### Reject

The resource is irrelevant, low quality, unsafe, duplicated, unauthorized, misleading, or promotional.

Maintainers may request additional evidence or decline a contribution even when every form field is complete.

---

## 31. Maintenance and Reverification

Every resource must have a `Last Verified` date.

Suggested review frequency:

| Resource | Review Frequency |
|---|---|
| Time-sensitive product documentation | Every 6 months |
| Active courses and training | Every 6 months |
| Tools and open-source projects | Every 6 months |
| Engineering articles | Every 12 months |
| Incident reports | Every 12 months |
| Books | Every 12 months |
| Research papers | Every 12 to 24 months |
| Standards | When a new edition is announced |
| Original templates and runbooks | After use, incidents, or major practice changes |

During reverification:

1. Open the link.
2. Confirm access conditions.
3. Check for a newer edition or canonical source.
4. Review technical currency.
5. Confirm that the entry description remains accurate.
6. Update limitations and related resources.
7. Change the status if necessary.
8. Record material changes in `CHANGELOG.md`.

---

## 32. Broken, Outdated, and Archived Resources

### Broken Links

- Search for the publisher’s new canonical URL.
- Check whether the organization moved or renamed the content.
- Use an authorized archive when appropriate.
- Mark the resource `Broken` while repair is pending.
- Retire it if no legitimate copy exists and its record has no continuing value.

### Outdated Resources

Do not remove a resource only because it is old.

Keep it when:

- Its principles remain correct
- It documents an important historical development
- It explains a failure or system that remains relevant
- Its limitations are clearly stated

Replace or retire it when:

- Following it creates material technical or security risk
- A newer authoritative version supersedes it
- Its central claims are no longer correct
- It depends on unavailable systems without historical value

### Archived Projects

Record:

- Archive date
- Last known release
- Maintenance status
- Reason it remains relevant
- Active alternatives where appropriate

---

## 33. Required Pull Request Information

A resource contribution should include:

```text
Resource ID:
Proposed Folder:
Title:
Canonical Link:
Author or Organization:
Resource Type:
SRE Domain:
Experience Level:
Access:
Last Verified:

Why It Belongs:
Production Relevance:
Known Limitations:
Duplicate Search Completed:
Licensing Checked:
Safety Concerns:
```

The contributor should also confirm:

- [ ] I opened and reviewed the complete resource.
- [ ] I verified the canonical link.
- [ ] I searched the repository for duplicates.
- [ ] I wrote the description in my own words.
- [ ] I identified important limitations.
- [ ] I disclosed any relationship with the author or vendor.
- [ ] I confirmed that the contribution may be legally shared.
- [ ] I did not include credentials, personal data, or unauthorized material.

---

## 34. Example Accepted Entry

```text
Resource ID: SRE-SLO-BOOK-001
Title: [Original Published Title]
Author or Organization: [Author or Organization]
Resource Type: Book
SRE Domain: SLIs, SLOs, and SLAs
Experience Level: Foundation to Practitioner
Publication Date: YYYY-MM-DD
Last Verified: YYYY-MM-DD
Access: Free
Source Class: Authoritative

Official or Permanent Link: https://example.com/resource
Alternative or Archived Link: Not required

What It Covers:
Explains user-centered reliability measurement, objective design, error
budgets, and the operational use of service-level objectives.

Why It Is Valuable:
Connects SLO theory to practical service ownership and production decisions.

Production Relevance:
Helps teams define acceptable reliability and decide when reliability work
should take priority over release velocity.

What It Does Not Cover:
Does not provide product-specific implementation instructions.

Recommended Prerequisites:
Basic understanding of service ownership and production monitoring.

Estimated Time:
6 to 10 hours.

Key Lessons:
- Start from user journeys.
- Measure outcomes rather than infrastructure activity.
- Use error budgets to make explicit risk decisions.

Operational Risks or Limitations:
Example objectives must be adapted to actual user expectations and business risk.

Related Resources:
- 03-SLIs-SLOs-and-SLAs
- 04-Error-Budgets

Status: Active
```

---

## 35. Final Maintainer Checklist

Before merging a resource, confirm:

- [ ] The resource passes the SRE relevance test.
- [ ] The original source was reviewed.
- [ ] The title, author, date, and link are correct.
- [ ] The resource has one primary domain.
- [ ] The experience level is appropriate.
- [ ] The description is original and accurate.
- [ ] Production relevance is explicit.
- [ ] Important gaps and limitations are documented.
- [ ] Technical instructions are safe or properly warned.
- [ ] The repository contains no duplicate canonical entry.
- [ ] Copyright and licensing requirements are respected.
- [ ] The `Last Verified` date is present.
- [ ] The status is correct.
- [ ] Internal links work.
- [ ] The contribution follows the repository writing style.
- [ ] A material addition is recorded in `CHANGELOG.md`.

---

## Standard Ownership

This standard is maintained by VERIQTA for the SRE World repository.

The standard may evolve as the repository grows, new resource types are introduced, or maintenance experience reveals gaps. Material changes should be recorded in `CHANGELOG.md`.

Questions and proposed changes should be submitted through the repository’s issue or pull request process.

---

> SRE World includes fewer resources with stronger evidence, clearer context, and greater production value.
