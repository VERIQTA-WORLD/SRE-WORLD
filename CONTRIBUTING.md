# Contributing to SRE World

Thank you for helping improve SRE World.

SRE World is a curated production reliability engineering knowledge base. Contributions should help engineers define, measure, operate, protect, restore, or improve the reliability of production services.

This repository values technical accuracy, production relevance, clear context, safe operational guidance, and original work. Resource quality takes priority over the number of links or files added.

Before contributing, read:

- [SRE World Roadmap](./ROADMAP.md)
- [Resource Standard](./RESOURCE-STANDARD.md)
- [Code of Conduct](./CODE_OF_CONDUCT.md)

By participating, you agree to follow these documents.

---

## Table of Contents

1. Ways to contribute
2. Scope of accepted contributions
3. Contributions that do not belong
4. Before you begin
5. Reporting broken or outdated resources
6. Proposing a new resource
7. Contributing original educational content
8. Contributing incident reports and postmortems
9. Contributing templates, runbooks, and playbooks
10. Contributing labs and production scenarios
11. Making corrections
12. Repository structure
13. File naming
14. Resource IDs
15. Writing standard
16. Technical accuracy and operational safety
17. Attribution, copyright, and licensing
18. Vendor and relationship disclosure
19. Git and pull request workflow
20. Commit messages
21. Pull request requirements
22. Review process
23. Reasons a contribution may be rejected
24. Contributor checklist
25. Maintainer responsibilities

---

## 1. Ways to Contribute

You can contribute by:

- Suggesting a high-quality SRE resource
- Adding an authoritative book, paper, talk, course, or article
- Adding a public incident report or postmortem
- Correcting inaccurate technical content
- Reporting a broken, redirected, or outdated link
- Replacing a secondary resource with a stronger primary source
- Improving a resource description
- Adding an important limitation or safety warning
- Creating an SRE template, worksheet, checklist, runbook, or playbook
- Creating a production troubleshooting scenario
- Creating a resilience or failure-injection lab
- Improving accessibility, formatting, navigation, or internal links
- Reviewing an open contribution for accuracy
- Translating concepts only when maintainers approve a language structure

A useful contribution does not need to be large. A verified link correction or an important technical clarification can be as valuable as a new section.

---

## 2. Scope of Accepted Contributions

Contributions should address one or more SRE domains:

- SRE foundations
- Service ownership
- SLIs, SLOs, and SLAs
- Error budgets
- Reliability measurement
- Observability engineering
- Alerting engineering
- On-call engineering
- Incident management
- Troubleshooting and debugging
- Postmortems and organizational learning
- Toil and automation
- Production readiness
- Change and release reliability
- Capacity planning
- Performance and load
- Distributed systems reliability
- Resilience engineering
- Disaster recovery
- Data reliability
- Network reliability
- Cloud reliability
- Kubernetes reliability
- Security and reliability
- Reliability architecture
- SRE organizations, maturity, governance, and leadership
- SRE case studies
- Production incidents
- SRE projects and labs
- SRE career development

The contribution should connect to production responsibility, service behavior, customer impact, operational risk, failure, recovery, or measurable reliability improvement.

---

## 3. Contributions That Do Not Belong

Do not submit:

- General DevOps beginner roadmaps
- General Linux, Git, Docker, or Kubernetes tutorials
- General CI/CD or infrastructure-as-code tutorials
- Cloud certification preparation
- Certification dumps or copied exam questions
- Tool installation walkthroughs without an SRE use case
- Generic lists of monitoring products
- Short definition-only posts
- Vendor advertisements
- Affiliate links without prior approval and disclosure
- Search-engine-generated collections
- Unreviewed AI-generated content
- Copied articles or descriptions
- Pirated books, courses, videos, or paid documents
- Duplicate resources with no additional value
- Unsafe production commands without safeguards
- Interview trivia disconnected from real SRE work
- Resources included only to generate traffic or promote an author

