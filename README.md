# Break SynthID

## Overview

This project analyzes vulnerabilities in Google's SynthID-Text
watermarking framework. It demonstrates that the mean score detection
mechanism is intrinsically vulnerable to a Layer Inflation Attack.

## Key Contributions

-   Theoretical proof that TPR@FPR is unimodal in the number of
    tournament layers
-   Central Limit Theorem analysis of the mean score function
-   Black-box Layer Inflation Attack
-   Empirical validation on multiple LLMs

## Core Insight

As the number of tournament layers increases:

1.  TPR initially increases
2.  Reaches a peak
3.  Then decreases
4.  Eventually converges to FPR

This allows watermark removal via artificial layer inflation.

## Attack Summary

The Layer Inflation Attack:

1.  Queries the watermarked model multiple times
2.  Collects candidate outputs
3.  Applies additional tournament layers
4.  Produces a final output with reduced mean score
5.  Bypasses watermark detection

## Experimental Setup

-   Dataset: ELI5
-   Tokens per sample: 100
-   FPR: 1%
-   Default layers: m = 30
-   Inflation layers: N = 15
-   Temperature: 1.0

## Results

TPR after attack:

-   GPT-2B: 0.05
-   Gemma-7B: 0.00
-   Mistral-7B: 0.01

## Structure

-   Break_Synth_ID.ipynb --- Main experiments
-   110_Google_s\_LLM_Watermarking\_(2).pdf --- Reference paper

## License

Research and educational use only.
