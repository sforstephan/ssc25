# Results of the sensitivity analysis

This document presents the results of a Morris sensitivity analysis conducted on the agent-based model included in this repository. The analysis focuses on understanding how key behavioral, structural, and network-related parameters influence emergent outcomes across several core metrics: **Capability**, **Effort**, **Evaluation**, **Performance**, **Informal Resources**, **Motivation**, **Relative Deprivation**, and **Utility**.

For each metric, we report the **mean absolute effect (Mu\*)**, the **standard deviation (Sigma)** indicating potential non-linear or interaction effects, the **raw mean effect (Mu)**, and the **confidence interval** for Mu\*. Parameters with a Mu\* value greater than **0.15** are highlighted with a ⭐ to indicate a substantial influence on the corresponding outcome.

Each table below summarizes the top drivers for a given metric and helps identify which mechanisms are most impactful in shaping agent behavior and systemic outcomes in the simulated organization.


## Capability


| ⭐ | Parameter | Description | Mu\* | Sigma | Mu | Mu\* ± Conf. |
|----|-----------|-------------|------|--------|-------|-------------|
| ⭐ | `capability_decay_gamma` | Relative decay of capability over time | 0.5323 | 0.2585 | -0.5323 | ± 0.0582 |
| ⭐ | `capability_growth_beta` | Weighting of formal vs. informal learning in capability updates | 0.3532 | 0.1901 | -0.3532 | ± 0.0386 |
|  | `resource_allocation_lambda` | Fraction of resources passed down the formal hierarchy | 0.1326 | 0.1892 | 0.1320 | ± 0.0404 |
|  | `number_agents` | Number of agents in the simulation | 0.0478 | 0.0876 | 0.0066 | ± 0.0177 |
|  | `resource_allocation_alpha` | Importance of performance in resource allocation (vs. equal share) | 0.0224 | 0.0631 | 0.0205 | ± 0.0148 |
|  | `formal_resources_depletion_rate` | Depletion rate of formal resources per step | 0.0143 | 0.0242 | -0.0005 | ± 0.0047 |
|  | `relative_deprivation_sensitivity` | Steepness of the RD effect curve | 0.0097 | 0.0210 | 0.0001 | ± 0.0041 |
|  | `informal_resources_sharing_fraction` | Fraction of informal resources eligible for sharing | 0.0091 | 0.0178 | -0.0002 | ± 0.0033 |
|  | `decay_factor_reciprocity` | Rate at which reciprocity decays in informal ties | 0.0083 | 0.0138 | 0.0004 | ± 0.0023 |
|  | `informal_resources_depletion_rate` | Depletion rate of informal resources per step | 0.0079 | 0.0210 | 0.0005 | ± 0.0040 |
|  | `relative_deprivation_threshold` | Threshold where RD begins to affect motivation and effort | 0.0074 | 0.0131 | 0.0005 | ± 0.0020 |
|  | `rewiring_probability` | Probability of rewiring informal network links | 0.0067 | 0.0105 | 0.0013 | ± 0.0019 |
|  | `feedback_effect_on_effort` | Strength of effort adjustment based on feedback | 0.0064 | 0.0105 | 0.0007 | ± 0.0020 |
|  | `learning_effect_on_capability` | Weight of resource-based learning in capability update | 0.0063 | 0.0094 | 0.0002 | ± 0.0015 |
|  | `similarity_scaling_factor` | Controls link probability in similarity-based informal network | 0.0063 | 0.0086 | 0.0000 | ± 0.0012 |
|  | `effort_social_influence_weight` | Weight of peer influence on effort | 0.0057 | 0.0087 | -0.0003 | ± 0.0014 |


## Effort

