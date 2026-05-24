# digiminds-speckit

> **Spec before you ship** — 6-step SDD spec generator for AI agency workflows | feature → spec → tasks → implementation, zero ambiguity

<div align="center">

[![Stars](https://img.shields.io/github/stars/hmzainjamil/digiminds-speckit?style=for-the-badge&color=FFD700&labelColor=555)](https://github.com/hmzainjamil/digiminds-speckit/stargazers)
[![Forks](https://img.shields.io/github/forks/hmzainjamil/digiminds-speckit?style=for-the-badge&color=00BFFF&labelColor=555)](https://github.com/hmzainjamil/digiminds-speckit/network)
[![Issues](https://img.shields.io/github/issues/hmzainjamil/digiminds-speckit?style=for-the-badge&color=FF6347&labelColor=555)](https://github.com/hmzainjamil/digiminds-speckit/issues)
[![PRs](https://img.shields.io/github/issues-pr/hmzainjamil/digiminds-speckit?style=for-the-badge&color=32CD32&labelColor=555)](https://github.com/hmzainjamil/digiminds-speckit/pulls)
[![Last Commit](https://img.shields.io/github/last-commit/hmzainjamil/digiminds-speckit?style=for-the-badge&color=9370DB&labelColor=555)](https://github.com/hmzainjamil/digiminds-speckit/commits)

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

It's a Claude Code skill that runs a structured 6-step Software Design Document (SDD) process before any implementation begins. Built specifically for the DigiMinds AI agency workflow — where AI agents, automation pipelines, and client deliverables require crystal-clear specs to function correctly.

The result: features shipped right the first time, with documented decisions that survive team changes.

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
| **Atomic Task** | Smallest indivisible unit of work — can be done in one sitting |
| **Spec Freeze** | Locked spec state — no changes without new SpecKit run |

### 🔥 Hot

- **Refuses to code without an approved spec** — hard gate enforced at skill level
- **Auto-generates acceptance criteria** from natural language requirements
- **Edge case matrix** generated automatically for every feature
- **Task dependency graph** visualized before implementation starts

---

## ⚙️ HOW IT WORKS

```
Feature request → Stage 1: EXTRACT requirements (what do we need?)
       ↓
Stage 2: RESEARCH (what do we know? what's unknown?)
       ↓
Stage 3: ANALYZE (edge cases, constraints, risks)
       ↓
Stage 4: PLAN (architecture, components, approach)
       ↓
Stage 5: TASKS (atomic numbered list with dependencies)
       ↓
[HUMAN REVIEW GATE — approval required]
       ↓
Stage 6: IMPLEMENT (code generation against locked spec)
```

Each stage produces a structured Markdown document. Stages 1-5 are spec-only — no code. Stage 6 only unlocks after human approval. This prevents the most common agency failure: building before understanding.

**Slash command flow:**
```bash
/speckit.specify  # Runs stages 1-3: extract + research + analyze
/speckit.plan     # Stage 4: architecture and approach
/speckit.tasks    # Stage 5: atomic task breakdown
/speckit.implement # Stage 6: implementation (requires prior spec)
```

---

## 🚀 INSTALL

### Option 1 — Clone into Claude skills directory

```bash
git clone https://github.com/hmzainjamil/digiminds-speckit.git \
  ~/.claude/skills/digiminds-speckit
```

### Option 2 — MAE pipeline integration

```bash
# Add to MAE skill manifest
mae skill add digiminds-speckit

# Verify
mae skill list | grep speckit
```

### Option 3 — Manual

```bash
mkdir -p ~/.claude/skills/digiminds-speckit
curl -sL https://raw.githubusercontent.com/hmzainjamil/digiminds-speckit/main/SKILL.md \
  -o ~/.claude/skills/digiminds-speckit/SKILL.md
```

### Option 4 — CLAUDE.md integration

```markdown
# In your CLAUDE.md:
## SPEC KIT — Run Before Any New Feature/Code
`python3 ~/.claude/bin/speckit-mae-bridge run "feature"` — full 6-step SDD
Slash commands: `/speckit.specify` `/speckit.plan` `/speckit.tasks` `/speckit.implement`
**Rule: No code before spec.**
```

---

## 📟 USAGE

### Full 6-step spec for a new feature

```
/speckit.specify build a lead capture form with Zapier webhook integration, GDPR consent, and Mailchimp sync
```

### Just the plan stage

```
/speckit.plan [paste your requirements brief here]
```

### Generate task breakdown from existing spec

```
/speckit.tasks [paste approved spec here]
```

### Implement from approved spec

```
/speckit.implement [paste approved spec + tasks]
```

### MAE bridge (automated)

```bash
python3 ~/.claude/bin/speckit-mae-bridge run "n8n automation: scrape LinkedIn → enrich → push to CRM"
```

### Direct CLI

```bash
# Full pipeline
speckit run "feature description"

# Just spec
speckit specify "feature description"

# Tasks only
speckit tasks "feature description"
```

---

## ⚙️ CONFIGURATION

| Config key | Default | Options | Description |
|---|---|---|---|
| `enforce_gate` | `true` | `true`, `false` | Require human approval before Stage 6 |
| `spec_format` | `markdown` | `markdown`, `notion`, `json` | Output format for spec docs |
| `task_granularity` | `atomic` | `atomic`, `sprint`, `epic` | Task breakdown level |
| `edge_case_depth` | `standard` | `minimal`, `standard`, `exhaustive` | How deep to dig on edge cases |
| `acceptance_criteria` | `gherkin` | `gherkin`, `checklist`, `bullet` | Format for acceptance criteria |
| `save_to_memory` | `true` | `true`, `false` | Persist spec to session memory |
| `review_checklist` | `true` | `true`, `false` | Include review checklist in spec |
| `dependency_graph` | `true` | `true`, `false` | Generate task dependency visualization |
| `risk_section` | `true` | `true`, `false` | Include risk assessment in spec |
| `agency_context` | `digiminds` | any string | Agency/project context for spec framing |
| `auto_implement` | `false` | `true`, `false` | Auto-start Stage 6 after approval |
| `spec_version` | `v1` | `v1`, `v2` | Spec template version |

---

## 💡 TIPS AND TRICKS

### Spec Quality

> **Front-load constraints** — tell SpecKit about budget, timeline, and tech stack in the initial prompt. Later changes invalidate the spec.

> **"Done" is a testable statement** — SpecKit forces acceptance criteria to be verifiable. "User can log in" is bad. "Given valid credentials, user is redirected to dashboard within 2s" is good.

> **Name your unknowns** — Stage 2 research will surface them, but naming them upfront speeds the process.

### Task Management

> **One task = one PR** — atomic tasks are designed to map to single pull requests. Resist combining them.

> **Dependencies first** — SpecKit generates a dependency graph. Always implement leaf tasks (no dependencies) first.

> **Time-box unknowns** — if a task has an unknown, add a spike task (2h max) before the implementation task.

### Agency Workflow

> **Client brief → SpecKit → proposal** — run SpecKit on the client brief before writing the proposal. Surfaces scope creep before it's quoted.

> **Spec as contract** — share the Stage 4 plan with clients for sign-off. It becomes the scope document.

> **Version your specs** — filename: `spec-[feature]-v[n]-[date].md`. Never overwrite.

---

## 🔧 TROUBLESHOOTING

| Issue | Cause | Fix |
|---|---|---|
| Skill not found | Wrong install path | Check `~/.claude/skills/digiminds-speckit/SKILL.md` exists |
| Stage 6 blocked | No approved spec in context | Run stages 1-5 first, get human approval |
| Generic spec output | Missing context | Provide tech stack, constraints, existing patterns in prompt |
| Tasks too coarse | Granularity setting | Set `task_granularity: atomic` in config |
| Acceptance criteria vague | Natural language input too loose | Add "testable" constraint to prompt |
| MAE bridge fails | Bridge script missing | Check `~/.claude/bin/speckit-mae-bridge` exists and is executable |
| Spec not persisting | Memory disabled | Set `save_to_memory: true` |
| Stage looping | Claude context window | Summarize previous stages and continue |
| Review gate skipped | `enforce_gate: false` | Set to `true` in production |
| Dependency graph missing | Visualization disabled | Enable `dependency_graph: true` |

---

## 📊 ARCHITECTURE

```
digiminds-speckit/
├── SKILL.md                      # Core skill — loaded by Claude Code
├── stages/
│   ├── 01-extract.md             # Stage 1: Requirements extraction
│   ├── 02-research.md            # Stage 2: Research and unknowns
│   ├── 03-analyze.md             # Stage 3: Edge cases and constraints
│   ├── 04-plan.md                # Stage 4: Architecture and approach
│   ├── 05-tasks.md               # Stage 5: Atomic task breakdown
│   └── 06-implement.md           # Stage 6: Implementation gate
├── templates/
│   ├── sdd-template.md           # SDD document template
│   ├── task-list.md              # Task breakdown template
│   └── review-checklist.md       # Human review checklist
├── bridge/
│   └── speckit-mae-bridge.py     # MAE pipeline integration
├── examples/
│   ├── lead-capture-spec.md      # Full example spec
│   └── n8n-automation-spec.md    # Automation example
└── README.md
```

**Integration architecture:**
```
Claude Code → /speckit.* commands → SKILL.md → Stage runner
     ↓
MAE pipeline → speckit-mae-bridge.py → subprocess
     ↓
Output: spec docs saved to ~/.claude/specs/[feature]-[date].md
     ↓
Paperclip OS → spec as project task → implementation tracking
```

---

## 🗺️ ROADMAP

| Feature | Status | ETA |
|---|---|---|
| 6-step SDD process | ✅ Done | — |
| Slash command interface | ✅ Done | — |
| Human review gate | ✅ Done | — |
| MAE pipeline bridge | ✅ Done | — |
| Acceptance criteria generation | ✅ Done | — |
| Notion export for specs | 🔄 In progress | Q3 2025 |
| Task dependency graph (visual) | 🔄 In progress | Q3 2025 |
| Linear/Jira task push | 📋 Planned | Q4 2025 |
| Multi-agent spec review | 📋 Planned | Q4 2025 |
| Spec diff on requirement change | 📋 Planned | Q4 2025 |
| Client portal for spec approval | 📋 Planned | Q1 2026 |
| Spec quality scoring | 📋 Planned | Q1 2026 |

---

## ☠️ STARTUPS / BUSINESSES

**The cost of skipping spec:**

| Scenario | No spec | With SpecKit |
|---|---|---|
| Feature scope creep | Constant rewrites | Locked spec = locked scope |
| Client disputes | "That's not what I asked for" | Signed-off spec is the contract |
| Onboarding new devs | Hours of tribal knowledge transfer | Read the spec |
| Bug root cause | Requirements misunderstood | Spec traces requirement to code |
| Agency profitability | Hours lost to rework | First-time-right ships on time |

**DigiMinds uses this for:**
- Every client automation workflow
- Every AI agent pipeline
- Every landing page build
- Every integration project

**The math:**
- Average rework cost (missed requirement): 4-8 hours
- SpecKit spec time: 20-30 minutes
- Break-even: first feature

---

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=hmzainjamil/digiminds-speckit&type=Date)](https://star-history.com/#hmzainjamil/digiminds-speckit&Date)

---

<div align="center">

Built by [HMZ](https://github.com/hmzainjamil) · DigiMinds agency OS · No code before spec

</div>
