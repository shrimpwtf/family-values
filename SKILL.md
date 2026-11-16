---
name: family-values
description: Applies the Family wallet design philosophy (Benji Taylor, "Family Values") of simplicity, fluidity, and delight to product and interface work. Use when designing, building, or reviewing app flows, navigation, sheets/trays/modals, transitions, onboarding, confirmation steps, empty states, or "make this feel polished/premium/like Family". Triggers on "family values", "Family wallet", "feel like Family", "dynamic tray", "tray system", "gradual revelation", "progressive disclosure", "fluid interface", "avoid static transitions", "text morph", "Continue to Confirm", "selective emphasis", "delight-impact curve", "easter egg", "add delight", "make it feel considered".
---

# Family Values

A design philosophy for making complex products feel welcoming, distilled from Benji Taylor's essay on building the Family crypto wallet. It is not an animation tutorial. It is a set of principles and concrete rules for deciding *what* to show, *how* to move between states, and *where* to spend polish.

> Simplicity ensures accessibility, fluidity maintains continuity of experience, and delight fosters meaningful connections.

The three values, in priority order:

| Value | Mechanism | One-line rule |
|---|---|---|
| **Simplicity** | Gradual revelation | Fundamentals at your fingertips; everything else appears when it becomes relevant. |
| **Fluidity** | Seamless transitions | Never teleport. Every change of state shows where you came from and where you went. |
| **Delight** | Selective emphasis | Polish everything evenly, then spend extra magic where features are used least. |

Underneath all three sit table-stakes values (utility, performance, security). Never trade those away for the three above.

## How to use this skill

Pick the mode that matches the request, then load only the references it needs.

### 1. Designing a new flow or feature
1. Map the flow's paths and edge cases first. Simplicity in a product with hundreds of paths has to be designed on purpose.
2. Decide per step: **tray or full screen?** See [references/tray-system.md](references/tray-system.md).
3. Give each step a single job: one piece of content or one primary action.
4. Design the transitions as part of the navigation model, not decoration. See [references/fluidity.md](references/fluidity.md).
5. Place delight by frequency of use. See [references/delight.md](references/delight.md).

### 2. Implementing
- Build trays to the rules in [references/tray-system.md](references/tray-system.md).
- Build motion to the rules in [references/fluidity.md](references/fluidity.md). For web CSS recipes and motion tokens, pair this skill with the local `transitions-dev` and `transitions-polish` skills when they are available.
- Keep persistent elements as the *same* element across states. Do not cross-fade duplicates.

### 3. Reviewing or auditing an existing product
Run [references/review-checklist.md](references/review-checklist.md) and report findings grouped by value: Simplicity, Fluidity, Delight. Each finding should name the surface, the violated rule, and a concrete fix.

## Reference map

| File | Read when |
|---|---|
| [references/simplicity.md](references/simplicity.md) | Deciding what to show, hide, or defer; onboarding; dense feature sets |
| [references/tray-system.md](references/tray-system.md) | Building sheets, modals, confirmations, warnings, or multi-step mini-flows |
| [references/fluidity.md](references/fluidity.md) | Any transition, tab switch, label change, shared element, or chart update |
| [references/delight.md](references/delight.md) | Choosing where to add flourishes, easter eggs, sounds, celebrations |
| [references/review-checklist.md](references/review-checklist.md) | Auditing a design or build against all three values |
| [references/source.md](references/source.md) | Attribution and the Family examples each rule comes from |

## Non-negotiables

- **No static transitions** between related states. Motion should explain the change, and it can be as fast as a cut.
- **One thing per tray.** If a step does two jobs, split it.
- **Consecutive trays differ in height.** If two steps would be the same height, change the content so the progression is visible.
- **Shared elements travel; they are never duplicated.**
- **Critical changes are made visible.** A label that changes meaning, like Continue to Confirm, morphs instead of swapping instantly.
- **Even polish everywhere.** A neglected rarely-used screen undermines the whole product ("a fancy restaurant with a dirty bathroom").
- **Delight scales inversely with frequency.** High-frequency actions get subtle touches; rare moments get the big ones.
