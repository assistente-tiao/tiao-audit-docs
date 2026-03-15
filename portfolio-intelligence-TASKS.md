# Tasks — Portfolio Intelligence Agent

## Dependency Graph
T00 → T01 → T04 → T07 → T11 → T18 → T23
T02 → T05 → T08 → T12 → T19 → T24
T03 → T06 → T09 → T13 → T20 → T25
T04 → T10 → T14 → T21 → T26
T05 → T15 → T22 → T27
T07 → T16 → T28
T08 → T17 → T29
T18b → T23
T18,T18b,T19,T20,T21,T22,T23,T24,T25,T26,T27,T28,T29 → T30

## Tasks

### T00: Create project tracking card and definition of done
- **Branch:** `feat/t00-project-tracking-card`
- **Status:** [ ] Pending
- **Files:** `portfolio/EXECUTION-RULES.md`, `portfolio/KANBAN.md`
- **Depends on:** none
- **Complexity:** small
- **Acceptance criteria:** project objective, definition of done, and "backlog-first before execution" rule are explicit

### T01: Create project skeleton under workspace
- **Branch:** `feat/t01-portfolio-project-skeleton`
- **Status:** [ ] Pending
- **Files:** `portfolio/README.md`, `portfolio/PRD.md`, `portfolio/TASKS.md`, `portfolio/config/`, `portfolio/skills/`, `portfolio/scripts/`, `portfolio/reports/`, `portfolio/knowledge/`
- **Depends on:** none
- **Complexity:** small
- **Acceptance criteria:** project folder exists with agreed structure and PRD copied/referenced

### T02: Create Portfolio CIO SOUL.md
- **Branch:** `feat/t02-portfolio-soul`
- **Status:** [ ] Pending
- **Files:** `portfolio/SOUL.md`
- **Depends on:** none
- **Complexity:** small
- **Acceptance criteria:** identity, tone, philosophy GARP and operating rules are explicit and deterministic

### T03: Create Portfolio USER.md
- **Branch:** `feat/t03-portfolio-user`
- **Status:** [ ] Pending
- **Files:** `portfolio/USER.md`
- **Depends on:** none
- **Complexity:** small
- **Acceptance criteria:** investor profile, hurdle, sizing, broker context, tax notes and guardrails are documented

### T04: Create project-level CLAUDE.md derived dev rules
- **Branch:** `feat/t04-portfolio-claude-template`
- **Status:** [ ] Pending
- **Files:** `portfolio/CLAUDE.md`
- **Depends on:** T01
- **Complexity:** medium
- **Acceptance criteria:** fixed development rules, anti-patterns, playbooks and project placeholders exist for this project

### T05: Create SDD specification pack for this project
- **Branch:** `feat/t05-portfolio-sdd-pack`
- **Status:** [ ] Pending
- **Files:** `portfolio/SDD.md`, `portfolio/specs/architecture.md`, `portfolio/specs/modules/`
- **Depends on:** T02
- **Complexity:** medium
- **Acceptance criteria:** architecture, module boundaries and data flow are documented using SDD conventions

### T06: Create initial delivery roadmap and milestones
- **Branch:** `feat/t06-portfolio-roadmap`
- **Status:** [ ] Pending
- **Files:** `portfolio/ROADMAP.md`
- **Depends on:** T03
- **Complexity:** small
- **Acceptance criteria:** roadmap aligns PRD, V1 scope and execution phases without overengineering

### T07: Define Google Sheets source-of-truth schema
- **Branch:** `feat/t07-sheets-schema`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/google-sheets-schema.md`
- **Depends on:** T04
- **Complexity:** medium
- **Acceptance criteria:** tabs, columns, field ownership, formulas and manual-vs-agent responsibilities are explicit

### T08: Define market data contract and ticker normalization rules
- **Branch:** `feat/t08-market-data-contract`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/market-data-contract.md`
- **Depends on:** T05
- **Complexity:** medium
- **Acceptance criteria:** supported assets, price fields, FX handling, macro series, ticker suffix rules and fallback behavior are documented

