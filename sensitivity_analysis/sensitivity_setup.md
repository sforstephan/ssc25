# Sensitivity Analysis Setup

## Objective

To identify which model parameters most influence individual-level and system-level outcomes in an agent-based model of organizational dynamics with similarity-based informal networks.

## Method

- **Analysis type**: Global sensitivity analysis using the **Morris method**
- **Tool**: `SALib` (`morris.sample` and `morris.analyze`)
- **Trajectories (N)**: 75
- **Steps per simulation**: 2400 (based on stationarity analysis)

## Parameters Varied (16 total)

### Morris Sensitivity Analysis – Parameter Ranges

| Parameter Name | Notation | Description | Range |
|----------------|----------|-------------|--------|
| `number_agents` | $N$ | Number of agents in the simulation | 20 – 60 |
| `learning_effect_on_capability` | $\lambda_{\text{cap}}$ | Weight of resource-based learning in capability update | 0.05 – 0.3 |
| `feedback_effect_on_effort` | — | Strength of effort adjustment based on feedback | 0.1 – 0.5 |
| `capability_growth_beta` | $\beta^{\text{cap}}$ | Weighting of formal vs. informal learning in capability updates | 0.1 – 1.0 |
| `capability_decay_gamma` | $\gamma^{\text{cap}}$ | Relative decay of capability over time | 0.01 – 0.2 |
| `effort_social_influence_weight` | $\omega$ | Weight of peer influence on effort | 0.01 – 0.2 |
| `resource_allocation_alpha` | $\alpha$ | Importance of performance in resource allocation (vs. equal share) | 0.1 – 1.0 |
| `resource_allocation_lambda` | $\lambda_f$ | Fraction of resources passed down the formal hierarchy | 0.1 – 0.9 |
| `informal_resources_sharing_fraction` | $\delta^{\text{informal}}$ | Fraction of informal resources eligible for sharing | 0.05 – 0.3 |
| `formal_resources_depletion_rate` | $\delta_F$ | Depletion rate of formal resources per step | 0.3 – 0.8 |
| `informal_resources_depletion_rate` | $\delta_I$ | Depletion rate of informal resources per step | 0.01 – 0.4 |
| `decay_factor_reciprocity` | $\kappa^{\text{RS}}$ | Rate at which reciprocity decays in informal ties | 0.01 – 0.2 |
| `relative_deprivation_threshold` | $\theta_{RD}$ | Threshold where RD begins to affect motivation and effort | 0.3 – 0.7 |
| `relative_deprivation_sensitivity` | $\lambda_{RD}$ | Steepness of the RD effect curve | 5 – 15 |
| `similarity_scaling_factor` | $\theta^{\text{similarity}}$ | Controls link probability in similarity-based informal network | 1 – 4 |
| `rewiring_probability` | — | Probability of rewiring informal network links | 0.01 – 0.2 |


Fixed parameters in this analysis: 

| Parameter Name | Notation | Description | Value |
|----------------|----------|-------------|--------|
| `cost_of_effort_beta` | $\beta_c$ | Slope parameter in the logistic function linking motivation to cost of effort | 2 |
| `capability_decay_k` | $\kappa^{\text{cap}}$ | Parameter determining how rapidly learning efficiency declines with increasing capability | 2 |
| `relative_deprivation_threshold` | $\theta_{RD}$ | Threshold beyond which relative deprivation significantly reduces motivation | 0.5 |
| `relative_deprivation_sensitivity` | $\lambda_{RD}$ | Steepness of the RD effect curve | 5 |
| `incentive_update_interval` | $T_{\mathcal{I}}$ | Time steps between incentive updates | 5 |
| `root_resources` | $R_{\text{root}}$ | Resources of root agent that are further allocated to subordinates | 100 |



## Outputs Analyzed

We computed Morris indices for the following outcome variables (averaged across all agents and time):

- **Effort**
- **Capability**
- **Evaluation**
- **Performance**
- **Informal Resources**
- **Motivation**
- **Relative Deprivation**
- **Utility**

## Simulation Infrastructure

- ABM implemented in Python using Mesa
- Results stored in PostgreSQL
- Simulations run in parallel using multiprocessing
- Data post-processed and exported to Excel


