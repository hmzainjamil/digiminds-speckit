# digiminds-speckit

> **Spec before you ship** — 6-step SDD spec generator for AI agency workflows | feature → spec → tasks → implementation, zero ambiguity

<div align="center">

[![Stars](https://img.shields.io/github/stars/hmzainjamil/digiminds-speckit?style=flat&color=FFD700&labelColor=555)](https://github.com/hmzainjamil/digiminds-speckit/stargazers)
[![Forks](https://img.shields.io/github/forks/hmzainjamil/digiminds-speckit?style=flat&color=00BFFF&labelColor=555)](https://github.com/hmzainjamil/digiminds-speckit/network)
[![Issues](https://img.shields.io/github/issues/hmzainjamil/digiminds-speckit?style=flat&color=FF6347&labelColor=555)](https://github.com/hmzainjamil/digiminds-speckit/issues)
[![PRs](https://img.shields.io/github/issues-pr/hmzainjamil/digiminds-speckit?style=flat&color=32CD32&labelColor=555)](https://github.com/hmzainjamil/digiminds-speckit/pulls)
[![Last Commit](https://img.shields.io/github/last-commit/hmzainjamil/digiminds-speckit?style=flat&color=9370DB&labelColor=555)](https://github.com/hmzainjamil/digiminds-speckit/commits)

</div>

<div align="center">

![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-FF6B35?labelColor=555&style=flat)
![SDD](https://img.shields.io/badge/SDD-6_Step-2196F3?labelColor=555&style=flat)
![DigiMinds](https://img.shields.io/badge/DigiMinds-Agency-E91E63?labelColor=555&style=flat)
![AI Agents](https://img.shields.io/badge/AI_Agents-Orchestration-9C27B0?labelColor=555&style=flat)
![Automation](https://img.shields.io/badge/Automation-Workflows-4CAF50?labelColor=555&style=flat)
![No Code Before Spec](https://img.shields.io/badge/Rule-No_Code_Before_Spec-FF5722?labelColor=555&style=flat)

</div>

---

## Why This Exists

Agencies die from scope creep and misunderstood requirements. Developers start coding without a clear spec, stakeholders change minds mid-sprint, and everyone wastes time building the wrong thing precisely.

DigiMinds SpecKit enforces a non-negotiable rule: **no code before spec**.

It's a Claude Code skill that runs a structured 6-step Software Design Document (SDD) process before any implementation begins — built specifically for the DigiMinds AI agency workflow where AI agents, automation pipelines, and client deliverables require crystal-clear specs to function correctly.

---

## ☠️ STARTUPS / BUSINESSES

Every hour of rework costs 3–5x the original build time. Agencies that spec first ship 2x faster and have 80% fewer revision cycles. If your team is "moving fast" without specs, you're actually moving slow — just with confidence.

- **AI agencies** — client deliverables built on vague briefs = endless revisions
- **Dev shops** — spec gate prevents "we already built it wrong" conversations
- **Freelancers** — spec approval creates a paper trail that protects your time
- **Product teams** — spec freeze means no mid-sprint scope creep

---

## At a Glance

| Property | Detail |
|---|---|
| **Skill type** | Claude Code skill (SKILL.md) |
| **Process** | 6-step SDD: Extract → Research → Analyze → Plan → Tasks → Implement |
| **Output** | Full spec doc, task breakdown, implementation plan |
| **Agency** | DigiMinds — AI-powered digital marketing agency |
| **Use cases** | Features, automations, agent workflows, client deliverables |
| **Slash commands** | `/speckit.specify`, `/speckit.plan`, `/speckit.tasks`, `/speckit.implement` |
| **Integration** | MAE pipeline, Claude Code, Paperclip OS |
| **Spec format** | Markdown SDD with sections, acceptance criteria, edge cases |
| **Task format** | Numbered atomic tasks with dependencies |
| **Review gate** | Human approval required between spec and implementation |
| **Memory** | Spec saved to session memory for context persistence |
| **Enforcement** | Refuses to write code if spec not approved |

---

## 🧠 CONCEPTS

| Concept | Definition |
|---|---|
| **SDD** | Software Design Document — structured blueprint before implementation |
| **Stage 1: Extract** | Pull all requirements from user prompt/brief |
| **Stage 2: Research** | Identify unknowns, dependencies, existing patterns |
| **Stage 3: Analyze** | Edge cases, constraints, technical tradeoffs |
| **Stage 4: Plan** | Architecture decisions, component breakdown |
| **Stage 5: Tasks** | Atomic numbered task list with dependencies |
| **Stage 6: Implement** | Code generation against approved spec |
| **Acceptance Criteria** | Testable conditions for "done" — no ambiguity |
| **Edge Case Matrix** | Grid of inputs × expected behaviors |
| **Review Gate** | Mandatory human sign-off between plan and execution |
| **Atomic Task** | Smallest indivisible unit of work — one sitting |
| **Spec Freeze** | Locked spec state — no changes without new SpecKit run |
| **Dependency Map** | Task A must complete before Task B can start |
| **Constraint Register** | Known limitations: time, tech, integrations, budget |
| **Risk Matrix** | Probability × impact for each identified risk |
| **RACI** | Responsible/Accountable/Consulted/Informed per task |

---

### 🔥 Hot

```bash
# Full 6-step SDD for a new feature
python3 ~/.claude/bin/speckit-mae-bridge run "feature: AI-powered lead scoring agent for CRM"

# Step-by-step with slash commands
/speckit.specify "build webhook intake for n8n → Apollo CRM sync"
/speckit.plan     # Architecture decisions
/speckit.tasks    # Numbered atomic task list
/speckit.implement # Code after approval

# Force spec gate (refuses code without approved spec)
claude speckit "implement OAuth2 flow for client portal"

# Generate edge case matrix only
/speckit.analyze "file upload feature: PDF, DOCX, images, 50MB limit"

# Spec existing codebase
/speckit.specify "reverse-spec this Python file: [paste code]"
```

---

## Installation

```bash
# Clone to Claude Code skills directory
git clone https://github.com/hmzainjamil/digiminds-speckit ~/.claude/skills/digiminds-speckit

# Verify SKILL.md
ls ~/.claude/skills/digiminds-speckit/SKILL.md

# Link the MAE bridge (if using MAE pipeline)
ln -sf ~/.claude/skills/digiminds-speckit/bin/speckit-mae-bridge.py ~/.claude/bin/speckit-mae-bridge

# Add to CLAUDE.md for auto-enforcement
echo "Rule: No code before spec. Run /speckit.specify first." >> ~/.claude/CLAUDE.md
```

---

## The 6-Stage Process

### Stage 1: Extract
```
Input:  "Build a lead capture form with CRM sync"
Output: - Requirements list (functional + non-functional)
        - Stakeholders identified
        - Constraints noted (timeline, tech, integrations)
        - Open questions flagged for resolution
```

### Stage 2: Research
```
Output: - Existing patterns in codebase
        - Relevant libraries/frameworks
        - Similar implementations to reference
        - API documentation needed
        - Security considerations
```

### Stage 3: Analyze
```
Output: - Edge case matrix (input × expected behavior)
        - Technical tradeoffs (3 options with pros/cons)
        - Risk matrix (probability × impact)
        - Performance considerations
        - Test strategy outline
```

### Stage 4: Plan
```
Output: - Architecture diagram (ASCII)
        - Component breakdown
        - Data flow diagram
        - API contract (request/response shapes)
        - Database schema changes
```

### Stage 5: Tasks
```
Output: - Numbered atomic task list
        - Dependencies mapped (Task 3 requires Task 1)
        - Estimated complexity (S/M/L/XL)
        - RACI per task
        - Definition of Done per task
```

### Stage 6: Implement
```
Trigger: Human approval of spec (explicit sign-off required)
Output:  - Code matching spec exactly
         - Tests for acceptance criteria
         - No scope additions without new spec run
```

---

## SDD Document Template

```markdown
# Feature: [Name]
**Status:** Draft | Review | Approved | Frozen
**Date:** YYYY-MM-DD
**Author:** [Name]

## 1. Problem Statement
[What problem does this solve? Why now?]

## 2. Requirements
### Functional
- [ ] FR-01: [Requirement]
### Non-functional
- [ ] NFR-01: Performance — [threshold]
- [ ] NFR-02: Security — [requirement]

## 3. Acceptance Criteria
| ID | Given | When | Then |
|---|---|---|---|
| AC-01 | User is logged in | Submits form | Lead created in CRM |

## 4. Edge Cases
| Input | Expected | Error |
|---|---|---|
| Empty email | Validation error | Show inline error |

## 5. Architecture
[ASCII diagram]

## 6. Tasks
1. [ ] Task 1 (S) — no deps
2. [ ] Task 2 (M) — requires Task 1
```

---

## Slash Command Reference

| Command | Stage | Output |
|---|---|---|
| `/speckit.specify [brief]` | 1–2 | Requirements + open questions |
| `/speckit.analyze [feature]` | 3 | Edge cases + tradeoffs + risks |
| `/speckit.plan [requirements]` | 4 | Architecture + components + API |
| `/speckit.tasks [plan]` | 5 | Numbered atomic task list |
| `/speckit.implement` | 6 | Code (requires approved spec) |
| `/speckit.review [spec]` | All | Quality check against SDD standards |
| `/speckit.freeze` | Post-approval | Lock spec, generate change-log on edits |

---

## Integration with MAE Pipeline

```bash
# Full automated SDD pipeline via MAE
mae run "speckit: AI content calendar automation for DigiMinds"

# Batch spec generation
tcc blast \
  "speckit: lead scoring agent" \
  "speckit: CRM webhook sync" \
  "speckit: client reporting dashboard"

# Queue for async processing
tcc fire all
```

---

## Comparison: With vs Without SpecKit

| Metric | No Spec | With SpecKit |
|---|---|---|
| Rework cycles | 3–5 | 0–1 |
| Scope creep rate | High | Near zero |
| Dev start time | Immediate | +30 min spec |
| Total delivery time | +40% (rework) | On estimate |
| Client revisions | 5–10 | 1–2 |
| Documentation | Post-hoc/none | Built-in |
| Team onboarding | "Ask dev X" | Read the spec |

---

## Edge Case Matrix Example

| Input | Condition | Expected | Error Message |
|---|---|---|---|
| `email: ""` | Empty | Validation fail | "Email is required" |
| `email: "notanemail"` | Invalid format | Validation fail | "Enter valid email" |
| `email: "x@x.x"` | Edge case short | Pass validation | — |
| `file: 51MB PDF` | Over limit | Reject with error | "Max file size 50MB" |
| `file: .exe` | Wrong type | Reject with error | "PDF and DOCX only" |
| `API: timeout` | Network error | Retry 3x then fail | "Connection failed, retry" |

---

## ■ Tips

> **Spec freeze is the most important discipline**
> Once spec is approved: changes require a new /speckit.specify run.
> Mid-implementation changes cost 4x as much as pre-spec changes.
> Source: [Boehm's Cost of Change Curve](https://www.cs.umd.edu/~mvz/handouts/cost-to-fix.pdf)

> **Acceptance criteria must be testable, not aspirational**
> Bad: "The form should be user-friendly"
> Good: "Form submits in <500ms and shows success message within 1s"
> Source: [BDD — Cucumber docs](https://cucumber.io/docs/bdd/better-gherkin/)

> **Atomic tasks = parallelizable work**
> If a task takes more than one day, split it.
> If it can't be parallelized, it's a blocker — flag it early.

> **The SDD is the contract with future-you**
> In 3 months, you'll have no memory of why you made this decision.
> The spec is the only record.

---

## Troubleshooting

| Issue | Cause | Fix |
|---|---|---|
| Skill not enforcing spec gate | CLAUDE.md rule missing | Add "Rule: No code before spec" to CLAUDE.md |
| Tasks too large | Stage 5 needs split | Re-run `/speckit.tasks` with "split all tasks >1 day" |
| Open questions never resolved | Missing stakeholder input | Escalate list in Stage 1 output |
| Spec keeps changing | No freeze applied | Run `/speckit.freeze` after approval |
| Edge cases missing | Brief too vague | Add "generate exhaustive edge case matrix" to prompt |

---

## File Structure

```
digiminds-speckit/
├── SKILL.md              # Core skill definition
├── bin/
│   └── speckit-mae-bridge.py  # MAE integration
├── templates/
│   ├── sdd.md            # SDD template
│   ├── acceptance.md     # AC template
│   └── edge-cases.md     # Edge case matrix template
└── examples/
    ├── lead-capture.md   # Real SDD example
    └── crm-sync.md       # Real SDD example
```

---

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=hmzainjamil/digiminds-speckit&type=Date)](https://star-history.com/#hmzainjamil/digiminds-speckit&Date)

---

<div align="center">

Built by [hmzainjamil](https://github.com/hmzainjamil) · Core tool of [DigiMinds AI Agency](https://github.com/hmzainjamil)

</div>

---

## Spec Anti-Patterns

| Anti-Pattern | Problem | Fix |
|---|---|---|
| "Make it work like Slack" | Scope undefined, impossible to test | Define exact features needed, not product references |
| "Improve performance" | No baseline, no target | Specify: "reduce page load from Xms to Yms" |
| "Nice to have" items in spec | Scope creep magnet | Separate MVP spec from future backlog explicitly |
| Code before spec approval | Rework when requirements change | Enforce review gate strictly |
| Spec written by non-implementer | Missing technical constraints | Dev + stakeholder co-write spec |
| Acceptance criteria too vague | "Done" is subjective | Every AC must be testable with a specific assertion |
| No edge case matrix | Unexpected inputs break production | Always run Stage 3 Analyze fully |

---

## SDD Quality Checklist

Before approving a spec, verify:

| Check | Pass condition |
|---|---|
| Problem statement clear | Anyone can understand the why in 30 seconds |
| All functional requirements numbered | FR-01, FR-02... no orphan requirements |
| Non-functional requirements defined | Performance, security, reliability thresholds set |
| Acceptance criteria testable | Each AC has Given/When/Then format |
| Edge case matrix complete | At least 5 edge cases per input type |
| Architecture diagram exists | ASCII or Mermaid diagram included |
| Task list atomic | Each task completable in <1 day |
| Dependencies mapped | No hidden assumptions in task ordering |
| Open questions resolved | No "TBD" in approved spec |
| Reviewer sign-off logged | Name + date of approval recorded |

---

## Integration Patterns

### SpecKit + Claude Code Workflow

```
1. User prompts: "Build X"
2. SpecKit intercepts → runs /speckit.specify
3. Stage 1-4 complete → spec doc generated
4. Human reviews → approves or requests changes
5. /speckit.tasks → atomic task list
6. Human approves tasks
7. /speckit.implement → Claude executes against spec
8. Tests run against acceptance criteria
9. All ACs pass → feature complete
```

### SpecKit + MAE Pipeline

```bash
# MAE automatically runs SpecKit for new features
mae run "feature: [description]"
# → routes to speckit-mae-bridge.py
# → stages 1-4 auto-complete
# → human review gate
# → tasks assigned to specialist agents
# → implementation parallelized
```

### Version Control for Specs

```
docs/
└── specs/
    ├── feature-auth/
    │   ├── v1-initial.md      # original spec
    │   ├── v2-revised.md      # after stakeholder review
    │   └── v3-frozen.md       # approved, locked
    ├── feature-billing/
    └── feature-reporting/
```

---

## Metrics: SpecKit ROI

| Metric | Before SpecKit | After SpecKit |
|---|---|---|
| Revision cycles per feature | 4.2 | 0.8 |
| Scope creep incidents/month | 8 | 1 |
| Time to first working build | 2 weeks | 4 days |
| Documentation coverage | 20% | 100% |
| Onboarding time for new dev | 2 weeks | 3 days |
| Post-release bug count | High | Low |

*Metrics based on DigiMinds internal project tracking*

---

## Related Tools

| Tool | Role | Integration |
|---|---|---|
| `claude-mem-main` | Persist approved specs across sessions | Spec written to memory on approval |
| `mae-master-automation-engine` | Orchestrate SpecKit stages | `mae run "speckit: ..."` |
| `llm-agents-bundle` | Execute tasks from spec | Pass task list to agent pipeline |
| `digiminds-master` | Agency OS | SpecKit runs as part of every client project |