| ⭐ | Parameter | Description | Mu\* | Sigma | Mu | Mu\* ± Conf. |
|----|-----------|-------------|------|--------|-------|-------------|
| ⭐ | `resource_allocation_lambda` | Fraction of resources passed down the formal hierarchy | 0.4006 | 0.2880 | 0.3987 | ± 0.0598 |
| ⭐ | `capability_decay_gamma` | Relative decay of capability over time | 0.3254 | 0.2260 | -0.3250 | ± 0.0436 |
| ⭐ | `capability_growth_beta` | Weighting of formal vs. informal learning in capability updates | 0.3018 | 0.2527 | -0.2981 | ± 0.0537 |
| ⭐ | `number_agents` | Number of agents in the simulation | 0.1740 | 0.1763 | -0.1149 | ± 0.0298 |
|  | `formal_resources_depletion_rate` | Depletion rate of formal resources per step | 0.1451 | 0.1421 | -0.1426 | ± 0.0328 |
|  | `informal_resources_sharing_fraction` | Fraction of informal resources eligible for sharing | 0.1320 | 0.1354 | 0.1251 | ± 0.0331 |
|  | `resource_allocation_alpha` | Importance of performance in resource allocation (vs. equal share) | 0.1027 | 0.1484 | 0.0895 | ± 0.0307 |
|  | `relative_deprivation_threshold` | Threshold where RD begins to affect motivation and effort | 0.0680 | 0.0637 | 0.0621 | ± 0.0122 |
|  | `relative_deprivation_sensitivity` | Steepness of the RD effect curve | 0.0496 | 0.0667 | 0.0229 | ± 0.0104 |
|  | `similarity_scaling_factor` | Controls link probability in similarity-based informal network | 0.0491 | 0.0713 | -0.0054 | ± 0.0112 |
|  | `decay_factor_reciprocity` | Rate at which reciprocity decays in informal ties | 0.0467 | 0.0711 | 0.0133 | ± 0.0118 |
|  | `effort_social_influence_weight` | Weight of peer influence on effort | 0.0439 | 0.0560 | -0.0192 | ± 0.0089 |
|  | `informal_resources_depletion_rate` | Depletion rate of informal resources per step | 0.0399 | 0.0552 | 0.0030 | ± 0.0097 |
|  | `learning_effect_on_capability` | Weight of resource-based learning in capability update | 0.0394 | 0.0524 | 0.0017 | ± 0.0080 |
|  | `rewiring_probability` | Probability of rewiring informal network links | 0.0392 | 0.0597 | 0.0057 | ± 0.0101 |
|  | `feedback_effect_on_effort` | Strength of effort adjustment based on feedback | 0.0377 | 0.0538 | 0.0011 | ± 0.0086 |


## Evaluation

| ⭐ | Parameter | Description | Mu\* | Sigma | Mu | Mu\* ± Conf. |
|----|-----------|-------------|------|--------|-------|-------------|
| ⭐ | `capability_decay_gamma` | Relative decay of capability over time | 0.7039 | 0.4603 | -0.7039 | ± 0.0982 |
| ⭐ | `resource_allocation_lambda` | Fraction of resources passed down the formal hierarchy | 0.5716 | 0.3188 | 0.5716 | ± 0.0769 |
| ⭐ | `capability_growth_beta` | Weighting of formal vs. informal learning in capability updates | 0.3440 | 0.2552 | -0.3399 | ± 0.0555 |
| ⭐ | `formal_resources_depletion_rate` | Depletion rate of formal resources per step | 0.3144 | 0.2319 | -0.3072 | ± 0.0543 |
| ⭐ | `number_agents` | Number of agents in the simulation | 0.2878 | 0.2355 | -0.2309 | ± 0.0378 |
| ⭐ | `informal_resources_sharing_fraction` | Fraction of informal resources eligible for sharing | 0.1523 | 0.1577 | 0.1275 | ± 0.0321 |
|  | `resource_allocation_alpha` | Importance of performance in resource allocation (vs. equal share) | 0.1114 | 0.1810 | 0.0576 | ± 0.0350 |
|  | `similarity_scaling_factor` | Controls link probability in similarity-based informal network | 0.0860 | 0.1137 | -0.0087 | ± 0.0170 |
|  | `decay_factor_reciprocity` | Rate at which reciprocity decays in informal ties | 0.0857 | 0.1132 | 0.0078 | ± 0.0155 |
|  | `relative_deprivation_sensitivity` | Steepness of the RD effect curve | 0.0844 | 0.1063 | 0.0139 | ± 0.0146 |
|  | `informal_resources_depletion_rate` | Depletion rate of informal resources per step | 0.0808 | 0.1077 | 0.0096 | ± 0.0170 |
|  | `rewiring_probability` | Probability of rewiring informal network links | 0.0794 | 0.1020 | 0.0086 | ± 0.0122 |
|  | `relative_deprivation_threshold` | Threshold where RD begins to affect motivation and effort | 0.0773 | 0.0969 | 0.0312 | ± 0.0150 |
|  | `learning_effect_on_capability` | Weight of resource-based learning in capability update | 0.0769 | 0.1029 | -0.0123 | ± 0.0160 |
|  | `effort_social_influence_weight` | Weight of peer influence on effort | 0.0765 | 0.0912 | -0.0269 | ± 0.0123 |
|  | `feedback_effect_on_effort` | Strength of effort adjustment based on feedback | 0.0721 | 0.0896 | 0.0086 | ± 0.0126 |

