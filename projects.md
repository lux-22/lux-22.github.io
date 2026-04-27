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
  }
</style>

Coming soon.

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

### Weather Prediction & Trading System 

<div class="ascii-diagram">
 SOURCES           INGESTION          FEATURES           MODELING          LIVE
 ───────           ─────────          ────────           ────────          ────

 Weather  ──┐      ┌─────────┐      ┌───────────┐      ┌───────────┐      ┌────────┐
 Forecast ──┼─────→│ Unified │─────→│ Weather & │─────→│ Quantile  │─────→│ ML     │
            │      │   CSV   │      │ Market    │      │ Modeling  │      │ Infer. │
 Station  ──┼─────→│ Storage │─────→│ Features  │─────→│ (LGBM)    │─────→│ & Exec │
 Obs      ──┘      └─────────┘      └─────┬─────┘      └─────┬─────┘      └────────┘
                                          │                  │
 Predict. ──┐      ┌─────────┐            │            ┌─────┴─────┐      ┌────────┐
 Markets  ──┴─────→│ Market  │────────────┘            │ Walk-fwd  │      │ PnL &  │
                   │ Ingest  │                         │ Backtest  │      │ Trades │
                   └─────────┘                         └───────────┘      └────────┘
</div>

- **Data engineering and research layer:** Integrates NOAA observations, forecasts, and market data for feature construction, probabilistic modeling, and out-of-sample evaluation of weather prediction contracts. Repository: <a href="https://github.com/lux-22/weather_prediction" target="_blank" rel="noopener">github.com/lux-22/weather_prediction</a>.
- **Market microstructure and strategy layer:** Supports live order-book ingestion, negative-risk logic, and inventory-aware quoting research to study pricing dynamics and market-making behavior. Repository: <a href="https://github.com/lux-22/kpmm" target="_blank" rel="noopener">github.com/lux-22/kpmm</a>.
- **Execution layer:** Provides production-oriented tooling for automated order generation, scheduled runs, and deployment of strategy-driven trades. Repository: <a href="https://github.com/lux-22/autotrade" target="_blank" rel="noopener">github.com/lux-22/autotrade</a>.

<div style="margin-top: 10px;">
  <a href="{{ '/assets/files/weather_prediction_architecture.html' | relative_url }}" target="_blank">View high-fidelity interactive architecture diagram &rarr;</a>
</div>

<!--
### AI for science
...
-->
