# Example Manual Accessibility Audit Report — WCAG 2.2 Level AA

> **Illustrative example only.** The observations and evidence IDs below are synthetic and demonstrate report structure. This is not an executed audit and must not be used as evidence about the product. The example target is the documented ShopEasy accessibility exercise screen `/delivery-broken`.

## 1. Document control

| Field | Value |
|---|---|
| Product / service | ShopEasy training exercise |
| Version / build | Example build |
| Audit type | Designated issue-discovery exercise |
| Audit dates | 2026-07-17 |
| Auditor(s) | Example Auditor |
| Report date | 2026-07-17 |
| Report version | 0.1-example |

## 2. Audit basis

| Field | Value |
|---|---|
| Standard | Web Content Accessibility Guidelines (WCAG) 2.2 |
| Target level | AA, including A and AA |
| Normative source | https://www.w3.org/TR/WCAG22/ |
| Source verified | 2026-07-17 |
| Recommendation date | 12 December 2024 |
| Additional policy or law | None evaluated |

## 3. Executive summary

### Conclusion

**Not determined**

This example covers one synthetic page state and selected criteria only. It does not cover all 55 Level A/AA criteria, full responsive page variations, complete processes, or an agreed assistive-technology matrix. No WCAG conformance claim can be made.

### Result summary

| Metric | Count |
|---|---:|
| A/AA criteria | 55 |
| PASS | 0 |
| FAIL | 8 |
| N/A | 0 |
| NT | 47 |
| BLOCKED | 0 |
| Critical findings | 0 |
| High findings | 2 |
| Medium findings | 3 |
| Low findings | 0 |

### Highest-impact barriers

1. A11Y-001 — delivery method cannot be operated by keyboard.
2. A11Y-002 — postal-code input has no programmatically determinable label.
3. A11Y-003 — focus order does not match the meaningful visual task sequence.

## 4. Scope

### In scope

| Page / state / process | URL or identifier | Roles | Variants tested |
|---|---|---|---|
| Delivery form exercise | `/delivery-broken` | Guest | Synthetic desktop example state |

### Complete processes

| Process | Start | End | Included steps | Result |
|---|---|---|---|---|
| Checkout | Delivery | Order completion | Delivery state only | Incomplete |

### Out of scope and exclusions

- All other pages and states.
- Mobile, zoom, reflow, text spacing, media, timing, and authentication.
- Full screen-reader and browser compatibility matrix.

## 5. Test environments

| ID | Operating system | Browser / version | Viewport | Zoom / text settings | Input | Assistive technology / version |
|---|---|---|---|---|---|---|
| ENV-EXAMPLE | Synthetic | Synthetic browser | Desktop | 100% | Keyboard and pointer | Synthetic screen-reader observation |

## 6. Limitations

- This file demonstrates format; its observations are not real test evidence.
- Forty-seven criteria are `NT` because the example intentionally demonstrates selected findings only.
- The checkout process is incomplete; the conclusion must remain `Not determined`.

## 7. Selected criterion results

| Criterion | Level | Status | Evidence / rationale | Finding IDs |
|---|---|---|---|---|
| 1.1.1 Non-text Content | A | FAIL | EX-EV-004 | A11Y-005 |
| 1.3.1 Info and Relationships | A | FAIL | EX-EV-002 | A11Y-002 |
| 1.3.2 Meaningful Sequence | A | FAIL | EX-EV-003 | A11Y-003 |
| 1.4.3 Contrast (Minimum) | AA | FAIL | EX-EV-005 | A11Y-004 |
| 2.1.1 Keyboard | A | FAIL | EX-EV-001 | A11Y-001 |
| 2.4.3 Focus Order | A | FAIL | EX-EV-003 | A11Y-003 |
| 4.1.2 Name, Role, Value | A | FAIL | EX-EV-001, EX-EV-002 | A11Y-001, A11Y-002 |
| Remaining 47 A/AA criteria | A/AA | NT | Not included in this illustrative example | — |

> The eight failed criterion results above map to five root findings. One finding can affect multiple criteria, but every criterion remains independently traceable.

## 8. Findings

### A11Y-001 — Delivery method cannot be operated by keyboard

| Field | Detail |
|---|---|
| WCAG | 2.1.1 Keyboard — A; 4.1.2 Name, Role, Value — A |
| Severity | High |
| Severity rationale | Keyboard and screen-reader users cannot select a delivery method, blocking progression with no demonstrated workaround. |
| Affected users | Keyboard-only users; screen-reader users; users of switch or voice input that relies on semantic controls |
| Location | `/delivery-broken`, delivery-method selector |
| Environment | ENV-EXAMPLE |
| Evidence | EX-EV-001 |

**Preconditions**

- The delivery form is open.

**Steps to reproduce**

1. Place focus at the start of the page.
2. Press `Tab` repeatedly toward the delivery-method choices.
3. Attempt to select each choice using standard keyboard controls.

**Observed result**

In this synthetic example, the choices do not receive keyboard focus and do not expose radio-button role or selected state.

**Expected result**

Each delivery choice is keyboard operable and exposes an accessible name, radio role, and selected state to assistive technology.

**User impact**

Affected users cannot select a required delivery option and cannot continue the checkout task.

**Recommended outcome**

Provide a semantically exposed, keyboard-operable single-choice control with an announced selected state.

**Retest**

1. Reach every option by keyboard.
2. Change the selection using standard radio-control keys.
3. Verify name, role, and selected state with the agreed assistive technology.

