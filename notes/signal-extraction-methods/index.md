# Finding the signal in economic data
Carlos Galindo

> [!NOTE]
>
> ### At a glance
>
> - **Question.** When two economic series seem to move together, how much of that is seasonality, how much is a shared slow trend, and how much is genuine short-run co-movement?
> - **Approach.** Automated seasonal adjustment and trend-cycle decomposition, cross-spectral coherence by frequency, and a robust estimator of long-run growth, packaged to run on any series.
> - **Finding.** In a worked application to producer and consumer service prices, a claimed 70–80% correlation is not supported: correlations are 0.06–0.48. What link exists sits mostly at the seasonal frequency and in the very slow trend. Applied to 31 European economies over 1996–2026, the robust growth estimate sits above the ordinary mean in 27, because crisis falls outweigh the rebounds that followed.
> - **Why it matters.** Headline correlations average over frequencies, so they can hide where a relationship lives and overstate how useful it is for forecasting.

## The question

Economists are often handed a statement of the form “series A and series B are 70–80% correlated” and asked to build on it. Correlation of raw data is a blunt instrument. Almost every monthly price index has a strong calendar pattern, and almost every price index drifts upward over the long run. Two series can therefore look closely related simply because both rise in the same months of the year or both trend. Neither says anything about whether a change in one *leads to* a change in the other.

The work here began as a practical need: a way to take any economic series, strip out what is predictable from the calendar, isolate the trend, and ask what is left. The aim was a set of reusable methods that run the same way on any series, not a one-off analysis of one pair. Three methods were built for that purpose, and then tested on a concrete, contested claim about the relationship between producer prices and consumer service prices.

## Approach

**Seasonal adjustment and trend-cycle decomposition.** Each monthly series is decomposed into a trend, a seasonal factor and an irregular component. The workhorse specification is a multiplicative seasonal-ARIMA “airline” model with a regular and a seasonal moving-average term, with additive-outlier detection and no calendar regressors. The procedure was automated so that it can be applied to large collections of series without hand-tuning, and was applied to price and activity series for the United States and Mexico. Automation matters because a decomposition that needs a person to inspect each series cannot be used to screen thousands of them.

**Co-movement across frequencies.** For a pair of series the question is not “what is the correlation?” but “at which cycle lengths do they move together?”. Magnitude-squared coherence is, in effect, a correlation computed separately at each frequency, between zero (unrelated) and one (a perfect linear relationship at that cycle length). It was estimated with segment-averaged spectra for monthly first differences, and also for each decomposed component separately, with attention to three bands: the seasonal harmonics, a business-cycle band covering cycles of roughly 18 to 96 months, and the higher-frequency noise band. Significance was assessed against the usual null of no coherence, and the estimates were stress-tested across 14 combinations of segment length and overlap, because coherence estimates are biased upward when few segments are averaged.

**Long-run growth.** For any series, the long-run (steady-state) growth rate is estimated from annualised log growth. The method uses a robust location estimator, so that crisis quarters and one-off outliers do not drag the estimate, and compares it with the ordinary mean. A recursive version shows how the estimate and its 95% band evolved as data arrived. A band-pass filter isolates the slow component of growth, and a sequential search for structural breaks in that slow component shows whether a series has shifted regime.

**Application.** The methods were tested on five pairs of US price series: five producer price aggregates (final demand services, trade services, transportation and warehousing, a core measure and a core-excluding measure) against two consumer service indices (services less rent of shelter, and services less energy services), about 196 monthly observations from late 2009. The claim under test was that the two sides move together with a correlation of 70–80%. Results were checked on first differences and on log differences, since the two scale the data differently.

## What the work shows

**The headline claim does not hold.** Correlations of log differences across the five pairs run from 0.06 to 0.48, against 0.11 to 0.53 for plain first differences. Formal tests reject a true correlation of 0.70 for every pair, and rolling 36-month correlations never reach 0.70 in any window, peaking at 0.65. The log version is uniformly a little weaker than the first-difference one, because price indices with different base levels weight large changes unevenly. This is a methodological point worth knowing: the choice of transformation moves correlations by up to about 0.05, without changing the conclusion.

