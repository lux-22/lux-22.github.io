---
layout: homepage
---

<div class="page-tabs">
  <a class="tab" href="{{ '/' | relative_url }}">Home</a>
  <a class="tab" href="{{ '/publications.html' | relative_url }}">Publications</a>
  <a class="tab active" href="{{ '/projects.html' | relative_url }}">Projects</a>
</div>

<h2>Projects</h2>

<small style="font-weight: normal;">These are personal projects pursued independently outside of work.</small>

<style>
  .project-image-row {
    display: grid;
    grid-template-columns: 1fr 1fr 1.2fr;
    gap: 14px;
    margin-top: 10px;
  }
  .project-image-row img {
    width: 100%;
    height: auto;
    border-radius: 8px;
    display: block;
  }
  .project-image-row .image-wide {
    grid-column: span 2;
  }
  .project-figure-row {
    display: flex;
    gap: 14px;
    align-items: flex-start;
    flex-wrap: wrap;
  }
  .project-figure {
    height: 180px;
    border-radius: 8px;
    overflow: hidden;
  }
  .project-figure img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    display: block;
  }
  .project-figure-cover img { object-fit: cover; }
  .project-figure-narrow { width: 25%; }
  .project-figure-wide { width: 40%; }
  .project-figure-full { width: 100%; }
  /* .project-figure-medium { width: 35%; } */
  @media (max-width: 820px) {
    .project-image-row { grid-template-columns: 1fr; }
    .project-figure { width: 100%; height: auto; }
    /* .project-figure img { height: auto; } */
  }
</style>

Built a prediction-markets research and trading stack spanning data engineering, machine learning, market microstructure, and automated execution.

### Research Pipeline for Weather Prediction Markets

Built a research pipeline for weather prediction markets, combining NOAA observations and forecasts with market data to train and evaluate ML models for daily temperature contracts. Focused on data ingestion, feature engineering, probabilistic modeling, and out-of-sample evaluation against market-implied baselines across multiple U.S. cities.

<!-- This project is the data engineering and research layer of a broader prediction-markets trading stack, with downstream work focused on market microstructure and execution. -->

Repository: <a href="https://github.com/lux-22/weather_prediction" target="_blank" rel="noopener">github.com/lux-22/weather_prediction</a>.

### Market Microstructure and Market-Making Research (under development)

Research project focused on live order book ingestion, inventory-aware quoting, and automated execution in prediction markets. Implements negative-risk logic and an Avellaneda-Stoikov-style market-making framework to study market microstructure and event-driven trading systems.

Repository: <a href="https://github.com/lux-22/kpmm" target="_blank" rel="noopener">github.com/lux-22/kpmm</a>.

### Automated Execution System for Prediction Markets

Execution-focused trading system for submitting batched one-shot orders in prediction markets. Developed as an operational layer for model- or strategy-driven trades, with server deployment, cron-based scheduling, and configurable order generation for automated runs.

Repository: <a href="https://github.com/lux-22/autotrade" target="_blank" rel="noopener">github.com/lux-22/autotrade</a>.

<!--
### Weather Prediction Markets

Developed machine learning models for weather forecasting. Built a multi-source dataset 
joining NOAA observations and weather forecasts to predict daily maximum temperature. 
Implemented statistical analyses and ML pipelines with out-of-sample validation and 
automated trading integration.

### Market Making for Prediction Markets

Building an algorithmic trading system for prediction markets: stochastic optimization for
quoting strategies, async market data feeds, and event-driven backtesting infrastructure.
-->

<!--
### AI for science

Coming soon.

### Fire modeling

Led internally funded research projects including modeling of facade fires, radiation transfer. 
Developed a GPU-accelerated FireFOAM solver, and incorprated adaptive mesh refinement and load-balancing techniques into FireFOAM, an open-source CFD solver for fire dynamics simulations written in C++ (see <a href="https://www.sciencedirect.com/science/article/abs/pii/S0379711225002206" target="_blank" rel="noopener">FSJ 2025</a>, <a href="https://www.sciencedirect.com/science/article/abs/pii/S0379711225002218" target="_blank" rel="noopener">FSJ 2025</a>).

<div class="project-figure-row">
  <div class="project-figure project-figure-narrow">
    <img src="{{ '/assets/img/amr1.png' | relative_url }}" alt="Adaptive mesh refinement result 1" />
  </div>
  <div class="project-figure project-figure-narrow">
    <img src="{{ '/assets/img/amr2.png' | relative_url }}" alt="Adaptive mesh refinement result 2" />
  </div>
  <div class="project-figure project-figure-wide">
    <img src="{{ '/assets/img/facade-side-by-side-153.png' | relative_url }}" alt="Facade fire modeling side-by-side results" />
  </div>
</div>

### Deflagration to detonation transition

Developed a GPU-accelerated compressible reactive flow solver for fundamental studies of detonation wave-solid structure interactions.
Performed high-fidelity simulations of deflagration-to-detonation transition to quantify onset conditions and wave dynamics in reactive mixtures. (see <a href="https://www.sciencedirect.com/science/article/abs/pii/S001021802100153X" target="_blank" rel="noopener">CNF 2021</a>, <a href="https://www.sciencedirect.com/science/article/abs/pii/S0010218021002601" target="_blank" rel="noopener">CNF 2021</a>, <a href="https://www.sciencedirect.com/science/article/abs/pii/S001021802100448X" target="_blank" rel="noopener">CNF 2022</a>, and <a href="https://www.sciencedirect.com/science/article/abs/pii/S154074892200308X" target="_blank" rel="noopener">PCI 2023</a>).

<div class="project-figure-row">
  <div class="project-figure project-figure-narrow">
    <img src="{{ '/assets/img/ddt.png' | relative_url }}" alt="Deflagration to detonation transition" />
  </div>
  <div class="project-figure project-figure-wide">
    <img src="{{ '/assets/img/shock-waves.png' | relative_url }}" alt="Shock waves" />
  </div>
  <div class="project-figure project-figure-medium project-figure-cover">
    <img src="{{ '/assets/img/rde.png' | relative_url }}" alt="Rotating detonation engine" />
  </div>
</div>

### Hydrodynamic stability of premixed flames

Developed a parallel computing code to solve the low-Mach-number Navier–Stokes equations for studying hydrodynamic stability of premixed flames and Direct Numerical Simulation of turbulent flows; the code scales efficiently to over ~1000 CPUs (see <a href="https://www.cambridge.org/core/journals/journal-of-fluid-mechanics/article/abs/linear-stability-analysis-of-a-premixed-flame-with-transverse-shear/117E30FF6A3D485F7DB427273BD74F11" target="_blank" rel="noopener">JFM 2015</a>). 
Analyzed mass conservation property and solvability of the discretized zero-Mach-number Navier–Stokes equations (see <a href="https://www.sciencedirect.com/science/article/abs/pii/S002199911930837X" target="_blank" rel="noopener">JCP 2020</a>).

<div class="project-image-row">
  <img class="image-wide" src="{{ '/assets/img/DNS.png' | relative_url }}" alt="DNS" />
  <img src="{{ '/assets/img/hydrodynamics.png' | relative_url }}" alt="Hydrodynamics" />
</div>
-->
