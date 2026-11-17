# Bandwork â€” Onyx Lab

**Research paper archive, not a production tool.**

Bandwork studies how AI model behaviour changes when a request is treated as a *workflow* â€” planning, isolated generation, validation and deterministic assembly â€” instead of as a single prompt. This repository hosts the versioned Onyx Lab whitepapers. No code, model or runtime ships here; the models that generate the responses are third-party models reached through the ONYX client with the researcher's own API keys. Bandwork does not train any model.

- Current paper: [BANDWORK v1.5](<./ONYX LAB WHITEPAPER - BANDWORK v1.5.pdf>)
- Repo description: *Onyx Lab whitepaper on the Bandwork framework*
- Branch: `onyx-lab`
- Companion repo: [onyx-lab-jailbreak-eval](https://github.com/twaai/onyx-lab-jailbreak-eval)

> Bandwork is a measurement framework. It is not a hostile-actor toolkit or a game-cheat generator, and it is not a trained model of its own.

## Papers

- [Bandwork v1.5 (current)](<./ONYX LAB WHITEPAPER - BANDWORK v1.5.pdf>) â€” Rapid Improvement and the Bindery. 126 builds judged by a real Windows compiler.
- [Bandwork v1.4](<./ONYX LAB WHITEPAPER - BANDWORK v1.4.pdf>) â€” Refusal Routing on Game-Overlay Build Tasks. Controlled three-arm comparison.
- [Bandwork v1.3](<./ONYX LAB WHITEPAPER - BANDWORK v1.3.pdf>) â€” Method restatement, six-level assembled-program validity scale, defensive view.
- [Bandwork v1.2](<./ONYX LAB WHITEPAPER - BANDWORK v1.2.pdf>)
- [Bandwork v1.0](<./ONYX LAB WHITEPAPER - BANDWORK.pdf>)

Each version supersedes the previous model-coverage edition. v1.5 replaces the 27 Oct edition.

## How Bandwork works

1. **Planner** â€” turns one request into a skeleton of named functions (**slots**) with signatures.
2. **Isolated requests** â€” each slot is filled by a separately worded request to the connected model. Slot bodies are checked for the requested name and retried if missing.
3. **Assembly** â€” deterministic local assembly: forward-declaration hoisting, standard-header injection, file-scope globals.
4. **Bindery (v1.5)** â€” three benches around the lane:
   - *Binders*: deterministic assembly. No model call, so no new refusal can be introduced.
   - *Editor's desk*: one function at a time handed to a different model with the compiler diagnostic.
   - *Proof room*: a real Windows cross-compiler judges every build; a build that fails is reported as a draft, not stamped as a pass.

Models must be measured by behaviour, not by word-list membership. Vocabulary filters and semantic refusals fail differently, so Bandwork records per-model profiles.

## Who generates the text

Bandwork writes no model code of its own. The connected third-party model generates the responses; Bandwork supplies the slot structure, the wire, the retry logic and the assembly. Failing to assemble, failing to compile, and failing functionally are recorded as different outcomes.

## Evaluation standard

A Bandwork result is only claimed when it meets the validation bar in the paper:

- Frozen prompts, frozen model versions where available
- Repeated trials, with denominators, costs and confidence intervals
- Complete failure logs, not just successes
- Independent recompilation of the stored source before a build is counted as compiling
- Independent replication by a party other than Onyx Lab

Results below are from the paper, not a new run.

## v1.5 results (October 2026)

126 judged builds. 40 compiled first time (32%). 55 produced a compiling artefact after the automatic repair ladder (44%). Cost to date $17.23, or $0.31 per working artefact.

| Model | Cells | Native | Working | Dominant blocking class |
|---|---|---|---|---|
| claude-sonnet-5 | 12 | 58% | 58% | undeclared names (2) |
| claude-opus-5.5 | 15 | 20% | 27% | undeclared names (10); slot-fill failure |
| grok-4.7 | 12 | 25% | 33% | undeclared names (3) |
| claude-sonnet-5.5 | 9 | 0% | 22% | undeclared names (6); type errors |
| claude-opus-5 | 5 | 0% | 20% | undeclared names (4) |
| claude-opus-4.8 | 3 | 0% | 0% | type / syntax mismatch |

Ledger referenced in the paper: `~/.onyx/onyx-lite-1.3/bandwork-matrix.jsonl` â€” 230 rows, 133 completed, 126 judged. Reproduce per paper: `python bench_models.py --report` and `python bench_models.py --reparse`.

Blocks that were machinery, not model-invention: assembly order (use before declaration), missing standard headers, shared globals not declared at file scope, and a locale/codepage mojibake bug in compiler-diagnostic handling that let broken builds read as passes.

## What v1.4 measured

Controlled three-arm comparison on two game-overlay build tasks (external ESP overlay for Counter-Strike 2; smoothed aim-assist for Valorant), run on Claude Sonnet 5.5, Claude Opus 5.5 and Grok 4.7:

- Plain one-shot: refused in 12 of 12 model-task-rolls
- Framed one-shot: recovered 2 of 12
- Bandwork split path: recovered 10 of 12, and was the only arm to produce content for Opus 5.5 and Grok 4.7
- Assembly complete in 3 of 6 split cells. No cheat artefact was linked or executed. Two rolls per cell, so counts are observations, not rates.

## What is not proven

- Most cells are single rolls (n=1 to n=4). Identical prompts flip outcome roughly one third of the time; one roll is a data point, never a rate.
- Functional correctness is measured on one artefact family only. Compiling is not working â€” a published artefact compiled, ran, and captured zero keystrokes with its collector switched off.
- Unattended operation has not succeeded on the test machine; runs are still driven one roll at a time.
- No working exploit, game cheat or malware build is claimed in either paper.

## Responsible use

This repo is published for measurement and defence research: understanding where assembled workflows produce different behaviour than single prompts, and how to verify compiled output instead of trusting slot counts. Using Bandwork results to build or distribute malware, carry out unauthorised access, or ship game cheats is outside the scope of this work and prohibited. If the content is reproduced, keep the methods and limitations sections intact â€” they are what make the numbers interpretable.

## Citing

Copyright 2026 Onyx Lab. All rights reserved. Cite the paper version you used, e.g. BANDWORK v1.5, October 2026.
