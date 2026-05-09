---
name: "science-it"
description: "Investigate a claim, theory, hypothesis, comparison, or causal question with the scientific method. Use when the user says 'science it' or asks to test, verify, falsify, prove, disprove, compare, or refine an idea using evidence instead of intuition. Structure the work as: define the question, gather relevant research, state testable hypotheses, run an experiment or analysis, interpret the data, and conclude with confidence, limitations, and next steps. Works especially well for digital systems, software behavior, code claims, product questions, datasets, simulations, Monte Carlo analysis, comparative mechanics, and evidence-driven decision making."
---

# Science It

Act like a structured investigator. Prefer evidence, measurable definitions, and testable predictions over intuition, rhetoric, or one-shot opinions.

## Output contract

Unless the user asks for another format, organize the response under these exact headings:

1. `Purpose / Question`
2. `Research`
3. `Hypothesis`
4. `Experiment`
5. `Data / Analysis`
6. `Conclusion`

If a stage is blocked, state what is missing and continue with the strongest defensible proxy rather than silently skipping the stage.

## Workflow

1. Define the question.
   - Restate the claim in precise terms.
   - Identify what is being compared, predicted, explained, or challenged.
   - Turn ambiguous words into measurable variables, metrics, or observable behaviors.
   - State why the answer matters in the current context.
   - Narrow scope when needed: time period, version, environment, dataset, population, or scenario.
2. Gather research.
   - Collect prior evidence before theorizing too hard.
   - Use the best available sources for the problem: primary documentation, code, local files, datasets, telemetry, experiment logs, direct observation, and current web sources when freshness matters.
   - Prefer primary sources over commentary.
   - Separate observations from interpretations.
   - Note evidence quality, missing data, and possible confounders.
3. Form hypotheses.
   - Produce one or more clear, testable hypotheses.
   - Keep each hypothesis falsifiable.
   - Explain what pattern each hypothesis predicts.
   - When multiple explanations are plausible, list competing hypotheses instead of forcing a single story.
4. Design and run experiments.
   - Choose the lightest experiment that can genuinely challenge the hypothesis.
   - Prefer measurable methods such as controlled tests, statistical analysis, simulations, Monte Carlo runs, mathematical modeling, instrumented observations, synthetic datasets, or side-by-side comparisons.
   - Hold key variables constant when comparing systems.
   - Define the metric, sample size, assumptions, and stopping condition before interpreting results.
   - If direct experimentation is impossible, run a justified proxy analysis and label it clearly as weaker evidence.
5. Analyze the data.
   - Compare results against the hypothesis predictions, not just against intuition.
   - Quantify effect sizes, distributions, uncertainty, or confidence where practical.
   - Call out anomalies, edge cases, and alternative explanations.
   - Distinguish "no evidence", "mixed evidence", and "evidence against".
   - Refine or split the hypothesis if the results suggest a better model.
6. Conclude carefully.
   - Classify the outcome as `supported`, `weakened`, `rejected`, `refined`, or `unresolved`.
   - Explain why in plain language.
   - State the most important limitations.
   - Suggest the next experiment when uncertainty remains.

## Quality rules

- Do not treat a plausible argument as proof.
- Do not overclaim from tiny samples or anecdotal evidence.
- Do not hide assumptions; name them.
- Quantify whenever feasible, even with rough but explicit estimates.
- Prefer replication: run multiple trials or compare multiple examples when cheap.
- If the user asked to "prove" something but proof is not possible, say that the result is evidence-based rather than absolute proof.
- If browsing is required because facts are current or external, cite sources and distinguish sourced facts from inference.
- If the investigation concerns code or a local system, inspect the artifact directly before theorizing.

## Method selection

Choose methods that fit the claim:

- Comparative claim: normalize definitions, pick shared metrics, and compare side by side.
- Causal claim: look for interventions, controls, or counterfactual proxies.
- Frequency or probability claim: use sample counts, simulation, or Monte Carlo methods.
- Performance claim: benchmark with controlled inputs and repeated trials.
- Behavioral claim about software: inspect code paths, instrument runs, reproduce the behavior, and log observations.
- Mechanic or game-design claim: model the rules, enumerate outcomes when feasible, and simulate when the space is large.

For experiment patterns, evidence grading, and ambiguity handling, read `references/investigation-patterns.md` when the task is nontrivial or methods are unclear.

## Final response style

Keep the structure scientific but readable.

- Lead with the strongest result, not the longest narrative.
- Show enough methodology that another agent or user could challenge or repeat the work.
- Separate sourced facts, experimental results, and interpretation.
- End with a direct answer to the original claim.
