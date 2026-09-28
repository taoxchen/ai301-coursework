# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/57

**Verdict output**

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
**Ranking**

1. **#57 (accept)**: Tech detector counts vendored and build-output files. This is the only candidate that clears the rubric. It's a Python logic bug with a runnable repro and two named failing tests, `test_node_modules_excluded` and `test_build_directory_excluded`. That fits your profile: backend debugging, no UI work, small and bounded.
2. **#60 (reject)**: Faithfulness checker crashes on `text: None`. Open PR #80 ("Fixes #60") from pakmultilinks-dot sank it.
3. **#54 (reject)**: Resume section detection fails on leading whitespace. Open PR #76 ("Closes #54") from Tiyatrotist sank it.

**How the house rule applied.** It waives claim comments only. The `unclaimed` check treats an open linked PR as a separate disqualifier, and the house rule doesn't touch that. So the "I'll take this" comment on #57 and the five claim comments on #54 were ignored. The open PRs on #60 and #54 were not.

**Repo-wide checks**
- **repo-active:** passes. The repo isn't archived, and the last default-branch commit and last push were 2026-09-16, 11 days before today (2026-09-27).
- **ai-policy-ok:** passes. `docs/CONTRIBUTING.md` and the PR template contain no AI restriction.
- **maintainer-responsive:** fails for all three. I found no Owner, Member or Collaborator comments on any recent issue. Aburke225, a collaborator, opened the issues but hasn't replied on them. This is preferred-only and doesn't change any verdict.

**Per issue**
- **#57:**
  - `unclaimed` passes. There is no assignee and no PR, linked or mentioned. The only claim comment is from ApoorvThite on 09-21, which the house rule ignores.
  - `scope-bounded` passes. It's one bounded fix.
  - It carries the `good first issue` label.
- **#60:**
  - `unclaimed` fails because PR #80 is open and linked.
  - Everything else passes, including the label.
- **#54:**
  - `unclaimed` fails because PR #76 is open and linked.
  - Everything else passes, including the label.

