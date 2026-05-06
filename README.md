# Karen's Claude Code Cheatsheet

> Personal reference for custom skills and installed plugins.
> Built on top of [cc.storyfox.cz](https://cc.storyfox.cz/) — this page covers only my additions.

---

## 🗣️ Caveman Mode

Compress Claude's output to save tokens. Auto-activates on session start.

| Command | Description |
|---------|-------------|
| `/caveman` | Activate caveman mode (default: full) |
| `/caveman lite` | No filler/hedging. Keeps articles and full sentences |
| `/caveman full` | Drop articles, fragments OK, short synonyms. Classic caveman |
| `/caveman ultra` | Abbreviate everything (DB/auth/req/res), arrows for causality (X→Y) |
| `/caveman wenyan-lite` | Semi-classical Chinese. Drop filler, keep grammar |
| `/caveman wenyan-full` | Full 文言文. 80-90% character reduction |
| `/caveman wenyan-ultra` | Extreme classical Chinese compression |
| `/caveman-help` | Show caveman command reference card |
| `/caveman-commit` | Write commit messages in ultra-compressed Conventional Commits format |
| `/caveman-review` | Compressed one-line-per-comment code review |
| `/caveman-compress <file>` | Compress CLAUDE.md / memory files to caveman format (saves original as `.original.md`) |
| `stop caveman` / `normal mode` | Deactivate caveman mode |

---

## 🛠️ Dev Workflow

| Command | Description |
|---------|-------------|
| `/grill-me <idea>` | Stress-test a plan — asks 5–10 targeted questions to expose weak spots |
| `/grill-me @FILE.md` | Grill an existing spec or design doc |
| `/git-branch-creator` | Create branch with naming convention `creator/category/task-name` |
| `/codex-review` | Analyze git changes and recommend the right Codex review command |
| `/coding-dispatch` | Break multi-step tasks into subagents and execute sequentially |
| `/skill-creator` | Guide for creating or updating skills |
| `/sos` | Stuck on setup — design a Claude Code workflow (hook/skill/MCP/CLAUDE.md) |

---

## 🔍 Code Review — Plugin: `sd0x-dev-flow`

> Requires Codex MCP connected. Set up via `rone` + `~/bin/codex-mcp.sh`.

| Command | Description |
|---------|-------------|
| `/sd0x-dev-flow:codex-review-fast` | Quick second-opinion via Codex MCP (diff only, no tests) |
| `/sd0x-dev-flow:codex-review` | Full review: lint:fix + build + Codex verdict |
| `/sd0x-dev-flow:codex-review-doc` | Document/spec review via Codex MCP |
| `/sd0x-dev-flow:codex-review-branch` | Full review of an entire feature branch |
| `/sd0x-dev-flow:codex-security` | OWASP Top 10 security review via Codex |
| `/sd0x-dev-flow:codex-test-review` | Review test coverage, suggest edge cases |
| `/sd0x-dev-flow:simplify` | Wrap-up refactor: remove duplication, preserve behavior |
| `/sd0x-dev-flow:best-practices` | Industry best-practices conformance audit |
| `/sd0x-dev-flow:pre-pr-audit` | 5-dimension confidence audit before creating a PR |
| `/sd0x-dev-flow:risk-assess` | Breaking-change detection + blast radius before committing |
| `/sd0x-dev-flow:seek-verdict` | Independent second-opinion for any finding |

---

## 🚀 Development — Plugin: `sd0x-dev-flow`

| Command | Description |
|---------|-------------|
| `/sd0x-dev-flow:feature-dev` | Feature implementation workflow (plan → code → test → review) |
| `/sd0x-dev-flow:bug-fix` | Bug fix workflow with hypothesis loop |
| `/sd0x-dev-flow:debug` | Hypothesis-driven debugging probe loop |
| `/sd0x-dev-flow:refactor` | Multi-target refactoring orchestrator |
| `/sd0x-dev-flow:precommit` | Pre-commit checks: lint:fix → build → test |
| `/sd0x-dev-flow:precommit-fast` | Quick pre-commit: lint:fix → test |
| `/sd0x-dev-flow:smart-commit` | Analyze changes, group by cohesion, generate commit messages |
| `/sd0x-dev-flow:codex-implement` | Implement features via Codex MCP |
| `/sd0x-dev-flow:codex-brainstorm` | Adversarial brainstorm: Claude + Codex debate |

---

## 📊 Analysis & Planning — Plugin: `sd0x-dev-flow`

| Command | Description |
|---------|-------------|
| `/sd0x-dev-flow:codex-architect` | Architecture consulting via Codex |
| `/sd0x-dev-flow:deep-research` | Multi-source research orchestration |
| `/sd0x-dev-flow:deep-analyze` | Deep-dive analysis of a proposal |
| `/sd0x-dev-flow:feasibility-study` | First-principles feasibility analysis |
| `/sd0x-dev-flow:req-analyze` | Requirements decomposition and stakeholder scan |
| `/sd0x-dev-flow:tech-spec` | Tech spec generation and review |
| `/sd0x-dev-flow:necessity-audit` | Audit for over-designed spec elements |

---

## 📝 Documentation — Plugin: `sd0x-dev-flow`

| Command | Description |
|---------|-------------|
| `/sd0x-dev-flow:tech-brief` | Convert implementation details into dev-sharing format |
| `/sd0x-dev-flow:project-brief` | PM/CTO-readable executive summary from tech spec |
| `/sd0x-dev-flow:update-docs` | Update docs to match current code state |
| `/sd0x-dev-flow:doc-refactor` | Simplify docs, visualize flows with diagrams |
| `/sd0x-dev-flow:de-ai-flavor` | Remove AI artifacts / AI-sounding language from docs |
| `/sd0x-dev-flow:recap-doc` | Post-development recap document generator |

---

## 🔀 PR & Git — Plugin: `sd0x-dev-flow`

| Command | Description |
|---------|-------------|
| `/sd0x-dev-flow:create-pr` | Create or update GitHub PR with `gh` CLI |
| `/sd0x-dev-flow:pr-review` | PR self-review: produce checklist, update rules |
| `/sd0x-dev-flow:pr-comment` | Post review comments to a GitHub PR |
| `/sd0x-dev-flow:load-pr-review` | Load PR review comments into session for analysis |
| `/sd0x-dev-flow:merge-prep` | Pre-merge analysis: compare source vs target branch |
| `/sd0x-dev-flow:push-ci` | Push to remote and monitor CI until done |
| `/sd0x-dev-flow:watch-ci` | Monitor GitHub Actions CI runs |
| `/sd0x-dev-flow:smart-rebase` | Partial rebase for squash-merge repos |

---

## 🤖 Codex Plugin (`openai/codex-plugin-cc`)

> Alternative codex review. Claude is a pure pass-through (`disable-model-invocation: true`).

| Command | Description |
|---------|-------------|
| `/codex:review` | Code review against local git state |
| `/codex:adversarial-review` | Challenges implementation approach and design choices |
| `/codex:setup` | Check Codex CLI readiness, toggle stop-time review gate |
| `/codex:rescue` | Delegate investigation or fix to Codex rescue subagent |
| `/codex:status` | Show active and recent Codex jobs + review-gate status |
| `/codex:result` | Show final output for a finished Codex job |
| `/codex:cancel` | Cancel an active background Codex job |

---

## 📅 Microsoft 365 & Work

| Command | Description |
|---------|-------------|
| `/morning-briefing` | Daily briefing: Calendar + Email + Teams → dashboard (auto-runs on 開工) |
| `/teams-channel-digest` | Read / send Teams messages; analyze channel discussions |
| `/outlook-email-digest` | Extract requirements from Outlook emails → Confluence |
| `/uxd-weekly-digest` | Cross-project UXD weekly digest from Teams + other sources |
| `/designer-submodule` | Git workflow for designers in submodules (zero git knowledge required) |

---

## ✍️ Content & Communication

| Command | Description |
|---------|-------------|
| `/social-media-refiner` | Polish Threads/IG posts in @flying_k.s voice |
| `/meeting-summarizer` | Summarize meeting recordings or notes |
| `/meeting-quality-gate` | Evaluate if a meeting is worth holding |

---

## 🎯 Personal

| Command | Description |
|---------|-------------|
| `/fortune-stick-interpreter <籤號>` | Interpret Taiwan traditional fortune sticks (觀音/關帝/呂祖 etc.) |
| `/pole-move-organizer` | Sort and format pole dance move code lists |
| `/cost-monitor` | holylot.app weekly cost report (Fly.io + OpenRouter + Cloudflare) |

---

## 🎨 Design & Prototyping

| Command | Description |
|---------|-------------|
| `/huashu-design` | 花叔Design: HTML high-fidelity prototypes, animations, slides, app mockups |

---

## 📚 Knowledge Management

| Command | Description |
|---------|-------------|
| `/knowledge-base ingest` | Add raw material to AI/LLM knowledge base (web / PDF / image / text) |
| `/knowledge-base ingest <youtube-url>` | Extract YouTube transcript → summarize → save to `raw/youtube/` (no API key needed; requires `pip3 install youtube-transcript-api`) |
| `/knowledge-base compile` | Compile raw docs into wiki articles |
| `/knowledge-base query` | Ask questions to knowledge base |
| `/knowledge-base lint` | Health check knowledge base |

---

## ⚙️ Claude Code Meta

| Command | Description |
|---------|-------------|
| `/basic-concept` | Interactive guide to Skill fundamentals |
| `/sync-health-check` | Check Jottacloud sync + git status for all vibe projects |
| `/claude-workflow-designer` | Design Claude Code workflows (hook / skill / MCP / CLAUDE.md) |
| `/sd0x-dev-flow:claude-health` | Claude Code config health check + plugin sync audit |
| `/sd0x-dev-flow:project-setup` | Project config initialization (auto-detect ecosystem) |
| `/sd0x-dev-flow:install-hooks` | Install plugin hooks into project `.claude/` persistently |
| `/sd0x-dev-flow:statusline-config` | Customize Claude Code statusline |

---

*Last updated: 2026-05-06 · [cc.storyfox.cz](https://cc.storyfox.cz/) for built-in commands reference*

<!-- update log -->
<!-- 2026-05-06: add knowledge-base YouTube ingest command -->
