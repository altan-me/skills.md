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

## Notes

- Both are MIT licensed and open source.
- UI UX Pro Max has a premium tier (brand identity, logos, slides, icons); the
  open-source version covers the UI/UX part.
