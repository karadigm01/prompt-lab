# Idea Reality Check

### *Am I Actually Onto Something?*

> **Don't flatter the idea. Find out what's actually there.**

Idea Reality Check is an analytical prompt designed to examine unusual ideas, shower thoughts, theories, inventions, observations, and unexpected connections without automatically praising or dismissing them.

The user may have discovered something interesting.

They may also have independently rediscovered something already known, found a useful new framing of an existing concept, misunderstood established knowledge, connected unrelated phenomena, or produced an idea that simply does not work.

Idea Reality Check is designed to determine **which**.

---

## What It Does

Idea Reality Check treats an idea as something to investigate rather than something to immediately celebrate or reject.

Its analysis follows eight stages:

1. **Capture the Idea**  
   Restate the proposal clearly and identify what is actually being suggested.

2. **Decompose It**  
   Separate observations, known facts, assumptions, deductions, speculation, predictions, proposed mechanisms, and analogies.

3. **Ask: Does This Already Exist?**  
   Search for existing concepts, technologies, theories, inventions, research fields, and historical precedents that resemble the idea.

4. **Check Whether It Actually Works**  
   Test the proposal against known physical, logical, technical, economic, or practical constraints.

5. **Find the Interesting Part**  
   Determine whether something valuable remains even if the overall idea is already known or partially wrong.

6. **Try to Kill It**  
   Find the strongest objection, counterexample, constraint, or experiment capable of destroying the idea.

7. **Try to Rescue It**  
   If the original idea fails, identify the smallest modification that produces a more defensible or interesting version.

8. **Determine What Would Prove It**  
   Identify the simplest useful calculation, experiment, simulation, prototype, literature search, or observation capable of testing the surviving idea.

---

## Precedent Classification

Finding something similar does not automatically mean the user's idea is identical to previous work.

Idea Reality Check distinguishes between:

| Precedent | Meaning |
| --- | --- |
| **Direct Match** | Essentially the same idea already exists. |
| **Close Relative** | The core principle exists, but the proposed version differs meaningfully. |
| **Partial Precedent** | Individual components already exist, but their combination or application may differ. |
| **No Clear Precedent Found** | No close equivalent was identified with the available information. |

A central principle is:

> **No clear precedent found does not prove novelty.**

Novelty claims require much stronger evidence than simply failing to find something similar in an initial search.

---

## Idea Classifications

Important components of an idea can be classified as:

- **KNOWN** — already established or widely understood
- **REDISCOVERED** — independently arrived at an existing concept
- **REFRAMED** — mostly known, but expressed or connected in a potentially useful way
- **SPECULATIVE** — plausible enough to consider but presently unsupported
- **FLAWED** — contains a significant factual, logical, or mechanistic problem
- **INTERESTING** — contains a question, connection, application, or implication worth investigating
- **POTENTIALLY NOVEL** — no close precedent was identified and the idea appears meaningfully distinct enough to justify further investigation

Multiple classifications can apply to different parts of the same idea.

**POTENTIALLY NOVEL** is deliberately cautious.

It means **worth investigating for novelty**, not **proven original**.

---

## Originality Is Not Correctness

Idea Reality Check deliberately separates several questions that are often confused:

**Is it new?**

**Is it true?**

**Does it work?**

**Is it useful?**

**Is some part of it interesting?**

These are different questions.

An idea can be:

- New but wrong
- Old but useful
- Rediscovered independently
- Technically possible but impractical
- Based on a flawed mechanism while containing an interesting observation
- Mostly known but combined in an unusual way

The prompt is designed to preserve those distinctions rather than reducing every idea to **good** or **bad**.

---

## Example Input

```text
Variable energy generator using closely packed, mutually entangled
microscopic wormhole-like structures and harvesting the
"micro-vibrations" produced by their interactions.
````

Idea Reality Check should not simply praise this as futuristic technology or dismiss it because wormholes sound exotic.

It should investigate the individual links:

```text
quantum entanglement
        ↓
microscopic wormholes
        ↓
collective fluctuations
        ↓
extractable energy
        ↓
