# agent-coding-rules

Coding rules for AI coding agents such as Claude Code and Codex: one short file the agent
reads every session, and one longer document it opens when it gets stuck.

| File | When the agent reads it | What it holds |
|---|---|---|
| [coding-rules.md](coding-rules.md) | Every session | Principles (SSOT, DRY, KISS, YAGNI, SOLID, performance, memory and thread safety), a few hard rules, and rules for handling evidence. |
| [PROBLEM_SOLVING.md](PROBLEM_SOLVING.md) | When stuck | "Drain the water first": remove what limits your options before calling in an expert. |

## Install

1. Clone this repository to `~/.agent-docs`. The rules file points to that folder.

   ```sh
   git clone https://github.com/jungdaesuh/agent-coding-rules ~/.agent-docs
   ```

2. Give `coding-rules.md` to your agent:

   | Agent | What to do |
   |---|---|
   | Claude Code | Copy `coding-rules.md` into `~/.claude/rules/` (create the folder if it does not exist). |
   | Codex | Paste the contents of `coding-rules.md` into `~/.codex/AGENTS.md`. If you have a non-empty `~/.codex/AGENTS.override.md`, Codex reads that file instead, so paste it there. |
   | Other agents | Paste the contents into the agent's global instructions file. |

3. Start a new session.

## Update

Run `git -C ~/.agent-docs pull`, then repeat step 2.

## Remove

Delete the copied file or the pasted text, then delete `~/.agent-docs`.

## Make them yours

These rules are opinions. Edit your copy of `coding-rules.md` and drop what does not fit your work.

## License

[MIT](LICENSE)
