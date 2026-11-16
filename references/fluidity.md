# Fluidity: seamless transitions

## The principle

A fluid interface is like moving through water: **you float rather than walk**. In practice that means visible links between screens, components, and features, so that every state change reads as a natural next step.

Static transitions break the user's sense of flow and orientation. They also make a product feel lifeless, and "a lifeless product feels like a dead product, and a dead product feels uncared for."

Motion is never added for its own sake. **Each animation has an architectural job: helping the user understand how they got from A to B.**

## Physical rules

Treat the app as a space with **unbreakable physical rules**:

- Before adding a transition, know *how and why* it makes sense in the navigation model. A view-level transition only works if you understand the app's navigation deeply.
- Aim for dimensionality: every movement should feel like a logical step, the way movement works in physical spaces.
- In principle any element can turn into another, **if there is a strong enough reason for the transformation**.

## Rules

### 1. Avoid static transitions
The default is motion, not a cut. Speed still matters, but well-applied motion can make things clearer *and* feel just as fast. Motion can also make the product *seem* faster (for example, price charts that animate between values instead of redrawing).

### 2. Directional motion encodes space
Switching tabs includes a brief directional movement: tap a tab on the left and the transition moves left, and the same for the right. "We fly instead of teleport."

### 3. Map the journey
In multi-path flows such as onboarding, use motion to show the structure: for example, a stack of cards that lays out where the user is heading and shows how a different choice would lead somewhere else. The user should never feel lost.

### 4. Animate the small things too
The principle reaches the smallest details. For example, the chevron in a multi-step flow changes shape between screens to make the navigation action clear. These details add up over time.

### 5. Morph text instead of swapping it
When a label changes, especially when its meaning changes (**Continue → Confirm**), morph it visibly instead of replacing it instantly. A silent swap can leave the user unaware that they are about to take a significant step, such as confirming a transaction.
- Family's system uses **shared letters** (the "Con" in both words) as anchors and animates only what differs.
- Use the same approach for counts and dynamic labels (for example, a button label that updates as the user adds wallets).

### 6. Never duplicate a persistent element
If a component occupies a space and **will still be there in the next phase**, it should stay consistent. It should travel, not be cloned or cross-faded.
- Example: wallet cards move between screens as the same object.
- Example: in empty states, keep the unchanged part of a sentence still and update only the part that changes, rather than replacing the whole sentence.

### 7. Show cause and effect, especially where money or data is at stake
- Entering an amount → confirming it: carry the value visually across screens so the user can trust that the amount entered is the amount sent.
- After confirming, move a spinner into the bottom navigation to show where the pending transaction now lives (the activity tab).
- Follow-up actions follow the same physics: "speed up" moves its spinner into the original pending tray to show it applies to that transaction.
- Reorganising data (for example, grouping addresses by seed phrase) should animate items into place so the user can see what the action did.

### 8. Everything compounds
A single fluid transition does not make an interface fluid. Fluidity comes from hundreds, really thousands, of small deliberate decisions: trays morphing into full screens, buttons gliding across trays, buttons morphing into trays and back. Every interaction feeds into the next.

## The trust argument

Glitchy or missing motion erodes trust. It makes the user wonder whether the app understands what they are trying to do. Consistent, smooth motion communicates: *"I know exactly what you need — let me get that for you."* Fluidity is a commitment to comfort, clarity, and continuity.

## Before/after test

To judge whether a transition earns its place, compare it with a static version. If removing it loses the sense of connection, the contextual continuity, or the clarity of intent and outcome ("digital whiplash"), keep it. If nothing is lost, it may be decoration.

## Implementation notes

- Use shared-element / layout animations (for example, FLIP, View Transitions API, `matchedGeometryEffect`, Framer Motion `layoutId`) so that persistent elements are the *same* node moving between layouts.
- For text morphs, diff the old and new strings, keep the common characters in place, and animate only what was inserted or removed.
- Direction should come from navigation order (index delta), not be hard-coded per screen.
- Keep durations short enough that the motion never feels slower than a cut. For web token scales, see the local `transitions-polish` skill.
- Respect `prefers-reduced-motion`: keep the spatial cues (for example, a short opacity or position hint) and drop the large movement.
