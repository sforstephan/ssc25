# Setup of the sensitivity analysis

This folder contains the documentation and results of a global sensitivity analysis for an agent-based model (ABM) in this repository.

The analysis focuses on identifying which model parameters most strongly influence key outcome variables such as effort, capability, evaluation, performance, informal resource, relative deprivation, motivation, and utility.

The **Morris method** implemented via `SALib` was used for the analysis. Simulations were executed in parallel and the outputs were stored in a PostgreSQL database.

## Folder Contents

- `sensitivity_setup.md`: Description of the experimental design, parameters, and methodology
- `sensitivity_results.md`: Results of the sensitivity analysis

## Analysis Summary

In the sensitivity analysis, 16 parameters were tested across 75 Morris trajectories (N = 75, levels = 4). Results show that:

- **[X Parameter]** had the strongest impact on [Y outcome]
- **Relative deprivation sensitivity** and **capability decay** were major drivers of performance variability
- Informal network structure (e.g., rewiring probability) had measurable but secondary effects

## Citation

If you use these results, please cite:

> [Your Name], “Sensitivity Analysis of Organizational ABM with Similarity-Based Informal Networks,” [Conference/Paper Name], 2025.
