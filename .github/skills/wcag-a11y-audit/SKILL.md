---
name: wcag-a11y-audit
description: 'Plan, perform, document, and review manual web accessibility audits against WCAG 2.2 Level AA. Use when asked for a WCAG audit, a11y review, accessibility assessment, AA compliance check, accessibility findings, conformance evaluation, or audit report.'
argument-hint: 'Mode and target, for example: plan https://example.com checkout flow'
user-invocable: true
disable-model-invocation: false
---

# WCAG 2.2 AA Manual Accessibility Audit

Produce evidence-based manual accessibility audits and reports. The target is the latest stable WCAG Recommendation verified in [official sources](./references/sources.md). Level AA includes every applicable Level A and Level AA success criterion.

## Non-negotiable rules

- Perform manual evaluation only. Do not create test automation or audit code.
- Use automated-tool output, if supplied by the user, only as a lead. Reproduce each issue manually before reporting it as a finding.
- Never infer a pass from requirements, source code, a screenshot, or the absence of an automated warning.
- Never invent pages, states, observations, assistive-technology output, measurements, or evidence.
- Ask for missing critical context. If evidence cannot be obtained, use `NT — Not tested`; do not guess.
- Treat severity as user impact and task impact, independent of WCAG conformance level.
- Do not claim Level AA conformance from a sample, partial review, design-only review, or review containing `FAIL`, `NT`, or `BLOCKED` criteria.
- Separate normative WCAG requirements from informative Understanding documents, Techniques, and Quick Reference guidance.
- Do not include Level AAA in the conformance decision unless the user explicitly requests it.

## Supported modes

Interpret the first argument as a mode when present:

- `plan` — define scope, environment, page/state sample, complete processes, and execution plan.
- `audit` — guide or perform the manual audit and record criterion-level evidence.
- `finding` — turn supplied observations into traceable findings without adding facts.
- `report` — create a report from supplied or observed evidence using the bundled template.
- `review` — quality-check an existing plan, finding set, or report.
- No mode — ask which outcome is required, then continue.

## Procedure

### 1. Refresh the audit basis

1. Read [official sources](./references/sources.md).
2. When network access is available, fetch the W3C WCAG overview and canonical WCAG specification before starting.
3. Confirm the latest stable Recommendation, publication date, errata, and whether a newer stable WCAG 2.x Recommendation exists.
4. Use a draft, editor's draft, or WCAG 3 only when explicitly requested, and label it non-normative or draft as applicable.
5. Record the exact standard title, version, canonical URL, and verification date in the report.

If current official sources cannot be fetched, disclose that limitation and use the pinned basis in [official sources](./references/sources.md); never describe it as freshly verified.

### 2. Establish scope before testing

Collect and confirm:

- target URL, build, or supplied artifact;
- audit objective: issue discovery, readiness review, or conformance evaluation;
- in-scope URLs, page states, dialogs, errors, authenticated areas, languages, and responsive variants;
- complete user processes from start to finish;
- out-of-scope content and third-party content;
- technologies relied upon;
- browser, operating system, viewport, zoom, input methods, and assistive technologies available;
- test accounts, roles, data, safety constraints, and destructive actions;
- required evidence format and report destination.

Do not choose an assistive-technology matrix or legal interpretation silently. Propose a matrix and obtain confirmation. If the user cannot provide a required environment or access, record the limitation.

### 3. Build the coverage plan

Use [AA audit instructions](./references/wcag-2.2-aa-audit.md).

1. Inventory representative templates, components, content types, states, and complete processes.
2. Map each in-scope item to relevant Level A and AA criteria.
3. Include every one of the 55 Level A/AA criteria in the coverage matrix.
4. For potentially inapplicable criteria, plan how applicability will be established; do not mark `N/A` in advance.
5. Identify high-risk areas: navigation, forms, authentication, errors, dynamic updates, dialogs, custom controls, media, time limits, drag interactions, responsive layouts, and third-party content.
6. Distinguish sampled issue discovery from a full conformance evaluation.

