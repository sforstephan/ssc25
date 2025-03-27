# Setup of the sensitivity analysis

This folder contains the documentation and results of a global sensitivity analysis for an agent-based model (ABM) in this repository.

The analysis focuses on identifying which model parameters most strongly influence key outcome variables such as effort, capability, evaluation, performance, informal resource, relative deprivation, motivation, and utility.

The **Morris method** implemented via `SALib` was used for the analysis. Simulations were executed in parallel and the outputs were stored in a PostgreSQL database.

## Folder Contents

- `sensitivity_setup.md`: Description of the experimental design, parameters, and methodology
- `sensitivity_results.md`: Results of the sensitivity analysis

## Analysis Summary

In the sensitivity analysis, 16 parameters were tested across 75 Morris trajectories (`N = 75`, `levels = 4`). Results show that:

- **`capability_decay_gamma`** had the strongest and most consistent impact across multiple outcomes, including **Capability**, **Effort**, **Evaluation**, **Performance**, and **Utility**.
- **`resource_allocation_lambda`** was another dominant driver, significantly influencing **Effort**, **Evaluation**, **Performance**, **Motivation**, **Relative Deprivation**, and **Utility**.
- **`capability_growth_beta`** also showed strong influence on **Capability**, **Effort**, **Evaluation**, **Performance**, **Motivation**, and **Utility**.
- **`number_agents`** meaningfully affected **Evaluation**, **Performance**, **Utility**, and **Effort**.
- **`informal_resources_sharing_fraction`** had a substantial impact on **Informal Resources**, and also influenced **Effort**, **Evaluation**, **Performance**, and **Utility** to a lesser extent.
- **`relative_deprivation_threshold`** and **`relative_deprivation_sensitivity`** were key behavioral parameters affecting **Motivation**, with `threshold` also impacting **Utility** and **Performance**.





