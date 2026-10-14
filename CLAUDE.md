@AGENTS.md

# Claude: start here

In Claude Code, the import above includes the shared rules and task router.
If reading this file through GitHub or a browser, explicitly open
[AGENTS.md](AGENTS.md#start-here); the `@` line alone does not fetch that file there.

Next, use its task table to choose and **read the full SKILL.md file** from
`.agents/skills/`, then read the topic documents that skill requires before Figma
work. Use file reading (`Read` in Claude Code), or fetch the file from
`EugeneBondarev/Rulla-design` at the same Git revision when using GitHub.

Repository paths start at the Rulla-design root, not another checkout's working
directory. There is no second skill library in `.claude/skills/`. Do not treat a
workflow name as a registered `/command` or pass its file path to the `Skill`
tool; follow the file's instructions after reading it. Missing files/access are
handled by AGENTS.md, not by substituting a different installed skill.