## Informal resources

| ⭐ | Parameter | Description | Mu\* | Sigma | Mu | Mu\* ± Conf. |
|----|-----------|-------------|------|--------|-------|-------------|
|  | `informal_resources_sharing_fraction` | Fraction of informal resources eligible for sharing | 0.9437 | 0.0389 | 0.9437 | ± 0.0093 |
|  | `capability_decay_gamma` | Relative decay of capability over time | 0.0328 | 0.0385 | -0.0269 | ± 0.0069 |
|  | `resource_allocation_lambda` | Fraction of resources passed down the formal hierarchy | 0.0303 | 0.0388 | 0.0219 | ± 0.0077 |
|  | `capability_growth_beta` | Weighting of formal vs. informal learning in capability updates | 0.0296 | 0.0343 | -0.0246 | ± 0.0073 |
|  | `number_agents` | Number of agents in the simulation | 0.0182 | 0.0259 | -0.0005 | ± 0.0042 |
|  | `formal_resources_depletion_rate` | Depletion rate of formal resources per step | 0.0151 | 0.0213 | -0.0072 | ± 0.0037 |
|  | `relative_deprivation_threshold` | Threshold where RD begins to affect motivation and effort | 0.0143 | 0.0191 | 0.0081 | ± 0.0036 |
|  | `similarity_scaling_factor` | Controls link probability in similarity-based informal network | 0.0140 | 0.0219 | 0.0008 | ± 0.0039 |
|  | `resource_allocation_alpha` | Importance of performance in resource allocation (vs. equal share) | 0.0139 | 0.0187 | 0.0044 | ± 0.0029 |
|  | `relative_deprivation_sensitivity` | Steepness of the RD effect curve | 0.0131 | 0.0181 | 0.0015 | ± 0.0029 |
|  | `rewiring_probability` | Probability of rewiring informal network links | 0.0122 | 0.0182 | 0.0008 | ± 0.0031 |
|  | `informal_resources_depletion_rate` | Depletion rate of informal resources per step | 0.0121 | 0.0169 | -0.0006 | ± 0.0024 |
|  | `feedback_effect_on_effort` | Strength of effort adjustment based on feedback | 0.0120 | 0.0165 | -0.0020 | ± 0.0027 |
|  | `decay_factor_reciprocity` | Rate at which reciprocity decays in informal ties | 0.0120 | 0.0183 | 0.0009 | ± 0.0034 |
|  | `learning_effect_on_capability` | Weight of resource-based learning in capability update | 0.0113 | 0.0198 | -0.0026 | ± 0.0039 |
|  | `effort_social_influence_weight` | Weight of peer influence on effort | 0.0098 | 0.0142 | -0.0001 | ± 0.0024 |


## Motivation

| ⭐ | Parameter | Description | Mu\* | Sigma | Mu | Mu\* ± Conf. |
|----|-----------|-------------|------|--------|-------|-------------|
| ⭐ | `relative_deprivation_threshold` | Threshold where RD begins to affect motivation and effort | 0.2823 | 0.0870 | 0.2823 | ± 0.0153 |
|  | `relative_deprivation_sensitivity` | Steepness of the RD effect curve | 0.1161 | 0.0738 | 0.1137 | ± 0.0172 |
|  | `resource_allocation_lambda` | Fraction of resources passed down the formal hierarchy | 0.1029 | 0.1182 | 0.0655 | ± 0.0193 |
|  | `capability_growth_beta` | Weighting of formal vs. informal learning in capability updates | 0.0989 | 0.0937 | -0.0872 | ± 0.0167 |
|  | `capability_decay_gamma` | Relative decay of capability over time | 0.0914 | 0.0937 | -0.0724 | ± 0.0152 |
|  | `informal_resources_sharing_fraction` | Fraction of informal resources eligible for sharing | 0.0560 | 0.0699 | 0.0397 | ± 0.0136 |
|  | `number_agents` | Number of agents in the simulation | 0.0560 | 0.0727 | -0.0190 | ± 0.0098 |
|  | `formal_resources_depletion_rate` | Depletion rate of formal resources per step | 0.0474 | 0.0622 | -0.0181 | ± 0.0106 |
|  | `resource_allocation_alpha` | Importance of performance in resource allocation (vs. equal share) | 0.0447 | 0.0649 | 0.0158 | ± 0.0106 |
|  | `similarity_scaling_factor` | Controls link probability in similarity-based informal network | 0.0425 | 0.0579 | 0.0015 | ± 0.0083 |
|  | `decay_factor_reciprocity` | Rate at which reciprocity decays in informal ties | 0.0374 | 0.0522 | 0.0010 | ± 0.0077 |
|  | `feedback_effect_on_effort` | Strength of effort adjustment based on feedback | 0.0367 | 0.0531 | -0.0012 | ± 0.0070 |
|  | `rewiring_probability` | Probability of rewiring informal network links | 0.0365 | 0.0492 | 0.0072 | ± 0.0072 |
|  | `learning_effect_on_capability` | Weight of resource-based learning in capability update | 0.0361 | 0.0515 | -0.0040 | ± 0.0080 |
|  | `effort_social_influence_weight` | Weight of peer influence on effort | 0.0349 | 0.0470 | 0.0015 | ± 0.0071 |
|  | `informal_resources_depletion_rate` | Depletion rate of informal resources per step | 0.0308 | 0.0411 | 0.0008 | ± 0.0061 |


