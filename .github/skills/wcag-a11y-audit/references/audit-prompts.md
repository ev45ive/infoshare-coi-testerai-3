# WCAG 2.2 AA audit prompt recipes

Replace bracketed placeholders. Do not remove requests for evidence or limitations.

## 1. Scope and plan

> `/wcag-a11y-audit plan` Create a manual WCAG 2.2 Level AA audit plan for `[target]`. Objective: `[issue discovery/readiness/conformance evaluation]`. In scope: `[URLs, states, roles, languages, processes]`. Out of scope: `[items]`. Available environments and assistive technologies: `[matrix]`. Ask for every missing fact that would affect scope or the conformance conclusion. Include all 55 Level A/AA criteria, complete processes, evidence requirements, and explicit limitations. Do not create automation or code.

## 2. Guided page audit

> `/wcag-a11y-audit audit` Guide me through a manual WCAG 2.2 AA audit of `[URL/page/state]` in `[browser, OS, viewport, zoom, input, AT]`. Test one coherent area at a time. For every check, state the exact manual action and evidence to capture. Record only observations I provide or you directly verify. Use PASS, FAIL, N/A, NT, or BLOCKED and never infer a pass.

## 3. Complete-process audit

> `/wcag-a11y-audit audit` Audit the complete process `[start → intermediate steps → outcome]` against WCAG 2.2 Level AA. Roles and test data: `[details]`. Include all pages, dialogs, errors, confirmations, time limits, authentication, and responsive states in the process. Track focus and announcements across transitions. Stop and ask if a required state or environment is unavailable. Do not make a conformance claim from an incomplete process.

## 4. Turn observations into findings

> `/wcag-a11y-audit finding` Convert the observations below into traceable WCAG 2.2 AA findings. Preserve facts exactly; do not add behavior, measurements, user impact, or assistive-technology output that is not supported. For each finding include criterion, level, impact-based severity with rationale, affected users, location/state/environment, preconditions, atomic steps, actual result, expected result, evidence, remediation outcome, and retest method. Observations: `[paste notes]`.

## 5. Generate a report

> `/wcag-a11y-audit report` Create a manual WCAG 2.2 Level AA audit report from `[evidence source or notes]` using the bundled report template. Scope: `[scope]`. Audit matrix: `[matrix]`. Include criterion status for all 55 A/AA criteria, findings, limitations, and a justified conclusion of Conforms, Does not conform, or Not determined. Leave unknown fields as `TBD` or `NT`; do not invent values.

## 6. Review an audit report

> `/wcag-a11y-audit review` Review `[report path or pasted report]` for evidence quality, WCAG 2.2 accuracy, complete A/AA coverage, traceability, reproducibility, impact-based severity, sampling limitations, and valid conformance wording. List blocking issues first. Do not rewrite factual observations unless evidence supports the change.

## 7. Retest findings

> `/wcag-a11y-audit audit` Prepare and guide a manual retest of findings `[IDs]` in build `[build]` using the original environments and evidence. Verify the reported barrier, adjacent states, regressions, and criterion-level status. Do not close a finding merely because implementation changed; require observed expected behavior.

## 8. Design-only accessibility review

> `/wcag-a11y-audit audit` Review the supplied design or screenshots for observable WCAG 2.2 AA risks only. Clearly separate visible evidence from behavior that cannot be tested, such as keyboard operation, programmatic semantics, reading order, announcements, and accessible authentication. Mark untestable criteria `NT` and conclude `Not determined`; do not call this a conformance audit.
