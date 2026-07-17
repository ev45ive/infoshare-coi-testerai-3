# WCAG 2.2 Level A and AA manual audit instructions

This checklist covers the **55** Level A and Level AA success criteria in WCAG 2.2. It paraphrases testing intent; the [WCAG 2.2 Recommendation](https://www.w3.org/TR/WCAG22/) remains authoritative.

## Status and evidence rules

For every criterion, record `PASS`, `FAIL`, `N/A`, `NT`, or `BLOCKED`, plus page/state, environment, steps, observation, and evidence reference.

- Test all relevant states, including default, hover, focus, active, disabled, error, loading, success, expanded, collapsed, authenticated, and responsive states.
- `N/A` requires evidence that no relevant content or functionality exists in the confirmed scope.
- A single reproducible failure makes the criterion `FAIL` for that scope.
- If a required environment, state, measurement, or assistive technology is unavailable, use `NT` or `BLOCKED`.
- Do not treat an informative technique as the only valid implementation. Evaluate the normative success criterion.

## 1 — Perceivable

| Criterion | Level | Manual audit instruction |
|---|---|---|
| [1.1.1 Non-text Content](https://www.w3.org/TR/WCAG22/#non-text-content) | A | Inventory informative, functional, sensory, decorative, CAPTCHA, and complex non-text content. With images unavailable and with agreed AT, verify an equivalent purpose is available; decorative items are ignored; controls have accurate names. |
| [1.2.1 Audio-only and Video-only (Prerecorded)](https://www.w3.org/TR/WCAG22/#audio-only-and-video-only-prerecorded) | A | For prerecorded audio-only and video-only content, verify the required equivalent alternative or audio track, unless it is clearly labeled as a media alternative for text. Check completeness and sequence. |
| [1.2.2 Captions (Prerecorded)](https://www.w3.org/TR/WCAG22/#captions-prerecorded) | A | Play each prerecorded synchronized-media item. Verify captions include dialogue, speakers, and meaningful non-speech audio, and are synchronized, accurate, and available unless the media is a labeled text alternative. |
| [1.2.3 Audio Description or Media Alternative (Prerecorded)](https://www.w3.org/TR/WCAG22/#audio-description-or-media-alternative-prerecorded) | A | For prerecorded synchronized video, verify an audio description or complete media alternative conveys visual information needed to understand the content, subject to the normative exception. |
| [1.2.4 Captions (Live)](https://www.w3.org/TR/WCAG22/#captions-live) | AA | Observe representative live synchronized media. Verify live captions are available and convey spoken and meaningful non-speech audio sufficiently and in time to follow the content. |
| [1.2.5 Audio Description (Prerecorded)](https://www.w3.org/TR/WCAG22/#audio-description-prerecorded) | AA | Play prerecorded synchronized video with audio description enabled. Verify important visual details not present in the main audio are described without losing essential information. |
| [1.3.1 Info and Relationships](https://www.w3.org/TR/WCAG22/#info-and-relationships) | A | Compare visible structure and relationships with AT presentation: headings, landmarks, lists, tables, groups, labels, instructions, required states, and emphasis. Verify equivalent information is programmatically determinable or in text. |
| [1.3.2 Meaningful Sequence](https://www.w3.org/TR/WCAG22/#meaningful-sequence) | A | Compare visual sequence with screen-reader reading order and linearized navigation. Verify any order affecting meaning is programmatically available in the correct sequence. Test responsive variants. |
| [1.3.3 Sensory Characteristics](https://www.w3.org/TR/WCAG22/#sensory-characteristics) | A | Review instructions and feedback. Verify understanding or operation does not rely only on shape, color, size, visual location, orientation, or sound. |
| [1.3.4 Orientation](https://www.w3.org/TR/WCAG22/#orientation) | AA | Use portrait and landscape orientations on supported devices or equivalent orientation changes. Verify content and operation are not restricted to one orientation unless essential. Record essentiality evidence. |
| [1.3.5 Identify Input Purpose](https://www.w3.org/TR/WCAG22/#identify-input-purpose) | AA | For fields collecting user information whose purpose appears in WCAG's input-purpose list, verify supported user agents can programmatically identify the purpose, including practical autofill/personalization behavior where available. |
| [1.4.1 Use of Color](https://www.w3.org/TR/WCAG22/#use-of-color) | A | Inspect instructions, links, errors, charts, required fields, selections, and states with color perception reduced or color removed. Verify color is not the only visual means of conveying information or action. |
| [1.4.2 Audio Control](https://www.w3.org/TR/WCAG22/#audio-control) | A | Load pages from a fresh state. If audio starts automatically for more than three seconds, verify a pause/stop control or independent volume control is available and keyboard operable. |
| [1.4.3 Contrast (Minimum)](https://www.w3.org/TR/WCAG22/#contrast-minimum) | AA | Measure rendered text and images of text against actual backgrounds in all states. Verify at least 4.5:1 for normal text and 3:1 for qualifying large-scale text, applying only normative exceptions. Record colors, ratio, state, and text size/weight. |
| [1.4.4 Resize Text](https://www.w3.org/TR/WCAG22/#resize-text) | AA | Resize text to 200% without assistive technology. Verify no content or functionality is lost, clipped, overlapped, or made unreachable; captions and images of text follow criterion scope. |
| [1.4.5 Images of Text](https://www.w3.org/TR/WCAG22/#images-of-text) | AA | Inventory images containing text. Verify real text is used when the presentation can be achieved with the technology, except for customizable or essential presentation such as qualifying logos. |
| [1.4.10 Reflow](https://www.w3.org/TR/WCAG22/#reflow) | AA | Test vertical content at 320 CSS px width and horizontal writing content at the equivalent reflow condition, commonly 400% zoom from 1280 CSS px. Verify no loss and no two-dimensional scrolling except essential two-dimensional regions. |
| [1.4.11 Non-text Contrast](https://www.w3.org/TR/WCAG22/#non-text-contrast) | AA | Measure visual information needed to identify controls, states, focus indicators where applicable, and meaningful graphics against adjacent colors. Verify at least 3:1 unless a normative exception applies. |
| [1.4.12 Text Spacing](https://www.w3.org/TR/WCAG22/#text-spacing) | AA | Apply line height 1.5 times font size, paragraph spacing 2 times, letter spacing 0.12 times, and word spacing 0.16 times without changing other styles. Verify no content or functionality is lost. Use only properties applicable to the language/script. |
| [1.4.13 Content on Hover or Focus](https://www.w3.org/TR/WCAG22/#content-on-hover-or-focus) | AA | Trigger author-controlled additional content by pointer hover and keyboard focus. Verify it is dismissible without moving focus/hover when required, hoverable when pointer-triggered, and persistent until the allowed dismissal conditions occur. |

## 2 — Operable

| Criterion | Level | Manual audit instruction |
|---|---|---|
| [2.1.1 Keyboard](https://www.w3.org/TR/WCAG22/#keyboard) | A | Complete every function using a keyboard interface only, without pointer emulation. Verify standard and custom controls, drag alternatives, menus, dialogs, uploads, editors, maps, and exceptions based on path-dependent underlying functions. |
| [2.1.2 No Keyboard Trap](https://www.w3.org/TR/WCAG22/#no-keyboard-trap) | A | Move focus into every component, modal, embedded frame, and editor, then leave using only the keyboard. If nonstandard exit keys are needed, verify instructions are available before or when entering. |
| [2.1.4 Character Key Shortcuts](https://www.w3.org/TR/WCAG22/#character-key-shortcuts) | A | Identify shortcuts using only printable characters. Verify each can be disabled, remapped with a non-printable modifier, or is active only while its component has focus. Test with speech input risk in mind. |
| [2.2.1 Timing Adjustable](https://www.w3.org/TR/WCAG22/#timing-adjustable) | A | Identify session, task, reading, and response time limits. Before expiry, verify users can turn off, adjust, or extend limits as required, or document the applicable normative exception. |
| [2.2.2 Pause, Stop, Hide](https://www.w3.org/TR/WCAG22/#pause-stop-hide) | A | Identify moving, blinking, scrolling, and auto-updating content. For content in scope of the criterion, verify users can pause, stop, hide, or control update frequency unless essential. |
| [2.3.1 Three Flashes or Below Threshold](https://www.w3.org/TR/WCAG22/#three-flashes-or-below-threshold) | A | Identify flashing without prolonged exposure. Verify no content flashes more than three times in one second unless it is below the general and red-flash thresholds. Use safe frame-by-frame evidence or supplied analysis where needed; if the threshold cannot be safely verified, mark `NT`. |
| [2.4.1 Bypass Blocks](https://www.w3.org/TR/WCAG22/#bypass-blocks) | A | On pages with repeated blocks, verify a keyboard- and AT-usable mechanism bypasses them, such as a working skip link, appropriate regions, or another conforming method. Confirm destination focus/reading position. |
| [2.4.2 Page Titled](https://www.w3.org/TR/WCAG22/#page-titled) | A | Check the programmatic title for every page and distinct application view. Verify it identifies topic or purpose and differentiates similar pages. |
| [2.4.3 Focus Order](https://www.w3.org/TR/WCAG22/#focus-order) | A | Navigate sequentially through every state. Verify focus order preserves meaning and operation, including dialogs, injected content, responsive layouts, and focus return after closing overlays. |
| [2.4.4 Link Purpose (In Context)](https://www.w3.org/TR/WCAG22/#link-purpose-in-context) | A | Review links with surrounding programmatically determined context and through an AT links list. Verify each purpose is determinable except when ambiguous to users generally. |
| [2.4.5 Multiple Ways](https://www.w3.org/TR/WCAG22/#multiple-ways) | AA | For each page within a set, verify at least two ways to locate it, such as navigation, search, site map, table of contents, or related links, except pages that are process results or steps. |
| [2.4.6 Headings and Labels](https://www.w3.org/TR/WCAG22/#headings-and-labels) | AA | Review visible headings and labels in every state. Verify they accurately describe topic or purpose; do not require a heading or label where none is present under the criterion. |
| [2.4.7 Focus Visible](https://www.w3.org/TR/WCAG22/#focus-visible) | AA | Navigate all keyboard-operable controls in each state and background. Verify a visible focus indicator is present whenever keyboard focus is relevant. |
| [2.4.11 Focus Not Obscured (Minimum)](https://www.w3.org/TR/WCAG22/#focus-not-obscured-minimum) | AA | Move focus through pages with sticky headers/footers, cookie banners, dialogs, and overlays at supported zooms. Verify the focused component is not entirely hidden by author-created content. Apply notes and exceptions carefully. |
| [2.5.1 Pointer Gestures](https://www.w3.org/TR/WCAG22/#pointer-gestures) | A | Identify multipoint and path-based gestures interpreted by the content. Verify equivalent operation through a single pointer without a path-based gesture unless the gesture is essential. |
| [2.5.2 Pointer Cancellation](https://www.w3.org/TR/WCAG22/#pointer-cancellation) | A | For single-pointer actions, press down, move away, and release; test cancellation and undo. Verify activation normally occurs on up-event or another allowed condition applies. |
| [2.5.3 Label in Name](https://www.w3.org/TR/WCAG22/#label-in-name) | A | For controls with visible text or text images, compare the visible label with the accessible name using agreed AT or accessibility inspection. Verify the name contains the visible text, preferably in the same order. |
| [2.5.4 Motion Actuation](https://www.w3.org/TR/WCAG22/#motion-actuation) | A | Identify functions triggered by device or user motion. Verify a user-interface alternative exists and motion response can be disabled, unless an accessibility-supported or essential exception applies. |
| [2.5.7 Dragging Movements](https://www.w3.org/TR/WCAG22/#dragging-movements) | AA | Identify all content-authored drag operations. Verify the same result can be achieved with a single pointer without dragging unless dragging is essential or controlled by an unmodified user agent. |
| [2.5.8 Target Size (Minimum)](https://www.w3.org/TR/WCAG22/#target-size-minimum) | AA | Measure pointer target bounding boxes and spacing in relevant responsive states. Verify at least 24 by 24 CSS px or that one of the spacing, equivalent, inline, user-agent, or essential exceptions applies. |

## 3 — Understandable

| Criterion | Level | Manual audit instruction |
|---|---|---|
| [3.1.1 Language of Page](https://www.w3.org/TR/WCAG22/#language-of-page) | A | With agreed AT, verify the default human language of each page/view is programmatically determinable and produces appropriate pronunciation. |
| [3.1.2 Language of Parts](https://www.w3.org/TR/WCAG22/#language-of-parts) | AA | Identify passages and phrases in another language. Verify language changes are programmatically identified except for proper names, technical terms, indeterminate words, and assimilated vernacular. |
| [3.2.1 On Focus](https://www.w3.org/TR/WCAG22/#on-focus) | A | Focus every component without activating it. Verify focus alone does not initiate an unexpected change of context. |
| [3.2.2 On Input](https://www.w3.org/TR/WCAG22/#on-input) | A | Change values in form controls without explicit submission. Verify input changes do not automatically cause a context change unless users were advised beforehand. |
| [3.2.3 Consistent Navigation](https://www.w3.org/TR/WCAG22/#consistent-navigation) | AA | Compare repeated navigation across pages in the same set and page variation. Verify relative order remains consistent unless changed by the user. |
| [3.2.4 Consistent Identification](https://www.w3.org/TR/WCAG22/#consistent-identification) | AA | Compare components with the same functionality across the page set. Verify they are identified consistently in visible labels and programmatic names as applicable. |
| [3.2.6 Consistent Help](https://www.w3.org/TR/WCAG22/#consistent-help) | A | If human contact, human contact mechanisms, self-help, or automated contact mechanisms repeat across a page set, verify they occur in the same relative order unless users initiate a change. |
| [3.3.1 Error Identification](https://www.w3.org/TR/WCAG22/#error-identification) | A | Trigger each validation error. Verify the erroneous item is identified and the error is described in text; test visual and AT presentation without relying only on color. |
| [3.3.2 Labels or Instructions](https://www.w3.org/TR/WCAG22/#labels-or-instructions) | A | For every input, verify labels or instructions are available when needed, including format, units, required data, constraints, and grouped-control context. |
| [3.3.3 Error Suggestion](https://www.w3.org/TR/WCAG22/#error-suggestion) | AA | Trigger known input errors. When correction suggestions are known, verify useful text suggestions are provided unless doing so would jeopardize security or purpose. |
| [3.3.4 Error Prevention (Legal, Financial, Data)](https://www.w3.org/TR/WCAG22/#error-prevention-legal-financial-data) | AA | For legal commitments, financial transactions, deletion/modification of user-controlled stored data, and test-response submissions, verify submissions are reversible, checked with correction opportunity, or reviewable/confirmable before finalization. |
| [3.3.7 Redundant Entry](https://www.w3.org/TR/WCAG22/#redundant-entry) | A | Complete multi-step processes and note information requested again. Verify previously entered/provided information is auto-populated or selectable unless re-entry is essential, security-required, or no longer valid. |
| [3.3.8 Accessible Authentication (Minimum)](https://www.w3.org/TR/WCAG22/#accessible-authentication-minimum) | AA | Test every authentication step, including MFA and recovery. Verify cognitive-function tests are not required unless an allowed alternative, assistance mechanism, object recognition, or personal-content exception applies. Confirm password managers and paste are not blocked where they provide assistance. |

## 4 — Robust

| Criterion | Level | Manual audit instruction |
|---|---|---|
| [4.1.2 Name, Role, Value](https://www.w3.org/TR/WCAG22/#name-role-value) | A | With agreed AT/accessibility inspection, verify every control exposes an accurate name and role; user-settable states, properties, and values are available and operable; changes are conveyed. Cover custom controls and dynamic states. |
| [4.1.3 Status Messages](https://www.w3.org/TR/WCAG22/#status-messages) | AA | Trigger success, result count, loading/progress, cart, and error status messages that do not change context. Verify AT can announce or query them through role/properties without moving focus. |

## Conformance checks beyond individual criteria

A Level AA conclusion also requires all WCAG 2.2 conformance requirements:

1. Every applicable Level A and AA criterion is satisfied.
2. Conformance covers full pages, including responsive variations automatically presented.
3. Every page in each complete process conforms.
4. Only accessibility-supported uses of technologies are relied upon.
5. Non-accessibility-supported or nonconforming technology does not interfere; specifically verify non-interference for 1.4.2, 2.1.2, 2.2.2, and 2.3.1.

If any requirement is not established, report `Not determined` rather than `Conforms`.