### T09: Define analytics contract for V1
- **Branch:** `feat/t09-analytics-contract`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/analytics-contract.md`
- **Depends on:** T06
- **Complexity:** medium
- **Acceptance criteria:** V1 metrics, formulas, benchmark references and output locations are explicit in BRL

### T10: Define reporting contract for Discord outputs
- **Branch:** `feat/t10-reporting-contract`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/reporting-contract.md`
- **Depends on:** T04
- **Complexity:** medium
- **Acceptance criteria:** daily alert and sunday briefing structures are deterministic, concise and mapped to Discord constraints

### T11: Design portfolio-sheets skill spec
- **Branch:** `feat/t11-portfolio-sheets-skill-spec`
- **Status:** [ ] Pending
- **Files:** `portfolio/skills/portfolio-sheets/SKILL.md`, `portfolio/specs/modules/portfolio-sheets.md`
- **Depends on:** T07
- **Complexity:** medium
- **Acceptance criteria:** read/write operations, spreadsheet assumptions, batch update rules and error model are specified

### T12: Design market-data skill spec
- **Branch:** `feat/t12-market-data-skill-spec`
- **Status:** [ ] Pending
- **Files:** `portfolio/skills/market-data/SKILL.md`, `portfolio/specs/modules/market-data.md`
- **Depends on:** T08
- **Complexity:** medium
- **Acceptance criteria:** yfinance scope, macro coverage, retry/fallback policy and output JSON contract are specified

### T13: Design macro-monitor skill spec
- **Branch:** `feat/t13-macro-monitor-skill-spec`
- **Status:** [ ] Pending
- **Files:** `portfolio/skills/macro-monitor/SKILL.md`, `portfolio/specs/modules/macro-monitor.md`
- **Depends on:** T09
- **Complexity:** medium
- **Acceptance criteria:** BCB/yfinance/web-search split, collection cadence and update target fields are specified

### T14: Design analysis-engine skill spec
- **Branch:** `feat/t14-analysis-engine-skill-spec`
- **Status:** [ ] Pending
- **Files:** `portfolio/skills/analysis-engine/SKILL.md`, `portfolio/specs/modules/analysis-engine.md`
- **Depends on:** T10
- **Complexity:** medium
- **Acceptance criteria:** command surface, template usage, research limits and thesis-update rules are explicit

### T15: Design portfolio-analytics skill spec
- **Branch:** `feat/t15-portfolio-analytics-skill-spec`
- **Status:** [ ] Pending
- **Files:** `portfolio/skills/portfolio-analytics/SKILL.md`, `portfolio/specs/modules/portfolio-analytics.md`
- **Depends on:** T08
- **Complexity:** medium
- **Acceptance criteria:** beta, concentration, FX exposure, winners/losers and benchmark computations are specified for V1

### T16: Define cron and scheduling spec
- **Branch:** `feat/t16-cron-scheduling-spec`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/schedules.md`
- **Depends on:** T07
- **Complexity:** small
- **Acceptance criteria:** daily 23:00 BRT run and sunday briefing schedule are locked with timezone notes and DST behavior

### T17: Define observability and run-log spec
- **Branch:** `feat/t17-observability-spec`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/observability.md`
- **Depends on:** T08
- **Complexity:** small
- **Acceptance criteria:** run logs, failure reporting, operator visibility and audit trail are specified

### T18: Create Google Sheet bootstrap task spec
- **Branch:** `feat/t18-sheet-bootstrap-spec`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/bootstrap-sheet.md`
- **Depends on:** T11
- **Complexity:** medium
- **Acceptance criteria:** spreadsheet creation, tab bootstrap, permissions and initial formulas are specified end-to-end

### T18b: Validate external access readiness (GWS + yfinance + BCB)
- **Branch:** `feat/t18b-external-access-readiness`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/external-access-readiness.md`
- **Depends on:** none
- **Complexity:** small
- **Acceptance criteria:** Google Sheets write access, yfinance coverage, and BCB availability are explicitly validated before execution work starts

