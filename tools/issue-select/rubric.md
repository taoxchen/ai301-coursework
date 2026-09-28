# Rubric: is this a good first issue?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| repo-active | Repo facts: `archived:` flag, `last 5 default-branch commits` dates, `last push to any branch` date | Fails if `archived: yes`. Otherwise fails unless at least one default-branch commit or a push to any branch is dated within 90 days of the capture date (live mode: today). | required |
| unclaimed | Repo facts: `this issue: assignees:` and `linked PRs:` lines; the Comments section | Fails if the assignees list is non-empty, or any linked PR is open, or the comment thread has a claim ("I'll take this" / "working on this" / "can I work on this") that is not itself contradicted by a later comment (author saying they've dropped it) or superseded by the issue being reopened/unassigned. A closed, unmerged linked PR with no assignee and no recent (90-day) claim activity is an abandoned attempt, not a claim: passes. | required |
| scope-bounded | Issue title, body, and comment thread | Fails if any of: (a) the issue is explicitly a tracking/umbrella issue listing sub-items meant to be split into separate work; (b) the thread shows the design/approach is still being actively debated with no maintainer decision recorded; (c) a maintainer states the fix requires changes to core internals; (d) the issue is a usage/support question ("how do I...") rather than a proposed change. A short or terse write-up that still names one bounded change passes; polish is not scope. | required |
| ai-policy-ok | Repo facts: `contribution policy` line | Fails only if the policy explicitly states AI-generated code/contributions are not accepted. Disclosure, human-review, or testing conditions do not fail this check. No stated policy passes. | required |
| good-first-issue-label | Issue labels | Passes if the issue carries a `good first issue` / `good-first-issue` / equivalent label. | preferred |
| maintainer-responsive | Repo facts: `maintainer first-response sample` | Passes if at least one sampled issue got an Owner/Member/Collaborator first response within 14 days. | preferred |

## Verdict rule

Accept only if every `required` check passes. A single `required` check graded
`fail` rejects the issue; a `required` check graded `unclear` also counts as a
fail (evidence needed to clear it is genuinely missing, so don't take the
issue on a guess). `preferred` checks never change the verdict — report their
grades and use them only to rank issues that are already accepted (prefer a
labelled issue over an unlabelled one; among otherwise-equal accepted issues,
prefer the one with a faster sampled maintainer response).