## Performance

| ⭐ | Parameter | Description | Mu\* | Sigma | Mu | Mu\* ± Conf. |
|----|-----------|-------------|------|--------|-------|-------------|
| ⭐ | `capability_decay_gamma` | Relative decay of capability over time | 0.6976 | 0.4523 | -0.6976 | ± 0.1032 |
| ⭐ | `resource_allocation_lambda` | Fraction of resources passed down the formal hierarchy | 0.5924 | 0.3124 | 0.5906 | ± 0.0664 |
| ⭐ | `capability_growth_beta` | Weighting of formal vs. informal learning in capability updates | 0.3356 | 0.2486 | -0.3352 | ± 0.0519 |
| ⭐ | `formal_resources_depletion_rate` | Depletion rate of formal resources per step | 0.3036 | 0.2127 | -0.3033 | ± 0.0466 |
| ⭐ | `number_agents` | Number of agents in the simulation | 0.2821 | 0.2180 | -0.2387 | ± 0.0350 |
|  | `informal_resources_sharing_fraction` | Fraction of informal resources eligible for sharing | 0.1239 | 0.1309 | 0.1238 | ± 0.0298 |
|  | `resource_allocation_alpha` | Importance of performance in resource allocation (vs. equal share) | 0.0858 | 0.1550 | 0.0727 | ± 0.0317 |
|  | `relative_deprivation_threshold` | Threshold where RD begins to affect motivation and effort | 0.0515 | 0.0480 | 0.0439 | ± 0.0085 |
|  | `effort_social_influence_weight` | Weight of peer influence on effort | 0.0378 | 0.0433 | -0.0244 | ± 0.0076 |
|  | `similarity_scaling_factor` | Controls link probability in similarity-based informal network | 0.0364 | 0.0534 | -0.0030 | ± 0.0077 |
|  | `relative_deprivation_sensitivity` | Steepness of the RD effect curve | 0.0347 | 0.0516 | 0.0123 | ± 0.0101 |
|  | `decay_factor_reciprocity` | Rate at which reciprocity decays in informal ties | 0.0326 | 0.0546 | 0.0112 | ± 0.0105 |
|  | `learning_effect_on_capability` | Weight of resource-based learning in capability update | 0.0310 | 0.0427 | 0.0003 | ± 0.0065 |
|  | `informal_resources_depletion_rate` | Depletion rate of informal resources per step | 0.0301 | 0.0493 | 0.0058 | ± 0.0083 |
|  | `rewiring_probability` | Probability of rewiring informal network links | 0.0295 | 0.0448 | 0.0050 | ± 0.0075 |
|  | `feedback_effect_on_effort` | Strength of effort adjustment based on feedback | 0.0284 | 0.0406 | 0.0027 | ± 0.0070 |


## Relative deprivation

