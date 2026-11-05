# skills.md

Notes on the skills I run in my local agents (OpenCode and Hermes).

## [UI UX Pro Max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill)

Design intelligence for UI/UX work. It picks a style, color palette, typography,
layout pattern and stack-specific rules for whatever you're building, and warns
about anti-patterns before you ship.

- 79 UI styles, 192 color palettes, 74 font pairings, 25 chart types
- 22 tech stacks (React, Next.js, Vue, SwiftUI, Flutter, Tailwind, …)
- Industry reasoning rules (fintech, healthcare, saas, e-commerce, …)
- Needs Python 3 for its search script

Install:

```bash
npm install -g ui-ux-pro-max-cli
uipro init --ai opencode        # or: uipro init --ai universal --global
```

Use it just by asking for UI work, e.g. "build a landing page for my SaaS product".

## [Impeccable](https://github.com/pbakaus/impeccable) ([impeccable.style](https://impeccable.style))

Design vocabulary for coding agents. Instead of "make it pop" you name a move —
`polish`, `bolder`, `quieter`, `typeset`, `audit` — and it applies a playbook to
one target. Best on interfaces that already exist.

- 24 commands: steer, review, finish, live iteration, plan
- `critique` scores UX and ranks fixes; `audit` ranks accessibility/perf issues P0–P3
- `live` mode picks elements in the browser and hot-swaps variants
- Detector with 62 deterministic rules for "AI slop" (no LLM, no API key)
- Writes `PRODUCT.md` / `DESIGN.md` so later changes stay on-brand

Install:

```bash
npx impeccable install
```

Reload the agent, then run `/impeccable init` once per project.

## [Ponytail](https://github.com/DietrichGebert/ponytail)

A "lazy senior dev" mode. It pushes the agent to reuse what already exists
instead of writing new code, so diffs stay small: less code, fewer tokens,
faster. It never cuts validation, security, error handling or accessibility.

- Always-on rules plus levels: `lite`, `full`, `ultra`, `off`
- Commands: `/ponytail-review`, `/ponytail-audit`, `/ponytail-debt`, `/ponytail-gain`, `/ponytail-help`
- Flags deliberate shortcuts with `shortcut:` comments so they don't get forgotten

Install for OpenCode:

```bash
opencode plugin add @dietrichgebert/ponytail
```

Install for Hermes:

```bash
hermes plugins install DietrichGebert/ponytail --enable
```

Fallback for any agent: copy the repo's `AGENTS.md` into the project, or add
`skills/ponytail/SKILL.md` as a skill.

## Idea & asset sources

### [21st.dev](https://21st.dev)

Community registry of UI built by design engineers — not a skill, a place to grab
starting points instead of letting the model invent the average hero section.

- 12,000+ React + Tailwind components, full templates, shadcn themes, shaders
- Code is copied into your repo via the shadcn CLI, so you own and can edit it
- "Copy prompt" hands a component to any agent; MCP/CLI also available
- Free to browse, 2 free component copies per day

Use it when a design feels generic: pick a real reference, then let the skills
above adapt it to your tokens.

## Prompt ideas

### Directing style

```
Aesthetic: [family] - [5-8 vocabulary terms]
Reference: [screenshot] - match feel, not content
Intent: [what this should feel like and why]
Guardrails: always [constants]. Never [bans].
```

Name the direction before the task, then let the agent build against it. The
reference sets tone only; guardrails keep tokens, accessibility and brand
constants from drifting.

## Notes

- Licenses: UI UX Pro Max and Ponytail are MIT; Impeccable is Apache 2.0.
- UI UX Pro Max has a premium tier (brand identity, logos, slides, icons); the
  open-source version covers the UI/UX part.