Two things worth knowing:
- **#57 is contested.** ApoorvThite claimed it on 09-21 with no PR yet, so a classmate may open one first. The rubric doesn't count that against it here.
- **Several PRs are open at once.** pakmultilinks-dot opened PRs on #53, #56, #60, #61, #62, #69 and #72 within about ten minutes of each other, so I'd expect more issues to get covered quickly. #57 is unlikely to stay open long.

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/57",
    "checks": [
      {"name": "repo-active", "grade": "pass", "evidence": "archived: false; last default-branch commit and push 2026-09-16, 11 days before today (2026-09-27)"},
      {"name": "unclaimed", "grade": "pass", "evidence": "assignees: []; no linked or mentioned PR; only a claim comment (ApoorvThite, 2026-09-21), which the Path Review house rule ignores"},
      {"name": "scope-bounded", "grade": "pass", "evidence": "One bounded change: exclude node_modules/ and build/ paths in tech_detector.py; repro and two named failing tests given"},
      {"name": "ai-policy-ok", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PR template contain no AI restriction; no ban stated"},
      {"name": "good-first-issue-label", "grade": "pass", "evidence": "Labels: bug, good first issue, agent, tier-1"},
      {"name": "maintainer-responsive", "grade": "fail", "evidence": "No Owner/Member/Collaborator comments found on any recent issue; sampled issues have no maintainer first response"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/60",
    "checks": [
      {"name": "repo-active", "grade": "pass", "evidence": "archived: false; last default-branch commit and push 2026-09-16, 11 days before today"},
      {"name": "unclaimed", "grade": "fail", "evidence": "Open linked PR #80 'fix: tolerate None text in faithfulness checker context chunks' (body: 'Fixes #60'), opened 2026-09-27; claim comment from pkmaster21 ignored per house rule"},
      {"name": "scope-bounded", "grade": "pass", "evidence": "Single bounded bug: chunk.get('text', '') returns None when key is present with None value; repro and failing test named"},
      {"name": "ai-policy-ok", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PR template contain no AI restriction; no ban stated"},
      {"name": "good-first-issue-label", "grade": "pass", "evidence": "Labels: bug, good first issue, rag, tier-1"},
      {"name": "maintainer-responsive", "grade": "fail", "evidence": "No Owner/Member/Collaborator comments found on any recent issue"}
    ],
    "verdict": "reject"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/54",
    "checks": [
      {"name": "repo-active", "grade": "pass", "evidence": "archived: false; last default-branch commit and push 2026-09-16, 11 days before today"},
      {"name": "unclaimed", "grade": "fail", "evidence": "Open linked PR #76 'fix: detect indented resume section headings' (body: 'Closes #54') by Tiyatrotist, opened 2026-09-27; five claim comments ignored per house rule"},
      {"name": "scope-bounded", "grade": "pass", "evidence": "One bounded bug: section-header regexes in _detect_sections() anchored at line start; repro and failing tests named"},
      {"name": "ai-policy-ok", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PR template contain no AI restriction; no ban stated"},
      {"name": "good-first-issue-label", "grade": "pass", "evidence": "Labels: bug, good first issue, ingestion, tier-1"},
      {"name": "maintainer-responsive", "grade": "fail", "evidence": "No Owner/Member/Collaborator comments found on any recent issue"}
    ],
    "verdict": "reject"
  }
]
```
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

Three runs, in order: (1) `--limit 4` smoke run: 4/4; (2) `--only issue-12,issue-17,issue-10,issue-13` spot-check of the policy, dead-repo, scope and claimed categories: 4/4; (3) the full 20-issue run: 18/20. The full run is the one committed as `eval-run.txt`, whose agreement line reads `agreement: 18/20 scored items  (bar: 18/20: PASS)`. I ran only one full run because of the credit budget.

**Issue analysis**

issue-20 (excalidraw/excalidraw#11811, "Add company logo shape to the toolbar"). My rubric said accept; the gold label is reject ("one-line feature wish with no spec and a product decision hiding inside"). My rubric passed every check except the preferred one: the grader wrote for scope-bounded, "Single bounded feature (logo toolbar shape) with explicit out-of-scope note ('custom logo upload / branding settings'); no tracking issue, no debate, no maintainer core-internals statement, not a support question". That is a literal reading of my condition: the issue names one change and states "Success looks like: logo tool in the shapes toolbar → place/resize/move like other elements → correct export." The catch it missed is "Logo asset TBD": which company's logo, and whether excalidraw wants a branded shape at all, is a product decision, and the issue was filed by cursor[bot] with no labels and no comments, so no maintainer has agreed the feature should exist. My scope-bounded conditions (a)-(d) only fail an issue for an umbrella list, an active debate, a maintainer's core-internals statement, or a support question, and none of those describes a request that no maintainer has endorsed.

**Check rationale**

Current wording in `tools/issue-select/rubric.md`:

> | scope-bounded | Issue title, body, and comment thread | Fails if any of: (a) the issue is explicitly a tracking/umbrella issue listing sub-items meant to be split into separate work; (b) the thread shows the design/approach is still being actively debated with no maintainer decision recorded; (c) a maintainer states the fix requires changes to core internals; (d) the issue is a usage/support question ("how do I...") rather than a proposed change. A short or terse write-up that still names one bounded change passes; polish is not scope. | required |

The reasoning: the evidence guide says scope fails on umbrella issues, unsettled design debate, core-internals changes and support questions, and that a terse write-up can still be a bounded first issue, so I encoded those four failure modes as the conditions and added the last sentence so a short issue is not failed for its polish. I made it a required check because scope was one of the four lecture families and the scope category in the eval set needs at least one matching verdict.

**Trade-offs**

The "polish is not scope" sentence, and the fact that the check only fails on four named patterns, is what lets two arguable issues through: issue-20 (a feature request nobody has endorsed) and issue-15 (zulip/zulip#19589, years of design debate with two closed PRs; my grader read the closed PRs as abandoned attempts and found no active debate). That is the 2 misses in 18/20, both in the scope category (scope 2/4). I am accepting that trade because tightening it to fail any request without a maintainer's endorsement risks failing the terse maintainer-filed issues that gold accepts (issue-04, issue-11, issue-14), and I did not have the budget to re-run the accepted-issue canaries with `--only` to check. So I changed nothing after the full run; the bar of 18 allows exactly these two arguable misses.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

1. Fit: #57 is a Python backend logic bug in the tech detector (vendored and build-output files skew language detection), which matches what I wanted to practice: debugging real logic rather than docs polish or UI. It is small and bounded, with a repro and two named failing tests (`test_node_modules_excluded`, `test_build_directory_excluded`), so it fits the time I have.
2. The verdict correctly saw that the repo is active (last push 2026-09-16), there is no assignee and no open or mentioned PR, the scope is one bounded fix, and there is no AI ban. What the rubric could not weigh: how likely a classmate is to open a PR first. The skill flagged that pakmultilinks-dot opened PRs on seven other issues within ten minutes, and that #60 and #54 (which I had considered) were already covered by open PRs.
3. Difficulty in claiming: ApoorvThite left a claim comment on 2026-09-21 and has no PR yet. Under the Path Review house rule that does not block me, but I will probably be one of several people on it, and someone may open a PR before I do, so I should move quickly.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
