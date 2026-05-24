# AI Workload Acceleration through Semantic-Preserving Hardware Generation

This repository contains materials for the RAW 2026 PhD Forum work on compiler-driven hardware generation for AI workloads on reconfigurable platforms.

![RAW 2026 PhD Forum Poster](Poster%20RAW-2026%20PhD%20Forum.png)

## Authors

- Md Mahfuzul Haque  
- Md Rubel Ahmed  
- Louisiana Tech University

## Project Motivation

Demand for workload-aware accelerators is rapidly increasing, but hand-crafted RTL requires deep microarchitectural expertise.  
This project studies how to generate efficient RTL from high-level workload descriptions while preserving semantic structure across compiler lowering stages.

## Central Research Question

How can a hardware compiler preserve high-level AI workload semantics while progressively lowering designs into efficient, resource-aware spatial implementations for reconfigurable heterogeneous SoCs?

## Methodology

The work compares two RTL generation paths:

1. **Compiler-driven flow**  
   `Allo / torch.fx -> Allo-MLIR -> CIRCT dialects -> Calyx IR -> .sv`
2. **LLM-driven flow**  
   `Prompt -> GPT/Gemini -> RTL -> syntax check -> simulation -> QoR analysis`

The compiler flow emphasizes semantic-preserving transformations, explicit scheduling, and optimization passes throughout lowering.

## Key Findings

Across reported benchmarks, the compiler-driven flow outperforms LLM-only RTL generation:

- Up to **1.7x higher Fmax** vs ChatGPT
- Up to **75% fewer LUTs** vs ChatGPT
- Up to **1.4x higher Fmax** vs Gemini
- Up to **50% fewer LUTs** vs Gemini

## Why the Compiler Flow Performs Better

- Preserves high-level dataflow during lowering
- Applies explicit scheduling and optimization passes
- Supports resource-aware design-space exploration (tiling, unrolling, pipelining, memory banking, precision)

## Future Directions

- Push-button HLS for synthesizable accelerator generation from high-level workload specs
- LLM-assisted front-end support (pragma suggestions, debugging, design hints)
- Modular verification and stronger downstream QoR feedback loops

## Repository Assets

- `From Algotithm to RTL.pdf` — paper manuscript
- `IPDPS_PhD_Forum.pdf` — abstract/submission document
- `Poster RAW-2026 PhD Forum.pptx` — forum poster

## Citation

If you use this work, please cite the corresponding paper once the final bibliographic entry is available.
