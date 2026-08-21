# Autocorrelation / Seasonal Autocorrelation Visualizer

An interactive tool for building intuition about the autocorrelation coefficient (ACF) in time series analysis.
Objective : Help self-learners to develop an intuition of how ACF behave and their possible interpretation.
Based on the book Forecasting Principles and Practices 3rd edition by Rob J Hyndman and George Athanasopoulos.
Programming Language associated (but interpretation remains the same) : R programming.


## Disclaimer
Initial implementation was generated with the assistance of an AI for HTML coding and then humanely reviewed and revised for statistical correctness.
Any correction or addition is very welcome. 

## Overview

The autocorrelation coefficient is a crucial tool in time series analysis, but its practical meaning may not always be intuitive from the formula alone, therefore this tool enables you to manipulate the coefficients directly and observe its effect on a simulated series, its lag-1 scatter plot, and its full autocorrelation profile across multiple lags.
The simulations are AR(1) processes (for acf1) and seasonal AR processes at lag 4 (for season_acf1), both scaled to unit variance so that series remain visually comparable across settings. The tool distinguishes between the true coefficient set by the user and the coefficient estimated from the simulated sample, which illustrates sampling variability directly rather than treating the autocorrelation coefficient as a fixed, deterministic quantity.
Developed as a study aid alongside the autocorrelation material in *Forecasting: Principles and Practice* (Hyndman & Athanasopoulos, FPP3).

## Features

  - Interactive slider for acf1, with four labeled presets (strong persistence, white noise, oscillation, moderate)
  - Adjustable sample size (n = 60, 120, 240) to show how estimation precision changes with sample length
  - Resample control to redraw a new series for a fixed true coefficient, illustrating estimation variance
  - Lag-1 scatter plot with a fitted least-squares line, whose slope corresponds to the estimated coefficient
  - Full ACF profile across lags 1 to 10, showing both the sample estimate and the theoretical value (acf1^k) for comparison
  - 95 percent significance band for a white-noise process, so bars within the band are not statistically distinguishable from no autocorrelation
  - Separate module for seasonal memory (season_acf1) at lag 4, using a seasonal AR process rather than a periodic deterministic signal

## Usage

The tool runs entirely in the browser as static HTML but is also available locally using the following command :

```bash
git clone https://github.com/AirportSource/autocorrelation-visualizer.git
cd autocorrelation-visualizer
open index.html
```
