# Investigation Patterns

Use this file when the question is ambiguous, the experiment design is non-obvious, or the claim mixes multiple ideas that need to be separated.

## Evidence ladder

Prefer stronger evidence when available:

1. Direct measurement from the target system or dataset
2. Controlled experiment with repeatable inputs
3. Simulation or Monte Carlo model with documented assumptions
4. Analytical reasoning from explicit rules or source code
5. Anecdotes, commentary, or intuition

If a weaker layer is all that is available, say so plainly.

## Turning vague claims into measurable questions

Convert fuzzy words into proxies that can be observed or counted.

- `more random` -> roll frequency, entropy, variance, outcome swing, sensitivity to luck
- `better` -> win rate, speed, accuracy, cost, user success, error rate
- `safer` -> failure probability, blast radius, recovery time, exploitability
- `simpler` -> state count, rule count, branch factor, implementation complexity, time to explain

If a term supports multiple proxies, either test several or explain which proxy matters most.

## Comparing two systems fairly

- Use matched scenarios.
- Keep units consistent.
- Normalize by time, turn, request, user, or session when raw totals would mislead.
- Separate frequency from impact. A system can have fewer random events but higher swing per event.
- Distinguish rule-level randomness from practical play randomness when both matter.

## Experiment patterns

### Comparative analysis

- Define shared metrics.
- Build a side-by-side table.
- Use the same assumptions for both sides.
- Check whether the ranking changes under different reasonable assumptions.

### Monte Carlo or simulation

- State the model rules.
- Document assumptions and simplifications.
- Run enough iterations to stabilize the result.
- Report distributions, not only averages.
- Set or report the random seed when reproducibility matters.

### Controlled software test

- Change one variable at a time.
- Capture logs, counters, timings, or outputs.
- Repeat trials when nondeterminism exists.
- Record environment details that could affect the result.

### Source or code inspection

- Trace the actual path that implements the behavior.
- Count decision points, randomness calls, or branches when relevant.
- Treat static inspection as evidence about mechanism, not automatic proof about user-facing impact.

## Handling ambiguous outcomes

If the evidence is mixed:

- Split the original claim into narrower subclaims.
- Report which subclaims are supported and which are not.
- Prefer `refined` or `unresolved` over forcing a yes-or-no answer.
- Suggest the next discriminating experiment.
