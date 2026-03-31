# Code for: "Order matters: Autocorrelation of temperature dictates extinction risk in populations with nonlinear thermal performance"
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17728683.svg)](https://doi.org/10.5281/zenodo.17728683)

Forecasting the risks caused by climate change often relies upon combining species' thermal performance curves with expected statistical distributions of experienced temperatures, without consideration for the order in which those temperatures occur. Such averaging approaches may obscure the disproportionate impacts that extreme events like heatwaves have on fitness and survival. In this study, we instead incorporate thermal performance curves with population dynamical modeling to elucidate the relationship between the sequence of temperature events -- driven by temporal autocorrelation -- and extinction risk. We show that the permutation of temperatures determines the extent of risk; as thermal regimes grow warmer, more variable, and more autocorrelated, the risk of extinction grows non-linearly and is driven by interactions between the thermal distribution and its temporal autocorrelation. Given that the mean, variance, and autocorrelation of temperatures are changing in nuanced ways across the globe, understanding these interactions is paramount for forecasting risk. Using empirical data from a benchmarked set of thermal performance curves, we demonstrate how extinction risk is impacted by the change in mean, variance, and autocorrelation, while controlling for seasonal and diurnal cycling. Our results and modeling approach offer new tools for testing the robustness of thermal performance curves and emphasize the importance of looking beyond temporally-blind metrics, like mean population size or average thermal distributions, for forecasting impending extinction risks.

Required data to run all code is available for download at [https://doi.org/10.5061/dryad.w0vt4b91q](https://doi.org/10.5061/dryad.w0vt4b91q).

Initial release 2024-07; revised 2025-07; revised 2025-11

## Sections

### Additional Figures
This file contains code to generate all background figures not incorporated with the other models. Run to generate Figures 1 & 2.


### Model 1: Effects of Autocorrelation Across the Thermal Landscape
This model simulates the population dynamics of a logistically growing population with either a generalist or a specialist TPC experiencing different mean and standard deviations of temperatures across various levels of temporal autocorrelation. Outputs: extinction times for every parameter set.

Run 'Model1.nb' to generate outputs 'extTime_TPC_tmax_dims.m'
- 'TPC': either not included (temperate TPC) or 'trop_' (tropical TPC). Temperate must be run to generate Figs 4 and 5, tropical must be run to generate Figs A5 and A6.
- 'tmax': the number of timesteps included the simualations; default is 'tmax2000'
- 'dims': the dimensions of the output matrix (number of spectral exponents, mean temperatures, stdevs of temperatures, and simulation replications); default is 'dims21,7,7,1000'

Run 'Model1_plotting.nb' to generate Figure 3.


### Model 1.2: Comparing Risk Metrics
This model simulations the population dynamics of a logistically growing population with either a generalist or a specialist TPC experiencing different mean temperatures across various levels of temporal autocorrelation. Outputs: squence of population sizes and extinction times for every parameter set.

Run 'Model1.2_abundance.nb' to generate outputs 'extMetrics8_TPC_outputtype_tmax_dims.m'
- 'TPC': either not included (temperate TPC) or 'trop_' (tropical TPC). Both versions must be run to plot Fig 3.
- 'outputtype': for each run, will generate 'extTime' with the timestep of extinction from each run and 'popSize' with the population size at each timestep from each run
- 'tmax': the number of timesteps included the simualations; default is 'tmax2000'
- 'dims': the dimensions of the output matrix (number of spectral exponents, mean temperatures, stdevs of temperatures, and simulation replications); default is 'dims21,4,1,1000'

Run 'Model1.2_abundance_plotting.nb' to generate Figure 4.


### Model 2: Impacts of Autocorrelation on Global Risk Assessments
This model simulates the population dynamics of a logistically growing population with one of 38 empirical invetebrate TPCs experiencing historical (1994-2003) or recent (2014-2023) observed temperature regimes across various levels of temporal autocorrelation and realistic diurnal and seasonal cycles. Outputs: extinction times and minimum population size for every parameter set for each organism (Figure 6).

Inputs: This model requires downloaded files (species data) and (temperature data).
Run 'Model2.nb' to generate outputs 'model3_species_timeperiod_extthreshold.m'
- 'species': the scientific name of each species
- 'timeperiod': the tested time period; either historical ('1994-01-01to2003-12-31') or present ('2014-01-01to2023-12-31')
- 'extthreshold': the extinction threshold used during the run; default is 'ext1'

Run 'Model2_plotting.nb' to generate Figs 5 (and extended figs).


### Other files
For any users who do not have access to _Mathematica_, all files are additionally available to view as pdfs and 'autocorrelationstarter.Rmd' contains all the essential functions translated to _R_ (including TPCs, population dynamics, spectral synthesis, spectral mimicry, and seasonal detrending).


## References

Robey, A.J. and Vasseur, D.A. (2026). [Order matters: Autocorrelation of temperatures dictates extinction risk in populations with nonlinear thermal performance](https://doi.org/10.1002/ecy.70325). Ecology 107(3): e70325.