| ⭐ | Parameter | Description | Mu\* | Sigma | Mu | Mu\* ± Conf. |
|----|-----------|-------------|------|--------|-------|-------------|
|  | `resource_allocation_lambda` | Fraction of resources passed down the formal hierarchy | 0.1398 | 0.1415 | -0.1008 | ± 0.0233 |
|  | `capability_decay_gamma` | Relative decay of capability over time | 0.1337 | 0.1263 | 0.1156 | ± 0.0233 |
|  | `capability_growth_beta` | Weighting of formal vs. informal learning in capability updates | 0.1226 | 0.1154 | 0.1069 | ± 0.0211 |
|  | `informal_resources_sharing_fraction` | Fraction of informal resources eligible for sharing | 0.0813 | 0.0897 | -0.0475 | ± 0.0119 |
|  | `number_agents` | Number of agents in the simulation | 0.0758 | 0.0909 | 0.0253 | ± 0.0118 |
|  | `resource_allocation_alpha` | Importance of performance in resource allocation (vs. equal share) | 0.0698 | 0.0988 | -0.0323 | ± 0.0176 |
|  | `formal_resources_depletion_rate` | Depletion rate of formal resources per step | 0.0689 | 0.0815 | 0.0343 | ± 0.0129 |
|  | `relative_deprivation_threshold` | Threshold where RD begins to affect motivation and effort | 0.0541 | 0.0632 | -0.0310 | ± 0.0097 |
|  | `similarity_scaling_factor` | Controls link probability in similarity-based informal network | 0.0519 | 0.0675 | -0.0013 | ± 0.0095 |
|  | `decay_factor_reciprocity` | Rate at which reciprocity decays in informal ties | 0.0511 | 0.0687 | -0.0023 | ± 0.0115 |
|  | `feedback_effect_on_effort` | Strength of effort adjustment based on feedback | 0.0505 | 0.0676 | 0.0020 | ± 0.0092 |
|  | `informal_resources_depletion_rate` | Depletion rate of informal resources per step | 0.0487 | 0.0604 | -0.0010 | ± 0.0087 |
|  | `relative_deprivation_sensitivity` | Steepness of the RD effect curve | 0.0481 | 0.0599 | -0.0101 | ± 0.0081 |
|  | `rewiring_probability` | Probability of rewiring informal network links | 0.0469 | 0.0614 | -0.0061 | ± 0.0090 |
|  | `effort_social_influence_weight` | Weight of peer influence on effort | 0.0459 | 0.0560 | -0.0042 | ± 0.0072 |
|  | `learning_effect_on_capability` | Weight of resource-based learning in capability update | 0.0443 | 0.0557 | 0.0042 | ± 0.0086 |


## Utility

| ⭐ | Parameter | Description | Mu\* | Sigma | Mu | Mu\* ± Conf. |
|----|-----------|-------------|------|--------|-------|-------------|
| ⭐ | `capability_decay_gamma` | Relative decay of capability over time | 0.2089 | 0.1491 | -0.2039 | ± 0.0344 |
| ⭐ | `resource_allocation_lambda` | Fraction of resources passed down the formal hierarchy | 0.1916 | 0.1548 | 0.1718 | ± 0.0300 |
| ⭐ | `capability_growth_beta` | Weighting of formal vs. informal learning in capability updates | 0.1660 | 0.1291 | -0.1580 | ± 0.0268 |
|  | `number_agents` | Number of agents in the simulation | 0.0958 | 0.1266 | -0.0063 | ± 0.0177 |
|  | `formal_resources_depletion_rate` | Depletion rate of formal resources per step | 0.0893 | 0.1041 | -0.0498 | ± 0.0158 |
|  | `informal_resources_sharing_fraction` | Fraction of informal resources eligible for sharing | 0.0699 | 0.0808 | 0.0551 | ± 0.0163 |
|  | `resource_allocation_alpha` | Importance of performance in resource allocation (vs. equal share) | 0.0568 | 0.0854 | 0.0227 | ± 0.0180 |
|  | `relative_deprivation_threshold` | Threshold where RD begins to affect motivation and effort | 0.0489 | 0.0640 | 0.0161 | ± 0.0106 |
|  | `relative_deprivation_sensitivity` | Steepness of the RD effect curve | 0.0465 | 0.0569 | 0.0251 | ± 0.0083 |
|  | `informal_resources_depletion_rate` | Depletion rate of informal resources per step | 0.0462 | 0.0621 | 0.0079 | ± 0.0094 |
|  | `similarity_scaling_factor` | Controls link probability in similarity-based informal network | 0.0449 | 0.0638 | -0.0087 | ± 0.0098 |
|  | `feedback_effect_on_effort` | Strength of effort adjustment based on feedback | 0.0447 | 0.0562 | 0.0050 | ± 0.0080 |
|  | `effort_social_influence_weight` | Weight of peer influence on effort | 0.0439 | 0.0570 | -0.0100 | ± 0.0078 |
|  | `decay_factor_reciprocity` | Rate at which reciprocity decays in informal ties | 0.0436 | 0.0624 | 0.0113 | ± 0.0108 |
|  | `rewiring_probability` | Probability of rewiring informal network links | 0.0432 | 0.0582 | 0.0069 | ± 0.0092 |
|  | `learning_effect_on_capability` | Weight of resource-based learning in capability update | 0.0416 | 0.0608 | -0.0014 | ± 0.0098 |
