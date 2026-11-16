# Problem-Solving Principles

Referenced from the agent's global instructions through `coding-rules.md`. Apply on any stuck problem, failed
approach, dead end, or "we need an expert for this" moment, in code and in research alike.

## 1. Drain the water first (option-blocking constraints)

Origin: a sink stopper stuck under a full basin looked like a plumber's job. After the basin was pumped out and
dried, duct tape lifted the stopper in seconds. Removing the water made zero progress on the stopper and all the
difference to which solutions existed.

**Two kinds of constraint.**
- *Goal-blocking*: lowers the score of the current approach (the stopper is stuck).
- *Option-blocking*: shrinks the set of approaches that can be tried at all (the water).

Any search that ranks moves by immediate progress, including a person's first instinct, never removes an
option-blocking constraint, because that move scores zero. The cheap methods it hides stay invisible and the expert
route wins by default.

**Test.** Would removing this constraint change the *score* of my current method, or the *list of applicable methods*?
Only the second is water.

**Procedure.**
1. Write every failure as "approach X fails because condition C holds." C is the candidate water.
2. Classify C: part of the goal (must stay) or part of the state (can be changed).
3. Price removing C on its own, ignoring the goal. Check what C was holding up before removing it.
4. Under not-C, re-list the cheap methods that were rejected or never considered because C made them inapplicable.
5. Reserve a fixed share of effort for moves that only enlarge the option set; no progress-based rule will pick them.
6. Eliminate before escalate: cheapest state change first, expert route last.
7. Record C beside every closed approach. When C changes for any reason, every approach C closed is a live candidate
   again. A dead end is conditional, never final.

**Same principle elsewhere:** preconditions and means–ends analysis in planning; TRIZ's resolution of
contradictions; "without loss of generality" and change of variables in mathematics (reformulate until a known tool
applies: Schrödinger reached his wave equation through the Hamilton–Jacobi equation, the mechanical twin of the
eikonal equation of geometric optics); the minimal reproduction in debugging (remove noise so the bug is visible);
stabilise-before-diagnose in medicine.

**In code work this looks like:** reducing a failing case until the real fault is the only thing left before
changing code; removing a flaky dependency or a stateful fixture before debugging the logic behind it; asking which
assumption makes the simple fix unavailable before reaching for a framework, a rewrite, or an outside library.

**In research this looks like:** every negative result carries the hypothesis that closed it; a change to any axiom
reopens every result that hypothesis closed; a budget line exists for experiments whose only output is a larger
option set.

## Adding principles
One numbered section per principle: origin, the distinction it draws, a test, a procedure, where it already lives.
Keep each under sixty lines. Reference this file from the agent's global instructions with a pointer of at most one
paragraph; do not copy sections into them.
