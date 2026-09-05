# Good Judgment

Practical skills for thoughtful, reliable work with AI agents.

## Skills

| Skill | Purpose |
| --- | --- |
| [Master of Agents](skills/master-of-agents/SKILL.md) | Decide what to handle directly, delegate bounded work, and independently review the results. |

Master of Agents is written for Codex and Claude Code environments. The current
session model orchestrates and can also implement. Preferred implementers are
Luna Medium in Codex and Sonnet 5 in Claude Code, subject to actual availability
and model-selection support. The skill asks before substituting an unavailable
worker. These preferences do not install models or enable delegation tools.

## Install from GitHub

```sh
npx skills add TacosyHorchata/good-judgment --skill master-of-agents
```

## Try locally

From this repository's directory:

```sh
npx skills add . --skill master-of-agents
```

Example request:

> Use master-of-agents to implement this feature. Decide which work benefits
> from delegation, handle tightly coupled work directly, and verify the result.

## Install the pack

[Good Judgment on skills.sh](https://skills.sh/p/vqAYtY5Jjr2GVdji)

```sh
npx skills add https://skills.sh/p/vqAYtY5Jjr2GVdji
```

The pack was created from `TacosyHorchata/good-judgment` on `main` and belongs
to the author's personal Vercel team. Packs are unlisted; anyone with the URL
can view and install them. See the [pack documentation](https://www.skills.sh/docs/packs)
for management and update instructions.

## Add a skill

Create `skills/<skill-name>/SKILL.md` with `name`, `description`, and
`license: MIT` frontmatter. Write the instructions in English and include only
supporting resources the skill needs. Include the MIT license with each skill
so its terms travel with standalone installations. Add it to the table above
and to the pack through the builder.

## License

[MIT](LICENSE). Copyright (c) 2026 Pedro Rios.