### A11Y-002 — Postal-code input has no programmatic label

| Field | Detail |
|---|---|
| WCAG | 1.3.1 Info and Relationships — A; 4.1.2 Name, Role, Value — A |
| Severity | High |
| Severity rationale | Users who cannot perceive nearby visual text cannot identify the required input purpose. |
| Affected users | Screen-reader and voice-input users |
| Location | `/delivery-broken`, postal-code input |
| Environment | ENV-EXAMPLE |
| Evidence | EX-EV-002 |

**Steps to reproduce**

1. Navigate to the postal-code input with the agreed screen reader.
2. Read the announced control name and role.

**Observed result**

In this synthetic example, the input is announced without a name that identifies postal code.

**Expected result**

The visible label and input have a programmatically determinable relationship, and the input is announced with an accurate name.

**Recommended outcome**

Associate the visible postal-code label with the input so the relationship is available to assistive technology.

**Retest**

1. Navigate to the input with each agreed screen reader.
2. Verify that its accessible name includes the visible label text.

### A11Y-003 — Focus sequence conflicts with the meaningful visual sequence

| Field | Detail |
|---|---|
| WCAG | 1.3.2 Meaningful Sequence — A; 2.4.3 Focus Order — A |
| Severity | Medium |
| Severity rationale | Users encounter telephone and city fields in a different order from the displayed task, increasing confusion and input errors. |
| Affected users | Keyboard and screen-reader users; users with cognitive disabilities |
| Location | `/delivery-broken`, city and telephone fields |
| Environment | ENV-EXAMPLE |
| Evidence | EX-EV-003 |

**Steps to reproduce**

1. Identify the visual order of the city and telephone fields.
2. Navigate through both fields using `Tab`.
3. Compare visual, focus, and screen-reader reading sequences.

**Observed result**

In this synthetic example, keyboard and reading order place telephone before city while visual presentation places city before telephone.

**Expected result**

When sequence affects understanding or operation, programmatic reading and focus order preserve the meaningful task sequence.

**Recommended outcome**

Align the meaningful visual, reading, and focus sequences.

**Retest**

1. Compare visual order with sequential keyboard and screen-reader navigation.
2. Verify that all three sequences preserve the same meaning.

### A11Y-004 — Primary action text has insufficient contrast

| Field | Detail |
|---|---|
| WCAG | 1.4.3 Contrast (Minimum) — AA |
| Severity | Medium |
| Severity rationale | Low-vision users may be unable to identify the action needed to continue. |
| Affected users | Users with low vision or reduced contrast sensitivity |
| Location | `/delivery-broken`, primary action button |
| Environment | ENV-EXAMPLE |
| Evidence | EX-EV-005 — synthetic measurement 1.5:1 |

**Steps to reproduce**

1. Capture the rendered text and adjacent background colors in the default state.
2. Measure their contrast ratio with the agreed manual measurement tool.
3. Determine whether the text qualifies as large-scale text.

**Observed result**

The synthetic measured ratio is 1.5:1 for text that does not qualify for an exception.

**Expected result**

Normal text has a contrast ratio of at least 4.5:1 against its background, unless a normative exception applies.

**Recommended outcome**

Use foreground and background colors that meet the required ratio in every relevant state.

**Retest**

1. Measure all button states against their actual adjacent backgrounds.
2. Verify at least 4.5:1 for normal text or 3:1 for qualifying large-scale text.

### A11Y-005 — Informative delivery image has no equivalent text alternative

| Field | Detail |
|---|---|
| WCAG | 1.1.1 Non-text Content — A |
| Severity | Medium |
| Severity rationale | Users who cannot perceive the image miss information about free delivery. |
| Affected users | Blind users and users who disable images |
| Location | `/delivery-broken`, delivery information image |
| Environment | ENV-EXAMPLE |
| Evidence | EX-EV-004 |

**Steps to reproduce**

1. Locate the image communicating delivery information.
2. Navigate to or inspect it with the agreed screen reader.
3. Compare the available text alternative with the visual information.

**Observed result**

In this synthetic example, the image is ignored by assistive technology and equivalent free-delivery information is not otherwise available.

**Expected result**

Informative non-text content has a text alternative serving the equivalent purpose.

**Recommended outcome**

Provide an equivalent programmatically associated text alternative or the same information in adjacent text.

**Retest**

1. Verify that assistive technology presents equivalent information.
2. Confirm that decorative content remains ignorable.

## 9. Remediation priorities

| Priority | Finding IDs | Rationale / dependency |
|---|---|---|
| 1 | A11Y-001, A11Y-002 | Remove task blockers for keyboard and screen-reader users. |
| 2 | A11Y-003, A11Y-004, A11Y-005 | Reduce sequence, perception, and information barriers. |

## 10. Conformance requirements review

| Requirement | Result | Evidence / rationale |
|---|---|---|
| 1. Conformance level | Not determined | Forty-seven A/AA criteria are not tested. |
| 2. Full pages | Not determined | Responsive and other page variations are not tested. |
| 3. Complete processes | Not determined | Checkout is incomplete. |
| 4. Accessibility-supported ways of using technologies | Not determined | No agreed support matrix was executed. |
| 5. Non-interference | Not determined | Relevant criteria were not all tested. |

## 11. Final declaration

This illustrative partial review does not establish WCAG 2.2 Level AA conformance and does not assess legal compliance.
