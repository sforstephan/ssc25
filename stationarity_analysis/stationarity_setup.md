# Time Step Stabilization Analysis

## Objective

The objective of this analysis is to determine the number of time steps required until the outputs of the simulation model stabilize. Stabilization refers to the point after which key outcome metrics show only minimal fluctuations, indicating that the system has reached a steady state. This information helps reduce unnecessary computation in future experiments by avoiding overly long simulations.

## Method

To assess stabilization, we rely on the **coefficient of variation (CV)** computed over moving windows of simulation output. The CV is defined as:

\[
CV = \frac{\sigma}{\mu}
\]

Where \(\sigma\) is the standard deviation and \(\mu\) is the mean of the time series within the window. A smaller CV indicates less variability, suggesting that the output is stabilizing.

The analysis uses the following approach:
- Simulate the model for a long time horizon (4000 steps).
- Compute the mean of each outcome variable at each step across 200 runs.
- Slide a window (default size = 600, step size = 100) over the time series.
- Calculate the CV within each window.
- Identify the earliest window where CV drops below a predefined threshold (e.g., 0.05) and remains below it until the end.

## Parameters

### Full Parameter Table

## Parameter Overview

| Parameter Name | Notation | Description | Value |
|----------------|----------|-------------|--------|
| `resource_allocation_alpha` | $\alpha$ | Proportion of formal resources distributed based on evaluation (vs. equal sharing among subordinates) | 0.5 |
| `cost_of_effort_beta` | $\beta_c$ | Slope parameter in the logistic function linking motivation to cost of effort | 2 |
| `capability_growth_beta` | $\beta^{\text{cap}}$ | Weight placed on formal (vs. informal) resources in the learning process affecting capability growth | 0.5 |
| `cost_of_information_sharing` | $c^{\text{sharing}}_i$ | Fixed cost for agent $i$ when sharing informal resources with others | 0.1 |
| `centrality_in_evaluation` | $\delta^{\text{centrality}}$ | Scaling parameter controlling the influence of network centrality in evaluation bias | Enabled (True) |
| `informal_resources_sharing_fraction` | $\delta^{\text{informal}}$ | Fraction of informal resources an agent is willing to share in each time step | 0.1 |
| `informal_resources_depletion_rate` | $\delta_I$ | Depletion rate for informal resources | 0.05 |
| `formal_resources_depletion_rate` | $\delta_F$ | Depletion rate for formal resources | 0.6 |
| `capability_decay_gamma` | $\gamma^{\text{cap}}$ | Rate at which an agent’s capability decays over time | 0.05 |
| `capability_decay_k` | $\kappa^{\text{cap}}$ | Parameter determining how rapidly learning efficiency declines with increasing capability | 2 |
| `decay_factor_reciprocity` | $\kappa^{\text{RS}}$ | Decay factor for reciprocity scores over time | 0.05 |
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
| `centrality_in_evaluation` | $\theta^{\text{centrality}}$ | Scaling factor for the effect of the network centrality in the evaluation of agents | Enabled (True) |
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



