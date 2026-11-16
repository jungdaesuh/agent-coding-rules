# Coding rules

Rules for AI coding agents. They apply to every project unless the user or the project says otherwise.

## Principles

- **SSOT (single source of truth):** each fact, constant and rule is defined in one place, and everything else refers to that place.
- **DRY (don't repeat yourself):** state each piece of knowledge once. Code that only looks alike and will change for different reasons is not repetition; leave it apart.
- **KISS (keep it simple):** pick the simplest design that meets the requirement.
- **YAGNI (you aren't gonna need it):** build what the task needs now. Add no options, hooks or abstractions for uses nobody has asked for.
- **SOLID:** single responsibility, open for extension and closed for modification, subtypes usable wherever their base type is, small interfaces, and dependence on abstractions instead of concrete details. Read single responsibility as one body of knowledge per module, not one operation per function.
- **Immutable and functional:** prefer values that never change after creation and functions without side effects. Keep mutation and input/output at the edges.
- **Performant:** choose efficient data structures and algorithms from the start, and do no needless work on the common path. Tune only with measurements taken before and after.
- **Memory safe and efficient:** no leaks, no use after free, no out-of-bounds access. Do not hold or copy more data than the work needs.
- **Thread safe:** code that can run concurrently has no data races. Shared state is immutable, confined to one thread, or guarded.

## Hard rules

- **Imports:** declare imports statically at the top of the file. Do not load modules at run time (Python `importlib.import_module()` or `__import__()`, JavaScript `import()` or a computed `require()`, C `dlopen()` or `LoadLibrary()`, Rust `libloading`), and do not nest imports inside functions to delay loading, unless the user asks for it.
- **Types:** never cast to `any`. Keep code type safe.
- **Scope:** do not add defensive checks or try/catch blocks beyond what was requested.
- **Secrets:** never commit `.env` files or their variants. `.env.example` is the only exception.
- **Quality:** when something fails, find and fix the root cause. Take no shortcuts, and do not cheat a check to make it pass. Build production-grade software, not toy features.

## Tool tips

- Search for files with `fd` instead of `find`: it is faster and respects `.gitignore`. Use `find` only when `fd` is not installed.
- Continue a rebase without opening an editor: `GIT_EDITOR=true git rebase --continue`.

## When stuck

After a failed approach, a dead end, or the thought "this needs an expert", read `~/.agent-docs/PROBLEM_SOLVING.md` and apply it.

## Evidence

- **Re-read before quoting.** A summary of earlier conversation is a lossy index, not a source. Before citing a number, ratio or name from a summary or from memory, re-read the file it came from in the current turn.
- **Exit code 0 is not success.** A job that stops at a deadline or an iteration limit can exit with code 0 without having finished its work. Before comparing runs or explaining a result, read each run's own status record: success flag, stopping reason, iteration count, final error. Never compare a finished run with one that stopped early.
- **Tables by script.** Never copy columns of numbers by eye from tool output into a report. Generate the rows with a script that reads the data files.
- **Neutral names until verified.** Name run folders and output files neutrally until the hardware or the result is confirmed. A path named after the machine you asked for or the outcome you hoped for is later read as fact.
- **No temp-only citations.** Anything a report, handoff, commit message or script cites must live in the project tree or other durable storage, not only in a temp folder.