**Much of the correlation that exists is seasonal, and some is trend.** Decomposing each series shows where the link lives. Correlations between the seasonal components are 0.52–0.63 for the core, core-excluding and final-demand pairs. Correlations between trend growth rates are 0.18–0.44 for the four pairs against services less rent of shelter, highest for transport and for the core-excluding measure. The trends are estimated on observed data only, with no model forecast appended beyond the sample. Coherence agrees: between seasonal factors, mean coherence is 0.51–0.70 and reaches 0.81–0.86 at the seasonal band for the pure-price pairs. In plain terms, the two sides of the economy share a calendar and, for some pairs, a slow trend. Neither is evidence that producer prices pass through to consumers.

**Coherence is frequency-selective, not absent.** Averaged over all frequencies, the irregular components are only weakly coherent (mean 0.12–0.35). Yet peak coherence of the irregular components is significant at 0.42–0.82 for every pair, in 86–100% of the 14 estimator settings, and the conservative lower bounds for the raw series are 0.37 to 0.69. The transport-and-warehousing pair is the clearest case: its irregular component has coherence of 0.57 in the business-cycle band and 0.79 at the two-month cycle, which the seasonal model does not capture. The core measure, by contrast, has almost no coherence in the business-cycle band (0.06 for its trend). Its relationship with consumer services is narrow and calendar-bound.

**Zero-frequency coherence can mislead.** The trade-services pair has coherence of 0.91 at the zero frequency yet a time-domain correlation of just 0.06. There is no contradiction. All price indices share a long-run drift, so coherence at the lowest frequency is high, while the ordinary correlation is a spectrum-weighted average dominated by frequencies where this pair is unrelated (seasonal coherence 0.03).

**Lead-lag evidence points the wrong way for pass-through.** Granger tests show trade services preceding consumer services (p = 0.001, against 0.30 in reverse), but for the core-excluding measure the reverse direction dominates (p \< 0.001), which suggests feedback and not simple pass-through.

**Long-run growth across European economies.** The growth method was run on quarterly real GDP for 31 European economies, every country with an unbroken quarterly series from 1996 to mid-2026, with the EU27 aggregate as a reference. All economies share one window, 1996-Q2 to 2026-Q2 (121 quarters), and the summary statistics were fixed before any estimate was computed. The robust estimate is above the ordinary mean in 27 of the 31, because the outlying quarters are dominated by the falls of 2008–09 and 2020, which drag the mean down by more than the rebounds that followed lift it. The gap exceeds one standard error of the mean in four economies (Bulgaria, Estonia, Greece and Romania) and lies outside the 95% band in none, and the two estimators rank the economies almost identically (rank correlation 0.93). Ireland runs the other way (robust 4.1% against a mean of 5.4%), because its largest outliers are rises driven by multinational accounting. The slow component of growth shows at least one structural break in 16 of the 31. In 12 of those 16 the most recent regime grows more slowly than the 30-year average, in ten of them after a break between late 2006 and 2008. The exceptions are Greece, Italy, Portugal and Slovenia, whose latest regime begins with the post-2013 or post-2020 recovery. Counting every economy, latest-regime growth is below the window mean in 25 of 31. On each economy’s full available span, the robust estimate stays above the mean in 26 of 31, the same four economies exceed one standard error, and the rank correlation with the common-window ranking is 0.98.

The first three figures are drawn from the public price series and their stored decompositions, on observed months only (November 2009 to March 2026). The two long-run growth figures are drawn from Eurostat quarterly national accounts.

<div id="fig-decomp">

![](index_files/figure-commonmark/fig-decomp-output-1.png)

