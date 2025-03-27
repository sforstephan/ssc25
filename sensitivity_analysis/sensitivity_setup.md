# Sensitivity Analysis Setup

## Objective

To identify which model parameters most influence individual-level and system-level outcomes in an agent-based model of organizational dynamics with similarity-based informal networks.

## Method

- **Analysis type**: Global sensitivity analysis using the **Morris method**
- **Tool**: `SALib` (`morris.sample` and `morris.analyze`)
- **Trajectories (N)**: 75
- **Steps per simulation**: 2400 (based on stationarity analysis)

## Parameters Varied (16 total)

### 📊 Morris Sensitivity Analysis – Parameter Ranges

| Parameter | Description | Range |
|----------|-------------|-------|
| `number_agents` | Number of agents in the simulation | 20 – 60 |
| `learning_effect_on_capability` | Weight of resource-based learning in capability update | 0.05 – 0.3 |
| `feedback_effect_on_effort` | Strength of effort adjustment based on feedback | 0.1 – 0.5 |
| `capability_growth_beta` | Weighting of formal vs. informal learning in capability updates | 0.1 – 1.0 |
| `capability_decay_gamma` | Relative decay of capability over time | 0.01 – 0.2 |
| `effort_social_influence_weight` | Weight of peer influence on effort | 0.01 – 0.2 |
| `resource_allocation_alpha` | Importance of performance in resource allocation (vs. equal share) | 0.1 – 1.0 |
| `resource_allocation_lambda` | Fraction of resources passed down the formal hierarchy | 0.1 – 0.9 |
| `informal_resources_sharing_fraction` | Fraction of informal resources eligible for sharing | 0.05 – 0.3 |
| `formal_resources_depletion_rate` | Depletion rate of formal resources per step | 0.3 – 0.8 |
| `informal_resources_depletion_rate` | Depletion rate of informal resources per step | 0.01 – 0.4 |
| `decay_factor_reciprocity` | Rate at which reciprocity decays in informal ties | 0.01 – 0.2 |
| `relative_deprivation_threshold` | Threshold where RD begins to affect motivation and effort | 0.3 – 0.7 |
| `relative_deprivation_sensitivity` | Steepness of the RD effect curve | 5 – 15 |
| `similarity_scaling_factor` | Controls link probability in similarity-based informal network | 1 – 4 |
| `rewiring_probability` | Probability of rewiring informal network links | 0.01 – 0.2 |


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

## Results

Table 1
