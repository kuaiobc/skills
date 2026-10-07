# Skills

Cursor agent skills for architecture work and for controlling how a document is written.

Each skill lives in `.agents/skills/<name>/` and starts at that directory's `SKILL.md`.

## Skills

| Skill | Path | Role |
|---|---|---|
| architecture-writing | `.agents/skills/architecture-writing/` | Discover a system, reason about it, list architecture options, and recommend one. A person confirms, rejects, or modifies the recommendation before it becomes the decision. |
| writing-style | `.agents/skills/writing-style/` | Turn purpose, audience, language, and style preferences into writing behavior, then draft, evaluate, and revise. Domain facts come from the request or from a domain skill. |

## How they divide the work

`architecture-writing` owns the architecture model: evidence, scores, constraints, governance outcomes, the recommendation, and `human_decision`. `human_decision` stays `pending` until a person selects.

`writing-style` owns expression: tone, structure, audience, language, and removal of mechanical phrasing. When it is available, `architecture-writing` may use it after the model exists. Rewriting may change order and wording. It may not change facts, confidence, scores, governance results, the recommendation, or the human decision.

If `writing-style` is not available, `architecture-writing` still has a minimal writing method in `writing/technical-writing.md`.

## Start here

- Architecture tasks: [architecture-writing/SKILL.md](.agents/skills/architecture-writing/SKILL.md)
- Architecture package overview: [architecture-writing/README.md](.agents/skills/architecture-writing/README.md)
- Writing and revision tasks: [writing-style/SKILL.md](.agents/skills/writing-style/SKILL.md)
- Writing package overview: [writing-style/README.md](.agents/skills/writing-style/README.md)