Figure 1: US producer prices for transportation and warehousing services: not seasonally adjusted, seasonally adjusted, and the trend from the airline-model decomposition, November 2009 to March 2026. Source: BLS via FRED; the author’s decomposition.

</div>

<div id="fig-coherence">

![](index_files/figure-commonmark/fig-coherence-output-1.png)

Figure 2: Coherence of monthly log changes for the five producer-consumer pairs, by cycle length. Dashed: the squared ordinary correlation. Dotted: the 95% threshold for coherence under no relationship. Source: BLS via FRED; the author’s calculations.

</div>

<div id="fig-components">

![](index_files/figure-commonmark/fig-components-output-1.png)

Figure 3: Correlation of each producer-consumer pair, measured on monthly log changes and on each decomposed component. Source: BLS via FRED; the author’s decomposition and calculations.

</div>

<div id="fig-steady">

![](index_files/figure-commonmark/fig-steady-output-1.png)

Figure 4: Long-run real GDP growth, 1996-Q2 to 2026-Q2, annualised: the robust estimate (dot) against the ordinary mean with its 95% band (bar), ordered by the robust estimate. Ireland is affected by multinational accounting. Source: Eurostat quarterly national accounts; the author’s calculations.

</div>

<div id="fig-steady-de">

![](index_files/figure-commonmark/fig-steady-de-output-1.png)

Figure 5: Germany: the long-run growth estimate as each quarter of data arrives, with its 95% band, 1997-Q2 to 2026-Q2 (estimates on fewer than five quarters of data are omitted). Source: Eurostat quarterly national accounts; the author’s calculations.

</div>

## Insights

1.  **Decompose before you correlate.** A pair can share a calendar and a trend without sharing any short-run dynamics. Splitting the series first changes the answer to “how related are they?”.
2.  **Summary statistics average over frequency.** The ordinary correlation is a weighted average of coherence across frequencies. A relationship that lives at one cycle length is diluted, and a high value at the lowest frequency is not evidence of causal pass-through.
3.  **Report the transformation.** Log differences and plain differences gave correlations up to about 0.05 apart. The effect is small, but it is systematic and should be disclosed.
4.  **Check the estimator before trusting the peak.** Coherence peaks depend on segment length and overlap. Reporting the share of settings that remain significant is more informative than quoting the largest value.
5.  **Robust growth rates are cheap insurance.** Across 31 European economies, crisis quarters pull the average growth rate below the typical quarter in 27, by more than one standard error in four. A robust estimate with a recursive band shows how much a long-run number can be trusted, and a break search shows whether the long run has itself moved.

## Scope and next steps

The methods are built to decompose price series automatically, so that thousands can be screened without inspecting each one, and to read the links between series band by band. The application to five pairs of US price series shows how a frequency-selective view tests a pass-through claim directly.

The natural extensions are three. First, measuring the size and variance share of the frequency-selective link. Second, a forecasting experiment in which a band-limited component of producer prices predicts consumer service inflation out of sample, against a naive benchmark. Third, extending the cross-country growth estimates to output per head and to bands that allow for autocorrelation in quarterly growth. These estimates describe total real GDP on current data with conventional standard errors, not potential output.

## About the evidence

The application uses public monthly price series for the United States from late 2009, about 196 observations per series, and the decomposition work was applied to US and Mexican price and activity series. The first three figures are drawn from those public series and the stored decompositions. The long-run growth figures use Eurostat quarterly national accounts: GDP in chain-linked volumes, seasonally and calendar adjusted, for 31 European economies and the EU27, in the release of 9 October 2026. The numbers in the text are the project’s own results from the real series. The work was done from 2025 to 2026, as part of a rebuild of an applied research toolkit.

Figures and tables marked *simulated* are generated from simulated data built to share the structure of the analysis (its variables, horizons and frequencies). They show how each method works and what its output looks like. Results stated in the text, and figures that give a source, are the project’s own. Methods are described at the level of a methods section. Code and data pipelines are not reproduced here.
