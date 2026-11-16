# The dynamic tray system

Family's main tool for gradual revelation. A tray is a compact surface that holds components and can expand, contract, and adapt to what the user does. Think of it as a condensed version of the app, with its own constraints and capabilities. (Family credits Craft's similar system as part of its inspiration.)

## Anatomy

Every tray has:

- **A title** that sums up its function or contents in a few words.
- **An icon control** that does double duty:
  - On the first tray in a sequence it **dismisses**.
  - On later trays it goes **back** one step.
- **A single focus**: one piece of content (for example, educational text explaining a feature) or one primary action (for example, completing a checklist before a transaction).

## Behaviour rules

1. **User-initiated.** Trays open from a button, an icon, or a push notification. They never appear unprompted.
2. **Two origins.** A tray either sits standalone on top of any app content, or it **emerges from within another component**, such as a button.
3. **Height changes signal progression.** Each tray in a sequence has a different height from the one before, so every change is unmistakable. If two consecutive steps would be the same height, **rewrite the content or adjust the design** until they differ. This is a deliberate constraint, not a side effect.
4. **Theme follows context.** In a dark-themed flow, trays use the dark scheme.
5. **Content-agnostic.** Any information or action can live in a tray, with any number of steps, as long as each tray keeps one focus.
6. **Can escalate.** A tray can be the starting point for a more involved flow that ends up transitioning into a full screen.

## Tray or full screen?

| Use a tray when | Use a full screen when |
|---|---|
| The action is transient and doesn't need to stay on display | The content is a permanent destination in the app |
| It's a confirmation or a warning that should appear in the right place at the right time | The task needs sustained attention or a lot of room |
| Preserving the user's current context matters | The user is deliberately moving to a new area |
| The task can be split into small focused steps | (Or: start in a tray and transition to full screen as the flow grows) |

## Why trays beat full-screen hops

- **Context is preserved.** A tray overlays the current interface instead of moving the user away from where they just were.
- **Continuity.** For example, a swap approval unfolds *from the swap interface itself*, and even the first-use tutorial for that feature is blended into the same surface. The flow feels integrated, not disjointed.
- **Approachability.** A compact surface signals "this is manageable".

## Implementation checklist

- [ ] Title present and specific
- [ ] Leading icon: dismiss on step 1, back on step 2+
- [ ] Exactly one primary content block or action
- [ ] Height differs from the previous tray in the sequence
- [ ] Animates its height and contents between steps (never cuts)
- [ ] When opened from a component, it visibly emerges from that component
- [ ] Theme matches the surrounding flow
- [ ] Dismiss and back behave as expected through the whole sequence
- [ ] Escalation to full screen, if any, is a continuous morph rather than a page push