General DevOps material may be better suited to [DEVOPS WORLD](https://github.com/veriqta/DEVOPS-WORLD).

---

## 4. Before You Begin

Before opening an issue or pull request:

1. Read [RESOURCE-STANDARD.md](./RESOURCE-STANDARD.md).
2. Search the repository by title, author, URL, and subject.
3. Identify the correct primary folder.
4. Open and review the complete resource.
5. Verify the canonical link.
6. Confirm the author, organization, publication date, and access conditions.
7. Determine the appropriate SRE domain and experience level.
8. Identify production value, limitations, and safety concerns.
9. Confirm that the content may legally be linked, quoted, or contributed.
10. Check existing issues and pull requests for the same proposal.

If you are unsure whether a large contribution fits, open a proposal issue before writing it.

---

## 5. Reporting Broken or Outdated Resources

Open an issue and include:

```text
Resource ID:
Resource Title:
Repository Path:
Current Link:
Problem Found:
Date Checked:
Suggested Replacement:
Additional Evidence:
```

Examples of valid reports:

- The link returns an error.
- The resource moved to a new canonical location.
- The resource now requires payment or registration.
- The author or organization changed.
- A newer edition supersedes the listed version.
- Product-specific instructions are no longer safe or valid.
- The SRE World description does not match the source.
- The resource was archived.
- The resource contains a security or operational risk not documented in the entry.

Do not submit a report based only on the age of a resource. Older publications may remain valuable when their principles or historical importance are clear.

---

## 6. Proposing a New Resource

Use the required resource format from [RESOURCE-STANDARD.md](./RESOURCE-STANDARD.md):

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

### Proposal Requirements

- Use the original published title.
- Link to the original or authorized source.
- Write the description in your own words.
- Explain why the resource belongs in SRE World.
- Identify what the resource does not cover.
- State access requirements accurately.
- Record the date you verified the resource.
- Disclose any relationship with the author, organization, or product.
- Do not invent a permanent resource ID if a maintainer has not confirmed the next available number.

Maintainers may assign or adjust the final resource ID during review.

---

## 7. Contributing Original Educational Content

Original content should teach engineering reasoning, not merely repeat documentation.

It should include, where relevant:

- Purpose and intended audience
- Required background
- Reliability problem
- User or business impact
- Technical explanation
- Assumptions and boundaries
- Production example
- Failure modes
- Tradeoffs
- Operational risks
- Safe implementation or investigation method
- Recovery or verification steps
- Practical exercise
- Related repository sections
- References to authoritative sources

### Original Content Must Not

- Present invented production experience as real
- Fabricate incidents, metrics, benchmarks, or citations
- Copy another author’s structure or language without permission
- Present a product-specific method as universally correct
- Hide important limitations
- Recommend destructive production action without warning and validation
- Use generic text only to fill an empty folder

Original VERIQTA material should be clearly identified as original repository content.

---

## 8. Contributing Incident Reports and Postmortems

Use the organization’s original public report whenever possible.

Include:

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

### Incident Contribution Rules

- Separate confirmed facts from your analysis.
- Label inference clearly.
- Do not invent details that the organization did not disclose.
- Do not blame individuals.
- Distinguish the triggering event from contributing conditions.
- Preserve the original timeline when one is available.
- Explain the customer impact.
- Identify detection, response, mitigation, recovery, and learning separately.
- Avoid declaring a single root cause when the evidence shows interacting factors.
- Link to the original incident report.
- Do not include private, leaked, or personally identifying information.

---

## 9. Contributing Templates, Runbooks, and Playbooks

### Templates

State:

- What decision or record the template supports
- Who should complete it
- Required inputs
- When it should be used
- Review and approval requirements
- Completion criteria

### Runbooks

A runbook should contain:

- Title and owner
- Purpose
- Trigger or alert
- Customer impact
- Preconditions
- Required access
- Safety warnings
- Diagnostic steps
- Expected evidence
- Mitigation options
- Stop conditions
- Escalation conditions
- Rollback guidance
- Recovery verification
- Follow-up work
- Last tested date

### Playbooks

A playbook should contain:

- Scenario and scope
- Roles and responsibilities
- Severity or activation criteria
- Decision points
- Communication requirements
- Containment options
- Recovery conditions
- Handover and closure requirements

Runbooks and playbooks should support judgment. They must not imply that every production condition has one safe, universal response.

---

## 10. Contributing Labs and Production Scenarios

Labs must be safe, repeatable, and legally authorized.

Include:

- Learning objective
- Intended experience level
- Environment assumptions
- Required tools or access
- Estimated time
- Cost warning
- Safety boundaries
- Initial state
- Failure introduced
- Customer-visible symptoms
- Available evidence
- Expected investigation method
- Mitigation options
- Recovery verification
- Cleanup steps
- Reflection questions

### Lab Safety Rules

- Never instruct learners to test on systems they do not own or have permission to use.
- Use isolated environments.
- Avoid real customer data.
- Do not include real credentials.
- Warn about cloud charges and resource cleanup.
- Bound fault injection by time, scope, and target.
- Provide a reliable stop or recovery method.
- Explain how to confirm that cleanup succeeded.

Production scenarios should test investigation and decision-making, not only command recall.

---

## 11. Making Corrections

Corrections are encouraged when they improve accuracy or safety.

A correction should include:

- The current statement or location
- The proposed correction
- Why the current content is wrong or unclear
- Supporting primary or authoritative evidence
- Any effect on related sections

Do not rewrite an entire page when a focused correction is sufficient.

Maintainers may request a separate pull request for unrelated corrections.

---

## 12. Repository Structure

Place content in the most specific primary folder.

```text
SRE-WORLD/
├── 01-SRE-Foundations/
├── 02-Service-Ownership/
├── 03-SLIs-SLOs-and-SLAs/
├── 04-Error-Budgets/
├── 05-Reliability-Measurement/
├── 06-Observability-Engineering/
├── 07-Alerting-Engineering/
├── 08-On-Call-Engineering/
├── 09-Incident-Management/
├── 10-Troubleshooting-and-Debugging/
├── 11-Postmortems-and-Learning/
├── 12-Toil-and-Automation/
├── 13-Production-Readiness/
├── 14-Change-and-Release-Reliability/
├── 15-Capacity-Planning/
├── 16-Performance-and-Load/
├── 17-Distributed-Systems-Reliability/
├── 18-Resilience-Engineering/
├── 19-Disaster-Recovery/
├── 20-Data-Reliability/
├── 21-Network-Reliability/
├── 22-Cloud-Reliability/
├── 23-Kubernetes-Reliability/
├── 24-Security-and-Reliability/
├── 25-Reliability-Architecture/
├── 26-SRE-Organizations-and-Culture/
├── 27-SRE-Maturity-and-Governance/
├── 28-SRE-Leadership/
├── 29-SRE-Case-Studies/
├── 30-Production-Incidents/
├── 31-SRE-Projects-and-Labs/
├── 32-SRE-Interview-Scenarios/
├── 33-SRE-Research-Papers/
├── 34-Books-Talks-and-Courses/
├── 35-SRE-Career-Development/
├── Reliability-Patterns/
├── SLO-Examples/
├── Incident-Library/
├── Decision-Records/
├── Production-Failure-Library/
├── Learning-Paths/
├── Templates/
├── Checklists/
├── Runbooks/
├── Playbooks/
├── Worksheets/
├── Failure-Labs/
└── Glossary/
```

Use cross-references instead of copying the same resource into multiple folders.

If placement is unclear, use the domain that represents the resource’s primary learning outcome.

---

## 13. File Naming

Use descriptive Markdown filenames with hyphens:

```text
Designing-Availability-SLIs.md
Multi-Window-Burn-Rate-Alerts.md
Incident-Command-Checklist.md
Regional-Failover-Game-Day.md
```

Do not use vague filenames:

```text
notes.md
new.md
resource.md
links2.md
final-final.md
```

Rules:

- Use `.md` for Markdown files.
- Use `README.md` for a folder landing page.
- Use hyphens between words.
- Preserve approved acronyms such as `SRE`, `SLO`, `RTO`, and `RPO`.
- Avoid dates in filenames unless the content is a time-bound report.
- Do not rename existing files only for personal style preferences.

---

## 14. Resource IDs

Use the ID system defined in [RESOURCE-STANDARD.md](./RESOURCE-STANDARD.md):

```text
SRE-[DOMAIN]-[TYPE]-[NUMBER]
```

Examples:

```text
SRE-SLO-BOOK-001
SRE-INC-POST-004
SRE-OBS-TALK-012
SRE-DIST-PAPER-006
```

- Use three digits for the number.
- Do not reuse retired IDs.
- Do not change an ID because a title or URL changes.
- Check the folder and changelog before selecting a number.
- Maintainers may assign the final ID during review.

---

## 15. Writing Standard

Use:

- Clear and direct language
- Descriptive headings
- Short or medium sentences
- Accurate technical terms
- Concrete production examples
- Explicit assumptions
- Practical risks and tradeoffs
- Relative links for repository content
- Descriptive labels for external links

Avoid:

- Promotional language
- Excessive emojis
- Decorative Unicode text
- Unexplained acronyms
- Empty phrases such as “best practice” without context
- Long quotations
- Copied source descriptions
- Artificial keyword repetition
- Presenting one company’s approach as universally correct
- Claiming that one tool automatically creates reliability

### Markdown Rules

- Use one `#` heading for the page title.
- Use `##` and `###` headings in logical order.
- Add a blank line before and after lists, tables, and code blocks.
- Add alternative text to images.
- Use fenced code blocks with a language when applicable.
- Check that relative links resolve from the file’s location.
- Keep tables readable. Use lists when tables become too wide.

---

## 16. Technical Accuracy and Operational Safety

Contributions must:

- Separate fact, opinion, and inference
- State environment assumptions
- Explain significant tradeoffs
- Identify potentially destructive operations
- Use least privilege
- Avoid hardcoded credentials
- Avoid exposing personal or private data
- Include stop, rollback, or containment conditions where appropriate
- Include recovery verification
- Consider blast radius
- Identify when a procedure is product-specific
- Prefer reversible actions under uncertainty

### High-Risk Actions

The following require explicit safeguards and context:

- Deleting or replacing data
- Restarting production components
- Disabling alerts or health checks
- Forcing leader election or failover
- Changing routing or DNS
- Scaling resources rapidly
- Rolling back application or database changes
- Modifying access controls
- Injecting faults
- Running automated remediation

Never describe a high-risk action as universally safe.

---

## 17. Attribution, Copyright, and Licensing

Contributors must:

- Credit original authors and publishers.
- Link to authorized sources.
- Write summaries in original language.
- Preserve required license notices.
- Confirm permission for contributed images, diagrams, code, templates, and datasets.
- Mark adapted material and identify its license.
- Respect the repository’s license.

Do not:

- Upload copyrighted books or paid course material.
- Copy full articles or transcripts.
- Copy diagrams without permission.
- Submit content from private company systems.
- Include confidential incident information.
- Remove watermarks or attribution.
- Imply that an author or organization endorses SRE World.

When permission is unclear, link to the source instead of copying it.

By contributing original content, you confirm that you have the right to submit it under the repository’s license.

---

## 18. Vendor and Relationship Disclosure

Disclose whether you:

- Work for the organization that created the resource
- Created or co-created the resource
- Receive payment, commission, referrals, or other benefit
- Maintain the product or project
- Have another relationship that may affect your recommendation

Use a clear statement:

```text
Disclosure: I work for the organization that publishes this resource.
```

or:

```text
Disclosure: I have no financial or professional relationship with the author or organization.
```

A disclosed relationship does not automatically disqualify a contribution. An undisclosed relationship may result in rejection or removal.

---

## 19. Git and Pull Request Workflow

### Option A: Edit Through GitHub

For small corrections:

1. Open the file on GitHub.
2. Select the edit option.
3. Make one focused change.
4. Add a clear commit message.
5. Propose the change in a pull request.

### Option B: Work Locally

For larger contributions:

1. Fork the repository.
2. Clone your fork.
3. Create a branch.
4. Make the change.
5. Review the diff.
6. Commit the change.
7. Push the branch to your fork.
8. Open a pull request against the main SRE World repository.

Example:

```bash
git clone https://github.com/YOUR-USERNAME/SRE-WORLD.git
cd SRE-WORLD
git switch -c add-slo-resource
```

After editing:

```bash
git status
git diff
git add 03-SLIs-SLOs-and-SLAs/
git commit -m "Add verified SLO design resource"
git push -u origin add-slo-resource
```

Replace `YOUR-USERNAME` with your GitHub username.

### Branch Names

Use clear branch names:

```text
add-slo-resource
fix-broken-incident-link
update-capacity-template
correct-burn-rate-example
```

Avoid:

```text
changes
new
test
my-branch
```

---

## 20. Commit Messages

Use a short, specific message written in the imperative form.

Good examples:

```text
Add verified SLO design resource
Fix broken incident report link
Clarify retry budget calculation
Add regional failover game day
Update Kubernetes reliability references
```

Avoid:

```text
Update
Changes
Fixed stuff
Final
Work done
```

Keep unrelated changes in separate commits or pull requests.

---

## 21. Pull Request Requirements

Use this description:

```text
## Contribution Type

- [ ] New resource
- [ ] Original content
- [ ] Incident report or postmortem
- [ ] Template, runbook, playbook, or checklist
- [ ] Lab or production scenario
- [ ] Correction
- [ ] Broken or outdated link
- [ ] Documentation or navigation improvement

## Summary

Describe the change.

## SRE Relevance

Explain which SRE responsibility or production problem this contribution supports.

## Repository Location

List the folder and file changed.

## Verification

Explain how the source, link, calculation, procedure, or lab was verified.

## Production Value

Explain how an SRE practitioner can use the contribution.

## Risks or Limitations

List important boundaries, assumptions, safety concerns, or missing coverage.

## Disclosure

State any relationship with the author, vendor, organization, or project.

## Checklist

- [ ] I reviewed the complete resource or content.
- [ ] I searched for duplicates.
- [ ] I followed RESOURCE-STANDARD.md.
- [ ] I used the correct folder and file format.
- [ ] I verified all links.
- [ ] I wrote descriptions in my own words.
- [ ] I documented important limitations.
- [ ] I checked technical accuracy and operational safety.
- [ ] I respected copyright and licensing requirements.
- [ ] I disclosed relevant relationships.
- [ ] I checked the rendered Markdown and internal links.
```

### Keep Pull Requests Focused

A pull request should normally address one subject.

Examples:

- Add one resource or a closely related group.
- Correct one concept and its connected examples.
- Add one template and its documentation.
- Repair one set of related links.

Large unrelated changes are harder to review and may be returned for separation.

---

## 22. Review Process

Contributions pass through these checks:

```text
Contribution submitted
        ↓
Scope and SRE relevance
        ↓
Source and link verification
        ↓
Technical accuracy and safety
        ↓
Duplicate and classification review
        ↓
Writing and structure review
        ↓
Accept, request changes, or reject
```

Maintainers may:

- Ask for a primary source
- Request technical evidence
- Correct the domain or experience level
- Assign a different resource ID
- Ask for safety or limitation notes
- Request a smaller pull request
- Edit wording for consistency
- Delay acceptance until a specialist reviews the content
- Decline content that does not strengthen the repository

Submitting a contribution does not guarantee acceptance.

### Review Outcomes

#### Accepted

The contribution meets the repository standard and may be merged.

#### Changes Requested

The idea is useful, but accuracy, evidence, classification, safety, structure, or writing must be improved.

#### Rejected

The contribution is outside scope, duplicated, unsafe, misleading, promotional, unauthorized, or below the required quality level.

---

## 23. Reasons a Contribution May Be Rejected

A contribution may be rejected when it:

- Does not pass the SRE relevance test
- Duplicates an existing canonical resource
- Uses a weak secondary source when a stronger primary source is available
- Contains inaccurate technical claims
- Omits important risk or limitation information
- Encourages unsafe production action
- Includes unauthorized copyrighted material
- Includes confidential, private, or personal information
- Contains undisclosed promotional or affiliate intent
- Uses fabricated examples as real incidents
- Uses unverified AI-generated content
- Adds volume without meaningful value
- Does not follow the repository structure
- Does not address requested review changes
- Combines too many unrelated changes
- Violates the Code of Conduct

Rejection applies to the contribution, not the contributor. A declined proposal may be revised and resubmitted when the underlying issue can be corrected.

---

## 24. Contributor Checklist

Before submitting, confirm:

- [ ] My contribution is specifically relevant to Site Reliability Engineering.
- [ ] I reviewed the complete source or tested the original content.
- [ ] I searched by title, URL, author, and subject for duplicates.
- [ ] I selected the correct primary domain.
- [ ] I used the required resource format where applicable.
- [ ] I verified all external links.
- [ ] I used relative links for repository content.
- [ ] I wrote descriptions and summaries in my own words.
- [ ] I stated important assumptions and limitations.
- [ ] I considered production risk, blast radius, rollback, and verification.
- [ ] I did not include secrets, personal data, or confidential information.
- [ ] I respected copyright and licensing requirements.
- [ ] I disclosed relevant relationships.
- [ ] My filenames and headings follow the repository standard.
- [ ] My pull request contains one focused contribution.
- [ ] My commit message clearly describes the change.
- [ ] I checked the rendered Markdown.
- [ ] I am willing to address review feedback.

---

## 25. Maintainer Responsibilities

Maintainers should:

- Apply the resource standard consistently
- Review contributions respectfully
- Explain requested changes clearly
- Prefer evidence over personal preference
- Separate technical concerns from stylistic choices
- Protect the repository from low-quality or unsafe material
- Avoid undisclosed conflicts of interest
- Preserve contributor attribution
- Record material additions and removals in `CHANGELOG.md`
- Reverify accepted resources over time
- Correct mistakes transparently
- Enforce the Code of Conduct

Maintainers retain final editorial responsibility for repository scope, structure, and quality.

---

## Questions and Proposals

Use a GitHub issue when:

- You are unsure whether a contribution belongs.
- You want to propose a new collection or major structural change.
- The contribution will require substantial work.
- You need clarification about licensing or placement.
- You want to coordinate a multi-file contribution.

For security concerns involving the repository itself, use GitHub’s private vulnerability reporting feature when available. Do not publish secrets or exploitable private information in a public issue.

---

## Recognition

SRE World values contributors who improve its accuracy, clarity, safety, and practical usefulness.

Accepted contributions remain visible in Git history. Significant contributions may also be recognized in release notes or repository acknowledgements.

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

Thank you for contributing production knowledge that helps engineers build and operate more reliable systems.
