# Prompt Lab

**A collection of tested AI prompts designed to make language models do something more useful than simply produce an answer.**

Prompt Lab is a growing collection of structured prompts for research, reasoning, analysis, idea evaluation, and other specialized AI tasks.

Each prompt is treated as a small tool rather than a clever piece of wording.

Prompts are developed, tested against different kinds of inputs, and published alongside real example outputs so you can see how they behave before using them yourself.

## Why This Exists

A prompt can sound impressive and still perform badly.

It may work on the example it was written around but fail on unusual inputs. It may encourage hallucinations, excessive agreement, false certainty, shallow analysis, or the same canned response regardless of what the user provides.

Prompt Lab takes a more experimental approach:

**Design → Test → Stress → Revise → Publish**

Where possible, each prompt includes:

- The complete prompt
- Its intended purpose
- Variables and usage instructions
- Real test inputs
- Unedited AI outputs
- Notes about successes and failures
- Edge cases and limitations
- Version information

The goal isn't to prove that a prompt produces perfect answers.

The goal is to show **what it actually does.**

---

## Testing Philosophy

These prompts are not evaluated only with inputs they're expected to handle well.

Testing deliberately includes:

**Controls** — straightforward cases with well-established answers.

**Compound cases** — inputs containing multiple claims, assumptions, or reasoning steps.

**Ambiguous cases** — questions where definitions substantially affect the answer.

**Adversarial cases** — inputs likely to trigger hallucination, sycophancy, reflexive skepticism, or unjustified certainty.

**Boundary cases** — questions where available evidence may not support a definitive conclusion.

**Doozies** — deliberately strange or difficult inputs intended to push the prompt until something breaks.

A successful test does not require the AI to reach a predetermined conclusion.

What matters is whether the prompt produces the **reasoning behavior it was designed to produce.**

---

## Test Outputs

Example outputs in this repository are preserved as closely as practical to the original model responses.

They are **not presented as ground truth**.

An impressive-looking AI response can still contain factual errors, questionable citations, reasoning mistakes, or unsupported conclusions.

Test outputs exist to demonstrate prompt behavior.

When an output contains a known problem, it should be documented rather than silently corrected.

---

## Using the Prompts

Each prompt has its own directory containing its prompt, documentation, and available test results.

Copy the prompt, provide the requested variables or input, and run it with a compatible AI model.

Some prompts can take advantage of capabilities such as:

- Web search
- Source retrieval
- File analysis
- Code execution
- Long context windows

Results may differ between models and between model versions.

A prompt should guide model behavior.

It cannot guarantee model correctness.

---

## Repository Structure

    ```text
    prompt-lab/
    │
    ├── README.md
    │
    ├── <prompt-name>/
    │   ├── README.md
    │   ├── prompt.md
    │   └── examples/
    │       └── ...
    │
    ├── <another-prompt>/
    │   ├── README.md
    │   ├── prompt.md
    │   └── examples/
    │       └── ...
    │
    └── LICENSE
    ```

Each prompt directory is self-contained so new prompts can be added without requiring the central documentation to be rewritten.

---

## Prompts.chat

Public versions of these prompts may also be published on **Prompts.chat** for easier discovery and use.

This repository serves as the extended documentation and testing archive, including test runs and supporting material that cannot be fully represented in a prompt listing.

---

## Contributions & Testing

Trying one of these prompts on a difficult input?

Additional test cases, model comparisons, bug reports, edge cases, and prompt improvements are welcome.

Especially useful reports include:

1. The prompt and version used
2. The model used
3. The exact test input
4. The unedited output
5. What worked or failed
6. Whether the failure can be reproduced

A prompt failing in an interesting way is useful information.

---

## Status

**Experimental / actively developed**

Prompts and model behavior can change over time. Test results should therefore be treated as snapshots of a particular prompt running on a particular model at a particular time.

---

## The Basic Rule of Prompt Lab

**Don't judge a prompt by how good it sounds. Run it and see what happens.**
