---
name: ui-ux-design-principle
description: UI/UX design principles by Utomo Abimail (hierarchy, progressive disclosure, consistency, contrast, accessibility, proximity, alignment, verification). Use when building, designing, reviewing, or polishing any user interface, page, screen, or component.
---

# ui-ux-design-principle

by Utomo Abimail

Guidelines for building user interfaces. Merge with project-specific instructions as needed.
Based on Figma's "Seven essential UI design principles."

**Core idea:** Good UI goes unnoticed. Help users reach the content and features they need to finish their task. Don't hand them a map to memorize. Put up signs that point the way, one click, scroll, or interaction at a time.

**Tradeoff:** These rules favor clarity and predictability over novelty. When a rule conflicts with an explicit project design system, the design system wins.

## 0. Before Building

**Map the flow first, then place the elements.**

- Write down the user's goal and the steps to reach it before writing markup.
- Order elements on screen in the same sequence the user needs them.
- Check for an existing design system, tokens, or component library and use it. Don't invent new ones.
- If the screen's primary action or audience is unclear, ask before building.

## 1. Hierarchy

**Users should spot the most important thing at a glance.**

- Every screen gets **one** primary focal point and **one** primary action.
- Use size, weight, contrast, and spacing to rank importance. Don't use all four to make everything shout.
- Keep the type scale small, using the project's tokens. Headings should be visibly distinct from body text.
- Above-the-fold content is what users care about most. Secondary material can wait for a scroll.
- Show orientation cues like page titles, breadcrumbs, and active nav states, so users always know where they are.

Test: blur the screen or squint. If you can't tell what matters most, the hierarchy is broken.

## 2. Progressive Disclosure

**Show only what the current decision needs. Reveal the rest in steps.**

- Split long forms and setups (onboarding, checkout, config) into short, sequenced steps.
- Hide advanced or rarely used options behind "More", "Advanced", expanders, or secondary pages.
- Multi-step flows must show progress, for example "Step 2 of 4" or a stepper, and allow going back without losing input.
- Don't ship every feature onto one screen because it's available. Choosing what to leave out is part of the design.

## 3. Consistency

**The same thing looks and behaves the same everywhere.**

- Reuse existing components. A button, input, or card should not be restyled per page.
- Keep identical spacing, radius, color, and type tokens across screens. Don't use magic numbers.
- Put the same actions in the same places: primary action position, nav layout, and close/cancel placement.
- Use the same words for the same things, such as "Delete" vs "Remove" or "Sign in" vs "Log in". Pick one.
- **Every deviation needs a stated reason.** A button that is suddenly bigger makes users wonder why. If you can't explain the difference, remove it.

## 4. Contrast

**Spend emphasis on purpose. Contrast is a budget.**

- Reserve the strongest contrast for the primary action or critical information.
- Destructive actions get a distinct danger treatment, such as red, and a confirmation step. The safe alternative, like "Keep account", stays visually quieter so the two never compete.
- Secondary and tertiary actions use subdued styles, such as outline, ghost, or gray.
- If two elements compete for attention, demote one.

## 5. Accessibility

**Not optional. Vision impairment affects more than one in four people worldwide.**

- Color contrast meets WCAG AA: ≥ 4.5:1 for body text, ≥ 3:1 for large text and UI components or focus indicators.
- Never use color alone to carry meaning. Pair it with an icon, text, or pattern.
- Every meaningful image has `alt` text. Decorative images use `alt=""`.
- Everything works with a keyboard. Tab order follows visual order, focus is always visible, and nothing traps focus except modals, which return focus when closed.
- Use semantic HTML first (`button`, `a`, `label`, `nav`, `main`, headings in order). Add ARIA only when native semantics can't express it.
- Every input has a programmatic `<label>`, and errors are announced and linked to their field.
- Touch and click targets are at least 44×44px, with padding between adjacent targets.
- Respect `prefers-reduced-motion` and user font scaling. Don't lock font sizes in px when the project uses rem.

## 6. Proximity

**Things that belong together stay together. Risky things stay apart.**

- Group related controls tightly, such as play, pause, and seek, or a field and its label and error message.
- Use more space *between* groups than *within* them. Spacing alone should show the structure.
- Physically separate destructive or exit actions (Quit, Delete, Discard) from frequently used controls to prevent accidental clicks.
- Labels sit closer to their own field than to the neighboring one.

## 7. Alignment

**Clean lines create order and make screens easier to read.**

- Lay out on a grid or spacing scale (for example 4px or 8px steps) from the project's tokens.
- Use consistent left edges, and align text baselines and field edges in forms.
- Don't center-align long text or forms. Centering is for short, isolated content.
- Spacing values come from the scale only. Any off-grid value needs a reason.

## 8. Make It Effortless

- Every interaction gives feedback: hover, focus, active, disabled, loading, success, and error states.
- Design the empty, loading, and error states, not just the happy path.
- Add shortcuts where they speed up common tasks, such as search, keyboard shortcuts, sensible defaults, and autofocus on the first field.
- Keep navigation in the same place on every page.
- Prevent errors before reporting them, with constraints, inline validation, and confirmation for destructive actions.

## 9. Verify

**UI isn't done until it has been looked at and used.**

Before calling UI work complete:
1. Render it and look at it at mobile, tablet, and desktop widths → verify: no overflow or horizontal scroll, and the hierarchy holds.
2. Navigate it with the keyboard only → verify: everything is reachable, focus is visible, and the order is logical.
3. Check contrast for text and key UI → verify: it meets AA.
4. Walk the primary flow end to end, including error and empty states → verify: the user always knows where they are and what to do next.
5. Compare against existing screens → verify: components, spacing, and wording are consistent, and any deviation is justified.

If you can't run or view the UI, say so explicitly rather than claiming it works.

---

**These guidelines are working if:** each screen has one obvious next step, new UI is indistinguishable in style from existing UI, nothing relies on color alone, and users never have to ask "where am I?" or "what does this do?"
