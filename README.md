# family-values

An agent skill that applies the Family wallet design philosophy of **simplicity, fluidity, and delight** to product design, implementation, and review. It is distilled from Benji Taylor's essay [Family Values](https://benji.org/family-values) (July 2024).

## Layout

```
family-values/
├── SKILL.md                     # entry point: principles, modes, non-negotiables
└── references/
    ├── simplicity.md            # gradual revelation
    ├── tray-system.md           # dynamic tray anatomy, rules, tray-vs-screen
    ├── fluidity.md              # seamless transition rules
    ├── delight.md               # selective emphasis, Delight-Impact Curve
    ├── review-checklist.md      # audit checklist across all three values
    └── source.md                # attribution and rule → example index
```

## Install

Put this directory in a skills root that your agent scans (for example `~/.agents/skills/family-values` or `~/.claude/skills/family-values`). The agent loads `SKILL.md` when a request matches its description, and loads the references as needed.

## Credit

The principles and examples belong to Benji Taylor and the Family team. This package only restates them as rules and checklists.
