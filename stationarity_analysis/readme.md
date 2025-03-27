# Setup of the stationarity analysis

This folder contains documentation and results of a stationarity analysis for the agent-based model (ABM) in this repository. The analysis investigates whether key output metrics from the simulation stabilize over time and how many simulation runs are required to ensure robust average outcomes.

Two complementary analyses were conducted:

- **Step-based stationarity analysis**: Determines how many simulation time steps are required before output metrics become stationary.
- **Run-based stability analysis**: Assesses how many repetitions (i.e., simulation runs) are needed to produce stable average results using the coefficient of variation (CV).

## Folder contents

- `stationarity_setup.md`: Description of the method and experimental setup
- `stationarity_results_steps.xlsx`: Stationarity results over time steps (Phillips-Perron test)
- `stationarity_results_runs.xlsx`: Run-based stability results (coefficient of variation)

## Analysis summary

### Time Step Stabilization

To determine how many time steps are required before model dynamics stabilize, a **Phillips-Perron (PP)** unit root test was applied to sliding windows (600 steps, step size = 100) over the average time series for each output metric.

- A metric was considered **stationary** if the PP test rejected the null hypothesis of a unit root at the 5% level.
- Results show that most output metrics become stationary at around **step 2300**.
- Therefore, subsequent analyses used **2400 simulation steps** per run to ensure a stable time window.

### Repetition Robustness

To assess how many simulation runs are necessary for stable averages, the **coefficient of variation (CV)** was calculated for increasing numbers of runs.

- The CV is defined as $CV = \frac{\sigma}{\mu}$ and reflects the relative variability across repetitions.
- The analysis showed that from **75 runs onwards**, the CV falls below a predefined stability threshold for all core metrics.
- As a result, **75 runs** were selected as the baseline for scenario experiments and sensitivity analysis.


