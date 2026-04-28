---
layout: homepage
---

<div class="page-tabs">
  <a class="tab" href="{{ '/' | relative_url }}">Home</a>
  <a class="tab" href="{{ '/publications.html' | relative_url }}">Publications</a>
  <a class="tab active" href="{{ '/projects.html' | relative_url }}">Projects</a>
</div>

## Projects

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
  .ascii-diagram {
    color: #64748b;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    line-height: 1.25;
    margin: 30px 0;
    overflow-x: auto;
    white-space: pre;
    user-select: none;
    padding-left: 1.5em;
  }
</style>

<small>All projects listed here were pursued independently on personal time, using publicly available data and personal infrastructure, and are unaffiliated with my employer.</small>

### Prediction Markets Research Platform

Developed an end-to-end systematic research platform for probabilistic forecasting and automated trading, validated on event contracts as a sandbox for signal infrastructure and strategy development.

<div class="ascii-diagram">
 SOURCES           INGESTION          FEATURES           MODELING          PRODUCTION
 ───────           ─────────          ────────           ────────          ──────────

 Alt-Data ──┐      ┌─────────┐      ┌───────────┐      ┌───────────┐      ┌──────────┐
 Feeds    ──┼─────→│ Unified │─────→│ Feature   │─────→│ Signal    │─────→│ Signal   │
            │      │  Data   │      │ Store     │      │ Models    │      │ Gen &    │
 Ground   ──┼─────→│ Storage │─────→│           │─────→│ (LGBM)    │─────→│ Exec     │
 Truth    ──┘      └─────────┘      └─────┬─────┘      └─────┬─────┘      └──────────┘
                                          │                  │
 Market   ──┐      ┌─────────┐            │            ┌─────┴─────┐      ┌──────────┐
 Data     ──┴─────→│ Market  │────────────┘            │ Walk-fwd  │      │ Perf. &  │
                   │ Ingest  │                         │ Backtest  │      │ Risk     │
                   └─────────┘                         └───────────┘      └──────────┘
</div>

<div class="ascii-diagram">
 BACKTEST (out-of-sample: 2026-01-01 to 2026-03-31)
 ───────────────
 Train / test split     ≤ 2025-12-31  /  2026-01-01 →
 Markets                20 stations across 4 US time zones
 Validation             Rolling-origin walk-forward (30-day step, 14-day window)
 Point-in-Time          No lookahead; all features from data available at decision time
 Decision snapshot      Station-local midnight; cross-timezone aligned
 Transaction costs      Kalshi taker fee; YES ask-side execution
 Position sizing        1 contract / binary 0–1 outcome / no compounding
 ──────────────────────────────────────────────
 Pearson IC t-stat      3.16  (p &lt; 0.01)
 IC IR                  0.34
 Win rate by decile     24.8% → 59.0%
 Daily Sharpe           0.47
 Positive IC days       62.9%  (91 trading days)
 Trades                 1,046
</div>
<!--
→ Full methodology and charts in the research note
-->

- <strong>Data &amp; research layer:</strong> Multi-source alt-data ingestion, feature engineering, and probabilistic signal modeling with walk-forward validation. Repository: <a href="https://github.com/lux-22/weather_prediction" target="_blank" rel="noopener">github.com/lux-22/weather_prediction</a>.

- <strong>Market microstructure and strategy layer:</strong> Supports live order-book ingestion, negative-risk logic, and inventory-aware quoting research to study pricing dynamics and market-making behavior. Repository: <a href="https://github.com/lux-22/kpmm" target="_blank" rel="noopener">github.com/lux-22/kpmm</a>.
- <strong>Execution layer:</strong> Provides production-oriented tooling for automated order generation, scheduled runs, and deployment of strategy-driven trades. Repository: <a href="https://github.com/lux-22/autotrade" target="_blank" rel="noopener">github.com/lux-22/autotrade</a>.


<div style="margin-top: 10px;">
  <a href="{{ '/assets/files/weather_prediction_architecture.html' | relative_url }}" target="_blank">View high-fidelity interactive architecture diagram &rarr;</a>
</div>

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
