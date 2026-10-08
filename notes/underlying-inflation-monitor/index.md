# A global underlying-inflation monitor with a blended projection system
Carlos Galindo

> [!NOTE]
>
> ### At a glance
>
> - **Question.** Where is inflation heading once one-off noise is stripped out, across many economies at once, and how wide is the range of outcomes?
> - **Approach.** A monthly panel of headline and core inflation for 22 economies; several measures of underlying inflation; projections that blend model-based drivers with an external benchmark forecast.
> - **Finding.** One method now covers 22 economies to January 2025: a family of underlying-inflation measures per economy and a full projection distribution at each horizon, not a single line. The benchmark blend keeps near-term paths grounded, while the model’s drivers explain where and why the outlook departs from it.
> - **Why it matters.** Policy and market readers need a consistent, comparable read of underlying inflation across economies, and a forecast that shows its range of outcomes as well as its central path.

## The question

Monthly inflation is noisy. A single hot or cold print can reflect a holiday shift, a one-off price change or a seasonal pattern that has moved. The question that matters to a central banker, a macro investor or a government forecaster is different: what is the underlying pace of price growth, and where does it head over the next year?

Answering that for one country is routine. Answering it for many countries, in the same way, every month, is harder. Each economy has its own seasonality, its own volatile components and its own relationship to oil and the exchange rate. A set of one-off country analyses cannot be compared, and an unmaintained set decays quickly.

This project rebuilt and improved a multi-country underlying-inflation monitor and the headline and core projection system behind it. Both were begun in a previous role. The rebuild covers 22 economies, with projections to January 2025, and the projections blend model-based drivers with an external benchmark forecast.

## Approach

### The monitor

For each economy the monitor tracks headline and core inflation monthly, and presents several measures of underlying inflation side by side rather than choosing one. The set used in the reports includes:

- short moving averages of seasonally adjusted monthly changes, expressed at an annual rate;
- a local trend model that separates a slowly moving trend from month-to-month noise;
- a “statistical super-core” that discards the most volatile items in each period;
- momentum gauges that compare the recent pace with the pace a year earlier.

Putting the measures together matters. When they agree, the signal is clear. When they diverge, the divergence is itself information: it usually means a few components are doing the work. Seasonal adjustment and cycle extraction are automated and robust, so that every economy is cleaned the same way each month.

### The projection system

Projections are built from monthly changes and integrated into an index, from which year-on-year rates follow.

1.  **Drivers.** Each economy’s own past inflation, oil prices, exchange rates, and broad commodity and financial-conditions factors distilled from large panels of data.
2.  **Selection.** Each economy gets the specification its own data support, chosen systematically rather than by hand.
3.  **An ensemble of paths.** Rather than one regression, the system fits many variants across forecast settings and origins. The forecast distribution is the cross-section of those paths, not an assumed bell curve.
4.  **An outside anchor.** An external benchmark forecast enters as one of the drivers, blended with the model’s own target.
5.  **Regimes and fans.** A regime model gives the probability of each inflation regime, and fan charts show the range of outcomes at every horizon.
6.  **Scenarios.** A grid of exchange-rate and oil shocks in each direction maps how headline inflation would respond.

The probabilistic readings built on this system, from threshold probabilities to pooled forecast distributions, are set out in a companion note, [Inflation forecasts as probabilities, not single numbers](../inflation-forecast-probabilities/index.html).

## What the work shows

The first result is the monitor itself. Underlying inflation is shown as a family of measures per economy. The report pages for each economy carry the monthly picture, a longer history, and a comparison across the measures. A September 2024 edition ran to 66 pages, built on an automated monthly refresh so that the same view could be reproduced for every economy.

The figure below shows the idea on simulated data. A noisy monthly series hides a slowly moving trend. The short moving average lags and still carries noise, while the local trend and the trimmed measure follow the underlying pace more closely.

<div id="fig-measures">

![](index_files/figure-commonmark/fig-measures-output-1.png)

Figure 1: Several measures of underlying inflation on one noisy series: monthly annualised rate, three-month average and a smoothed trend (simulated data).

</div>

The second result is the projection design. Because the ensemble produces many candidate paths, the system yields a full distribution at each horizon and not just a central line. Anchoring on an external benchmark keeps near-term projections grounded; the model drivers add the economy-specific reasons for deviating from it later in the horizon.

<div id="fig-fan">

![](index_files/figure-commonmark/fig-fan-output-1.png)

Figure 2: A projection fan from an ensemble of paths, with an external benchmark path for comparison (simulated data).

</div>

The third result is breadth. Putting 22 economies on one footing allows a cross-country read: which economies have underlying inflation running above the level that headline suggests, and which below. The figure shows that kind of view on simulated numbers.

<div id="fig-panel">

![](index_files/figure-commonmark/fig-panel-output-1.png)

Figure 3: Underlying trend minus latest headline rate across 22 economies, ranked (simulated data).

</div>

## Insights

- **Show several measures, not one.** Disagreement among underlying-inflation measures is the most useful warning that a few components are driving the headline.
- **Distributions beat single lines.** Building the forecast distribution from an ensemble of paths avoids assuming a shape, and shows when risks are skewed.
- **An outside anchor disciplines the near term.** Blending in an external forecast keeps the first months grounded and lets the model’s drivers explain where, and why, the outlook departs from it.
- **Consistency is the product.** Applying one method to 22 economies makes the results comparable and keeps the maintenance cost bounded.

## Scope and next steps

The system is built for monthly, cross-country monitoring: one consistent read of underlying inflation and its outlook for each of 22 economies, refreshed automatically, with projections to January 2025.

The natural extensions are three. First, a systematic out-of-sample scoring of the projections and their fans against the external benchmark, economy by economy and horizon by horizon. Second, probability-based scores for the full distributions, so that the ensemble’s weights can be learned from its own record. Third, extending the exchange-rate and oil scenario grid to every economy in each edition.

The full method and worked examples can be discussed on request.

## About the evidence

The work was done between May 2024 and January 2025, building on a system begun in a previous role. It covers monthly headline and core inflation for 22 economies. The benchmark forecast is external and is not reproduced here. All figures on this page are simulated.

Figures and tables marked *simulated* are generated from simulated data built to share the structure of the analysis (its variables, horizons and frequencies). They show how each method works and what its output looks like. Results stated in the text, and figures that give a source, are the project’s own. Methods are described at the level of a methods section. Code and data pipelines are not reproduced here.
