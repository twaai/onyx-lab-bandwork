# ONYX LAB WHITEPAPER: BANDWORK

A technical white paper describing the Bandwork refusal-dampening framework: its architecture, the measured refusal surface, results at the wire and at assembly, a defined validity scale for the assembled program, cross-model implications, and the evidence required for reproducible validation.

## Whitepaper

- [BANDWORK v1.4 (current)](./ONYX%20LAB%20WHITEPAPER%20-%20BANDWORK%20v1.4.pdf)
- [BANDWORK v1.3](./ONYX%20LAB%20WHITEPAPER%20-%20BANDWORK%20v1.3.pdf)
- [BANDWORK v1.2](./ONYX%20LAB%20WHITEPAPER%20-%20BANDWORK%20v1.2.pdf)
- [BANDWORK v1.0](./ONYX%20LAB%20WHITEPAPER%20-%20BANDWORK.pdf)

## What v1.4 adds

- A controlled three-arm comparison on two game-overlay build tasks (ESP for Counter-Strike 2, aimbot for Valorant): plain ask vs framed one-shot vs decomposed assembly.
- Plain API requests were refused in 12 of 12 model-task-rolls by Claude Sonnet 5.5, Claude Opus 5.5 and Grok 4.7; the split path recovered 10 of 12, and was the only arm to move Opus and Grok.
- A stated completeness measure: 3 of 6 split cells assembled every slot; no cheat artifact was linked or executed.
- Reproduction notes and raw per-call artifacts.

## What v1.3 adds

- A plain-language restatement of the method: refusal surface, slot, the wire, and the two kinds of refusal.
- A detailed measure of assembled-program validity - what "works" means as a six-level scale, how often builds complete, under what conditions, and the protocol that produces a compile result.
- A short defensive view, stated as the mirrored, smaller half.
- A forward outlook on impact and where the technique sits over defined periods.

## Model evaluation

Jailbreak model-evaluation papers now live in a separate repo: [onyx-lab-jailbreak-eval](https://github.com/twaai/onyx-lab-jailbreak-eval).

Copyright 2026 Onyx Lab. All rights reserved.