### T19: Create knowledge base migration plan
- **Branch:** `feat/t19-knowledge-migration-plan`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/knowledge-migration.md`
- **Depends on:** T12
- **Complexity:** medium
- **Acceptance criteria:** source files, destination layout, naming convention and validation checklist are defined

### T20: Define position ingest bootstrap flow
- **Branch:** `feat/t20-position-ingest-spec`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/position-bootstrap.md`
- **Depends on:** T13
- **Complexity:** medium
- **Acceptance criteria:** manual load of current positions, PM and analyst assignment workflow are explicit

### T21: Define analyst-persona derivation workflow
- **Branch:** `feat/t21-analyst-derivation-spec`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/analyst-personas.md`
- **Depends on:** T14
- **Complexity:** medium
- **Acceptance criteria:** method to derive final analyst set from real portfolio and how to add new analysts later is explicit

### T22: Define thesis status and kill-switch workflow
- **Branch:** `feat/t22-thesis-killswitch-spec`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/thesis-status.md`
- **Depends on:** T15
- **Complexity:** medium
- **Acceptance criteria:** manual ownership, alert rules, status semantics and review cadence are explicit

### T23: Define daily close update implementation task
- **Branch:** `feat/t23-daily-update-task`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/jobs/daily-close.md`
- **Depends on:** T18
- **Complexity:** medium
- **Acceptance criteria:** end-to-end daily job inputs, outputs, failure handling and alert conditions are specified

### T24: Define sunday research implementation task
- **Branch:** `feat/t24-sunday-briefing-task`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/jobs/sunday-briefing.md`
- **Depends on:** T19
- **Complexity:** medium
- **Acceptance criteria:** macro, sector, release, benchmark and appendix sections are fully scoped

### T25: Define Discord command set and routing
- **Branch:** `feat/t25-discord-commands-spec`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/discord-commands.md`
- **Depends on:** T20
- **Complexity:** medium
- **Acceptance criteria:** supported commands, inputs, outputs, allowed side effects and fallback behavior are defined

### T26: Define validation checklist for market and analytics outputs
- **Branch:** `feat/t26-data-validation-checklist`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/validation-market-analytics.md`
- **Depends on:** T21
- **Complexity:** small
- **Acceptance criteria:** smoke checks for prices, FX, analytics and benchmark coherence are explicit

### T27: Define validation checklist for research outputs
- **Branch:** `feat/t27-research-validation-checklist`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/validation-research.md`
- **Depends on:** T22
- **Complexity:** small
- **Acceptance criteria:** thesis consistency, source hygiene and implication-to-portfolio checks are explicit

### T28: Define test strategy and quality gates for V1
- **Branch:** `feat/t28-test-strategy`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/test-strategy.md`
- **Depends on:** T16
- **Complexity:** medium
- **Acceptance criteria:** fixture strategy, contract tests, smoke tests and merge gates are explicit

### T29: Define git/worktree execution strategy for agent team
- **Branch:** `feat/t29-worktree-strategy`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/worktree-strategy.md`
- **Depends on:** T17
- **Complexity:** medium
- **Acceptance criteria:** branch naming, file ownership, PR granularity and conflict protocol are explicit

### T30: Final backlog audit against PRD and references
- **Branch:** `feat/t30-backlog-audit`
- **Status:** [ ] Pending
- **Files:** `portfolio/specs/backlog-audit.md`, `portfolio/TASKS.md`
- **Depends on:** T23, T24, T25, T26, T27, T28, T29
- **Complexity:** medium
- **Acceptance criteria:** every PRD section is mapped to tasks, gaps are called out, and backlog is declared execution-ready