### 4. Execute manual checks

Use this order unless the scope requires another sequence:

1. Content and structure: titles, headings, landmarks, reading order, language, alternatives, tables, and instructions.
2. Keyboard: all functions, traps, focus order, visible focus, obscured focus, shortcuts, dialogs, menus, and custom controls.
3. Visual presentation: color reliance, text and non-text contrast, images of text, hover/focus content.
4. Magnification and adaptation: 200% text resize, 400%/320 CSS px reflow, orientation, and text-spacing overrides.
5. Forms and processes: labels, purpose, errors, suggestions, prevention, repeated entry, and authentication.
6. Pointer and motion: gestures, cancellation, label in name, motion alternatives, dragging alternatives, and target size.
7. Media and timing: alternatives, captions, audio description, audio control, moving content, limits, and flashing.
8. Assistive technology: accessible names, roles, states, values, reading order, announcements, and status messages.
9. Cross-page consistency: repeated navigation, identification, help, and multiple ways to locate pages.

For each observation, record the environment, page/state, preconditions, atomic steps, expected result, actual result, and evidence reference immediately.

### 5. Decide criterion status

Use only these statuses:

- `PASS` — sufficient direct manual evidence shows the criterion is satisfied throughout the evaluated scope.
- `FAIL` — reproducible evidence shows at least one failure in scope.
- `N/A` — the criterion has no applicable content or functionality in scope; include a rationale.
- `NT` — the criterion was not tested or evidence is insufficient; include the reason.
- `BLOCKED` — testing was attempted but access, environment, data, or a defect prevented completion.

A criterion with mixed results is `FAIL`. Do not average results across pages. Preserve page-level evidence below the criterion summary.

### 6. Write findings

Each finding must contain:

- unique ID and concise title;
- WCAG criterion number, name, and level;
- severity and rationale;
- affected users and user/task impact;
- exact page, state, component, and environment;
- preconditions and atomic reproduction steps;
- observed and expected results;
- evidence reference;
- recommended outcome, not speculative implementation code;
- retest method.

Severity guide:

- `Critical` — blocks an essential process with no reasonable workaround, or creates immediate serious harm.
- `High` — prevents a major task or excludes a user group; workaround is absent or impractical.
- `Medium` — causes a substantial barrier, delay, error risk, or repeated burden; a workaround exists.
- `Low` — limited or localized impact with a straightforward workaround.

### 7. Produce the report

Copy [audit report template](./assets/audit-report-template.md) to the agreed destination and fill it only with verified data. Use [example report](./assets/audit-report-example.md) for formatting, not as evidence.

Conformance conclusion rules:

- `Conforms` only when all five WCAG conformance requirements are addressed and all applicable A/AA criteria pass for all full pages and complete processes in the claimed scope.
- `Does not conform` when at least one applicable A/AA criterion fails in the evaluated claim scope.
- `Not determined` for samples, partial audits, design reviews, blocked/untested criteria, missing complete processes, or insufficient accessibility-support evidence.

### 8. Run quality gates

Before finalizing, confirm:

- [ ] Current official audit basis is cited with verification date.
- [ ] Scope, exclusions, environments, pages/states, and complete processes are explicit.
- [ ] All 55 Level A/AA criteria have a status and evidence or rationale.
- [ ] Every `FAIL` maps to one or more reproducible findings.
- [ ] Every finding maps back to criterion-level evidence.
- [ ] `N/A`, `NT`, and `BLOCKED` entries include reasons.
- [ ] No unobserved fact, fabricated assistive-technology announcement, or guessed measurement appears.
- [ ] Severity is justified by impact, not by A/AA level.
- [ ] Limitations and sampling constraints are prominent.
- [ ] The conclusion follows the conformance rules above.

## Prompt recipes

For ready-to-use invocation examples and structured input prompts, read [audit prompts](./references/audit-prompts.md).
