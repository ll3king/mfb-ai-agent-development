# AGENTS.md

## Project

This file defines child-repo-specific execution rules for `C:\Users\61413\AI\mfb-ai-agent-development`.

Use this file as the project-level override layer for landing page, frontend, and design-governance work inside this child repo.

## Design Skill Routing

This project can use the globally installed Codex design skills when the task involves UI, frontend polish, landing pages, product screens, brand pages, or visual QA.

Use:
- `impeccable` for audit, polish, UX critique, responsive behavior, accessibility, typography, spacing, and final design QA.
- `design-taste-frontend` or `gpt-taste` for new landing-page direction, anti-slop frontend design, stronger visual concepts, and high-variance design exploration.
- `redesign-existing-projects` when improving an existing page without rebuilding the whole product.
- `brandkit` when brand direction, color, typography, or visual identity needs clarification.
- `image-to-code` only when a visual reference or screenshot should guide implementation.
- `imagegen-frontend-web` / `imagegen-frontend-mobile` only for visual concept generation, not production truth.

Default flow:
1. If the page already exists, audit first with `impeccable`.
2. If the page is new or visually weak, explore direction with `design-taste-frontend` / `gpt-taste`.
3. If implementation follows, preserve project architecture and existing components.
4. Before shipping, run `impeccable` as final QA.

Constraints:
- Do not let design skills override business goals, source-of-truth content, project tone, or user-approved scope.
- Do not redesign stable areas unless the task explicitly asks for redesign.
- For content-only updates, do not trigger design skills.

## Delegation preference

For concrete execution subtasks, prefer worker-style delegation over expanding the main controller context.

Default delegation model preference:
- prioritize `gpt-5.3-codex-spark` for bounded execution, extraction, file-level drafting, and mechanical design-support tasks
- keep the primary controller focused on strategy, synthesis, business judgment, design judgment, and final review

Delegation rules:
- the controller defines the exact objective, file scope, non-goals, and expected output before handing off work
- delegated tasks should be narrow, concrete, and evidence-driven
- delegated agents should not redefine business goals, page strategy, or project tone
- use stronger models only when the delegated task genuinely requires higher reasoning rather than simple bounded execution

## Repo Sync Boundary

This child repo is the only repository that may be changed, committed, or pushed when the task concerns `mfb-ai-agent-development`.

Hard rules:
- never commit or push from the parent repo `C:\Users\61413\AI\Money First Business` for child-repo landing page or design work
- before any commit or push, verify the working repo is exactly `C:\Users\61413\AI\mfb-ai-agent-development`
- before any push, verify the Git remote is exactly `https://github.com/ll3king/mfb-ai-agent-development.git`
- do not guess the remote, branch, or target repository from memory
- if the requested branch name differs from the current tracked branch, verify the actual branch state first, then push only within this child repo
- if there is any mismatch between local repo, remote URL, or requested branch, stop and resolve that mismatch before pushing