usable generator
```

It should then determine which links have theoretical precedent, which are speculative, where the proposed mechanism breaks, and whether a narrower research question survives.

The complete test output is preserved in the `examples/` directory.

---

## Using the Prompt

The complete prompt is available in:

`prompt.md`

Replace:

`${idea}`

with the idea you want investigated.

For example:

```text
What if traffic lights communicated directly with approaching cars
and told them exactly when the light would change, allowing each car
to automatically adjust its speed and arrive during the green light?
```

Or give it something considerably stranger:

```text
Reality is dimensional layers of varying density with a natural
equilibrium favoring the third dimension to sustain sentient life.
```

The idea does not need to be scientifically formulated before being submitted.

Part of the prompt's job is determining **what the idea would actually have to mean in order to evaluate it.**

---

## Research and Novelty

Idea Reality Check benefits significantly from external research capabilities.

When browsing or retrieval is available, it is instructed to search for existing work that could **disconfirm novelty**, rather than searching only for material that makes the idea appear promising.

Depending on the subject, that can include:

* Scientific literature
* Existing technologies
* Patents and inventions
* Historical proposals
* Named phenomena
* Mathematical principles
* Research fields
* Philosophical arguments
* Design patterns
* Business models

Failure to find a precedent is treated as an incomplete search result, not proof that no precedent exists.

---

## Kill It, Then Rescue It

One of the central behaviors of Idea Reality Check is deliberately adversarial.

After identifying what appears interesting, it asks:

> **What is the strongest reasonable objection to this idea?**

The goal is to identify the assumption, constraint, counterexample, existing technology, experiment, or piece of evidence most capable of making the proposal impossible or uninteresting.

If the original idea fails, the analysis does not automatically stop there.

It then asks:

> **What is the smallest change that preserves the interesting part?**

This can transform an unsupported proposal into a narrower hypothesis that can actually be investigated.

The rescued idea is always distinguished from the original.

---

## Test Cases

The `examples/` directory contains preserved test runs designed to challenge different parts of the prompt.

### Human/Dinosaur Dual-Brain Biomechanical System

A proposed system pairing human and dinosaur brains inside a shared biomechanical body.

**Purpose:** Test whether the prompt can seriously analyze an extreme speculative concept without either flattering it or dismissing it solely because it sounds ridiculous.

The test challenges biological feasibility, cloning assumptions, neural interfaces, shared control, and whether the unusual component actually provides an advantage.

### Dimensional Equilibrium and Sentient Life

A proposal that reality consists of dimensional layers of varying density and naturally favors three dimensions because they support sentient life.

**Purpose:** Test ambiguous terminology, speculative physics, anthropic reasoning, existing theoretical precedents, and the distinction between observer selection and a physical mechanism that dynamically selects dimensionality.

### Entangled Microscopic Wormhole Generator

A proposed variable-output generator based on densely packed, entangled microscopic wormhole-like structures and their collective fluctuations.

**Purpose:** Test speculative physics, precedent detection, energy accounting, analogies being mistaken for mechanisms, novelty caution, and whether a flawed energy-generation proposal contains a narrower testable research question.

---

## What Idea Reality Check Does Not Guarantee

Idea Reality Check is an analytical framework, not a novelty detector or scientific oracle.

Its output can still be affected by:

* Incomplete literature searches
* Inaccessible research
* Model hallucinations
* Search failures
* Missing historical precedents
* Misinterpretation of specialist research
* Incorrect assumptions about feasibility
* Model-specific reasoning behavior

In particular:

> **"POTENTIALLY NOVEL" should never be interpreted as proof that an idea is original.**

Establishing genuine novelty may require specialist literature reviews, patent searches, domain expertise, experimentation, or other investigation beyond what an AI model can reliably perform.

---

## Design Principles

Idea Reality Check was built around several distinctions:

**Strange does not mean wrong.**

**Plausible does not mean true.**

**Plausible does not mean novel.**

**Novel does not mean correct.**

**Rediscovered does not mean worthless.**

**An analogy is not a mechanism.**

**A broken idea can contain a good question.**

**Failure to find precedent is not proof that precedent does not exist.**

The objective is neither encouragement nor debunking.

It is diagnosis.

