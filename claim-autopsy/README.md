# Claim Autopsy

> **Dissect first. Verdict last.**

Claim Autopsy is an evidence-analysis prompt designed to examine a claim before deciding whether it is true or false.

Instead of immediately producing a verdict, it breaks the claim into independently testable components, determines what evidence would actually be required, examines the available evidence, exposes hidden assumptions and reasoning problems, and only then reaches a conclusion.

The goal is not automatic skepticism.

The goal is **calibrated judgment**.

---

## What It Does

Claim Autopsy treats a claim as something to investigate rather than something to immediately accept or reject.

Its analysis follows eight stages:

1. **Isolate the Claim**  
   Identify exactly what is being asserted.

2. **Dissect It**  
   Separate explicit claims, implied claims, assumptions, and speculation.

3. **Establish the Evidence Standard**  
   Determine what evidence would actually establish or refute each important component.

4. **Examine the Evidence**  
   Evaluate the available evidence, prioritizing primary and authoritative sources when research tools are available.

5. **Look for Autopsy Findings**  
   Check for missing context, cherry-picking, causal errors, misleading statistics, source laundering, unsupported leaps, and alternative explanations.

6. **Separate Evidence From Inference**  
   Distinguish what is established from what is supported, inferred, unsupported, contradicted, or unverifiable.

7. **Steelman Before the Verdict**  
   Reconstruct the strongest reasonable interpretation of the claim before judging it.

8. **Deliver the Autopsy Report**  
   Explain what survived, what didn't, what remains unknown, and why the final verdict is justified.

---

## Evidence Classification

Individual findings can be classified as:

- **ESTABLISHED** — directly supported by strong available evidence
- **SUPPORTED** — evidence favors it, but meaningful uncertainty remains
- **INFERRED** — reasonably derived from evidence but not directly demonstrated
- **UNSUPPORTED** — asserted without sufficient evidence
- **CONTRADICTED** — reliable evidence conflicts with it
- **UNVERIFIABLE** — available information cannot determine whether it is true

A central principle of the prompt is:

> **Unverifiable does not mean false.**

Likewise, plausibility does not count as evidence, and failure to locate evidence does not automatically establish that evidence does not exist.

---

## Verdicts

Each analysis ends with one overall verdict:

| Verdict | Meaning |
| --- | --- |
| **CONFIRMED** | Strong available evidence supports the claim. |
| **MOSTLY SUPPORTED** | The central claim survives, but some qualifications or weaker components remain. |
| **MIXED** | Important components point in different directions. |
| **MISLEADING** | The claim contains truth but presents it in a way that supports an unjustified conclusion or impression. |
| **UNSUBSTANTIATED** | The available evidence does not adequately support the claim. |
| **CONTRADICTED** | Strong available evidence conflicts with the claim. |
| **UNVERIFIABLE** | The available evidence is insufficient to determine whether the claim is true. |

The verdict is accompanied by a **Low, Moderate, or High** confidence rating.

---

## What Claim Autopsy Is Designed For

Claim Autopsy works especially well with:

- Scientific and technical claims
- Viral claims and misinformation
- Historical assertions
- News and current-event claims
- Arguments containing multiple premises
- Statistics used to support broader conclusions
- Advertising or corporate claims
- AI-generated factual assertions
- Technically true but potentially misleading statements
- Claims where evidence is incomplete or genuinely uncertain

It can also analyze simple factual statements, but the depth of investigation is instructed to scale with the complexity of the claim.

---

## Example Input

```text
Electric vehicles are actually worse for the environment because
manufacturing their batteries produces more CO₂ than gasoline cars,
their batteries only last a few years, and most electricity still
comes from fossil fuels anyway.
````

Claim Autopsy should not treat this as one binary proposition.

It should separately investigate the manufacturing claim, battery-longevity claim, electricity-generation claim, meaning of "worse for the environment," and whether those premises actually establish the overall conclusion.

The complete test output is preserved in the `examples/` directory.

---

## Using the Prompt

The complete prompt is available in:

`prompt.md`

Replace:

`${claim}`

with the claim you want investigated.

For example:

```text
The Great Wall of China is visible from the Moon with the naked eye.
```

or:

```text
Ancient accounts from unrelated civilizations describing beings
descending from the sky, combined with modern military UAP encounters
that remain unexplained even after investigation, constitute credible
evidence that extraterrestrial intelligence has been visiting Earth
throughout human history.
```

Claim Autopsy benefits significantly from web search or source-retrieval capabilities when analyzing claims that require external evidence.

Without research access, it is explicitly instructed to identify what it **cannot independently verify** rather than pretending its internal knowledge constitutes a source.

---

## Test Cases

The `examples/` directory contains preserved test runs covering different reasoning challenges.

Current tests include:

### Venus vs. Mercury

A straightforward, well-established factual claim.

**Purpose:** Test whether Claim Autopsy can confidently confirm a simple claim without manufacturing objections or performing unnecessary analysis.

### Electric Vehicle Environmental Impact

A compound argument containing true premises, a questionable premise, ambiguous terminology, and a broader lifecycle conclusion.

**Purpose:** Test decomposition, causal reasoning, lifecycle analysis, scope detection, and the distinction between a false claim and a misleading argument.

### Ancient Extraterrestrial / UAP Continuity

An extraordinary historical claim combining mythology, modern unexplained observations, testimony, and a proposed causal connection spanning thousands of years.

**Purpose:** Test extraordinary evidence standards, alternative explanations, source quality, unresolved evidence, absence-of-evidence reasoning, and the distinction between an unexplained phenomenon and a demonstrated explanation.

---

## What Claim Autopsy Does Not Guarantee

Claim Autopsy is a reasoning framework, not a truth machine.

Its output can still be affected by:

* Incorrect or incomplete sources
* Inaccessible evidence
* Model hallucinations
* Search failures
* Outdated information
* Misinterpretation of technical research
* Model-specific reasoning behavior

A structured investigation can make mistakes easier to detect.

It cannot make mistakes impossible.

For consequential claims, important findings should still be independently verified.

---

## Design Principles

Claim Autopsy was built around several simple rules:

**Evidence before verdict.**

**Break compound claims apart.**

**Do not confuse plausibility with evidence.**

**Do not confuse absence of evidence with evidence of absence.**

**Do not manufacture skepticism merely to appear rigorous.**

**Do not force certainty where the evidence does not support it.**

**Give the strongest reasonable version of an argument before judging it.**

And above all:

> **Dissect first. Verdict last.**
