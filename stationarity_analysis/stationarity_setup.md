# Stabilization Analysis

## Objective

This analysis investigates when the simulation outputs stabilize both over time and across repetitions. The goal is to identify:

1. **The minimum number of time steps** required before the output reaches a steady state.
2. **The number of repetitions** needed to obtain reliable aggregate statistics.

## Time Series Stabilization (Over Steps)

### Method

To determine when the system reaches a stable state, we perform a **Phillips–Perron (PP) test** for stationarity on each output metric. The test is applied on time series averaged across agents (for each run), using a moving window approach.

- **Test used**: Phillips–Perron (trend-stationarity, test type = `rho`)
- **Data**: Agent-level output, averaged across agents within each step and run.
- **Window size**: 600 steps  
- **Step size**: 100 steps  
- **Stationarity criterion**: The earliest step where the PP test detects stationarity and it persists until step 4000.

## Repetition-Based Stability (Across Runs)

### Method

Once the stable time window is identified, we assess how many **independent simulation runs** are needed to obtain reliable estimates of each output metric. We use the **coefficient of variation (CV)** across increasing numbers of runs:

$CV = \frac{\sigma}{\mu}$

Where:
- $\mu$: mean of the metric across runs  
- $\sigma$: standard deviation across runs  
- CV$: normalized dispersion of the output values

We track how the CV evolves as we increase the number of runs $n$, using the stabilized time window only.

### Comparison Approach

To determine whether a particular number of runs $n$ is sufficient, we compute:


$\Delta CV = |CV_{n} - CV_{n+\delta}|$


Where:
- $CV_{n}$ is the CV computed using $n$ runs
- $CV_{n+\delta}$ is the CV using a larger number of runs 
- If $\Delta CV < \varepsilon$, the outcome is considered stable with $n$ repetitions

Typical thresholds:
- $\varepsilon = 0.005$
- $\delta = 25$

## Outputs Analyzed

The following metrics were evaluated for stabilization:

- Effort  
- Capability  
- Evaluation  
- Performance  
- Informal Resources  
- Motivation  
- Relative Deprivation  
- Utility  


## Parameters

## Parameter Overview

| Parameter Name | Notation | Description | Value |
|----------------|----------|-------------|--------|
| `resource_allocation_alpha` | $\alpha$ | Proportion of formal resources distributed based on evaluation (vs. equal sharing among subordinates) | 0.5 |
| `cost_of_effort_beta` | $\beta_c$ | Slope parameter in the logistic function linking motivation to cost of effort | 2 |
| `capability_growth_beta` | $\beta^{\text{cap}}$ | Weight placed on formal (vs. informal) resources in the learning process affecting capability growth | 0.5 |
| `cost_of_information_sharing` | $c^{\text{sharing}}_i$ | Fixed cost for agent $i$ when sharing informal resources with others | 0.1 |
| `informal_resources_sharing_fraction` | $\delta^{\text{informal}}$ | Fraction of informal resources an agent is willing to share in each time step | 0.1 |
| `informal_resources_depletion_rate` | $\delta_I$ | Depletion rate for informal resources | 0.05 |
| `formal_resources_depletion_rate` | $\delta_F$ | Depletion rate for formal resources | 0.6 |
| `capability_decay_gamma` | $\gamma^{\text{cap}}$ | Rate at which an agent’s capability decays over time | 0.05 |
| `capability_decay_k` | $\kappa^{\text{cap}}$ | Parameter determining how rapidly learning efficiency declines with increasing capability | 2 |
| `decay_factor_reciprocity` | $\kappa^{\text{RS}}$ | Decay factor for reciprocity scores over time | 0.05 |
| `delta_centrality`                 | $\delta^{\text{centrality}}$       | Scaling parameter controlling the influence of network centrality in evaluation bias              | 0.1 |
| `relative_deprivation_sensitivity` | $\lambda_{RD}$ | Sensitivity parameter for the effect of relative deprivation on motivation and effort | 5 |
| `resource_allocation_lambda` | $\lambda_f$ | Share of an agent’s formal resources allocated to subordinates in the formal hierarchy | 0.9 |
| `learning_effect_on_capability` | $\lambda_{\text{cap}}$ | Base learning rate determining how quickly capability increases given available resources | 0.1 |
| `number_agents` | $N$ | Number of employee agents | 50 |
| `average_subordinates` | $N_{\text{sub}}$ | Number of subordinates per manager | 6 |
| `effort_social_influence_weight` | $\omega$ | Weight placed on peers’ effort levels in the social influence component of effort updates | 0.05 |
| `decay_factor_reciprocity` | $\rho$ | Decay factor for reciprocity scores (reused from above) | 0.05 |
| `root_resources` | $R_{\text{root}}$ | Resources of root agent that are further allocated to subordinates | 100 |
| `incentive_update_interval` | $T_{\mathcal{I}}$ | Time steps between incentive updates | 5 |
| `similarity_scaling_factor` | $\theta^{\text{similarity}}$ | Scaling factor for Jaccard similarity in informal network creation | 2.5 |
| `relative_deprivation_threshold` | $\theta_{RD}$ | Threshold beyond which relative deprivation significantly reduces motivation | 0.5 |





## Outputs Analyzed
The following agent-level metrics are analyzed to assess stabilization:
- Effort
- Capability
- Evaluation
- Performance
- Informal Resources
- Motivation
- Relative Deprivation
- Utility

Each metric is averaged across agents for each time step and analyzed for stabilization trends using the CV.

## Simulation Infrastructure

- 200 simulation runs
- 4000 time steps per run
- Data saved as Parquet files:



