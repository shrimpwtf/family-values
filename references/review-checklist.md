# Family Values review checklist

Use this to audit a design, prototype, or build. Report each finding as:

`[Value] Surface - violated rule - concrete fix`

Group the report under **Simplicity**, **Fluidity**, and **Delight**, most severe first. Call out what is already done well too, so it doesn't get regressed.

## Simplicity

- [ ] The default view shows only the fundamentals. Secondary features appear on intent.
- [ ] Newcomers can get started without being overwhelmed, and power features are still reachable (deferred, not deleted).
- [ ] Complex tasks are split into compact, focused steps.
- [ ] Each step or tray has exactly one piece of content or one primary action.
- [ ] Confirmations and warnings appear in context, at the right moment, not on a separate screen.
- [ ] Going deeper keeps the user in their current context.
- [ ] Edge-case paths (errors, empty, first use) were designed, not left to defaults.

## Trays (if the product uses sheets, modals, or trays)

- [ ] Every tray has a title and a leading icon (dismiss on the first tray, back on later ones).
- [ ] Consecutive trays differ in height.
- [ ] Trays opened from a component visibly emerge from it.
- [ ] Tray theme matches the surrounding flow (dark flow → dark tray).
- [ ] Trays are used for transient actions, and full screens for permanent destinations.

## Fluidity

- [ ] No static cuts between related states.
- [ ] Tab and lateral navigation moves in the direction of travel.
- [ ] Persistent elements travel between states and are never duplicated or cross-faded.
- [ ] Labels that change meaning (Continue → Confirm) morph visibly.
- [ ] Changing counts and partially changing text animate only the part that differs.
- [ ] Values entered by the user are carried visibly into confirmation screens.
- [ ] After an action, motion shows where its result now lives (for example, a pending indicator moving to its tab).
- [ ] Reorganising or sorting data animates items into their new places.
- [ ] Motion never feels slower than a cut, and charts animate between values.
- [ ] No glitchy, janky, or interrupted animations on trust-critical paths.
- [ ] Reduced-motion users still get the spatial cues.
- [ ] Before/after test: removing each transition would cost clarity. If not, question it.

## Delight

- [ ] Polish is even across the product, including rarely used settings and edge screens ("no dirty bathroom").
- [ ] Features were ranked by frequency, and delight intensity scales inversely with it.
- [ ] Core high-frequency actions have only subtle, non-blocking touches.
- [ ] Significant but rare moments (setup, backup, milestones) are celebrated, not streamlined into something forgettable.
- [ ] First-use and empty states guide the user in a friendly way.
- [ ] Any easter eggs sit on moderately used surfaces and are discoverable but never in the way.
- [ ] Delightful touches also carry meaning (status, reassurance, guidance).
- [ ] Sound, where used, is sparing and tied to completing something.

## Table stakes (never trade away)

- [ ] Utility: the feature actually solves the job.
- [ ] Performance: motion and flourishes never cost responsiveness.
- [ ] Security: clarity on money and safety-critical steps comes before any flourish.
