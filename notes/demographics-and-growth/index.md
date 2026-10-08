# Demographics and growth in emerging markets
Carlos Galindo

> [!NOTE]
>
> ### At a glance
>
> - **Question.** How far do a country’s demographic trajectory and its social conditions together explain how fast an emerging economy can grow over the next two decades?
> - **Approach.** Pair published population projections with public social indicators for 18 economies, reduce each block to a single factor, and compare both factors with projected potential growth.
> - **Finding.** Working-age population growth and inequality line up with projected growth in the expected directions, yet several economies sit far from the pattern, which points to social fabric and productivity as the swing factors.
> - **Why it matters.** It turns the “demographic dividend” slogan into a screen that separates economies with a dividend from those able to cash it.

## The question

Demographics is the slow variable in macroeconomics. Births, deaths and migration set the size of the workforce a generation ahead, and they are known with far more confidence than almost anything else in a long-run forecast. The popular story is that a young, growing population is a growth engine and an ageing one is a drag.

That story is incomplete in a way that matters to anyone allocating attention or capital across emerging markets. A large cohort of working-age people is a potential, not an outcome. It becomes growth only when those people are educated, healthy, employed and able to move up, and when savings and investment follow. This project asked a simple question of that framework: across a broad group of emerging economies, how much of projected growth lines up with demography, and how much with the social conditions that decide whether demography pays?

The work was a research note and a presentation, written and delivered in under a week in spring 2025. It was built to be read by decision-makers, so it favours a clear structure and a short list of takeaways over econometric detail.

## Approach

**Coverage.** The sample covers 18 emerging economies across Latin America, emerging Asia, Central and Eastern Europe, the Middle East and Africa. For each one the project assembled projected annual growth of total and economically active population over 2024–2044, the year in which the working-age population peaks, the year in which the dependency ratio crosses one half, and projected potential output growth over the same horizon taken from published external work. A second block of public indicators described social conditions: literacy, urbanisation, income inequality, life expectancy, connectivity, access to electricity, and spending on education and health.

**Framework.** The note starts from the demographic dividend: a falling dependency ratio opens a window in which savings, investment and productivity can rise, provided human capital and social mobility keep up. It also treats the mirror image, demographic drag, when the workforce shrinks and the dependency burden climbs.

**Factors.** To avoid choosing among dozens of overlapping indicators, each block was standardised and reduced to its first principal component. The demographic factor was built from six population variables and the social fabric factor from twelve variables on education, infrastructure and well-being. A composite score averaged the two with equal weights. Each country’s score can be decomposed into the contribution of every underlying variable, which makes the ranking explainable in a meeting rather than a black box.

**Reading the relationships.** Factors and individual indicators were set against projected potential growth with correlations, simple regressions and a quadrant map that sorts countries by strength of demography and strength of social fabric. A cluster analysis grouped economies with similar profiles. A comparison across several published long-run growth scenarios gave a sense of how wide the disagreement over each country’s trajectory is.

## What the work shows

**Demography lines up with growth, modestly.** Across the sample, growth of the economically active population and projected potential growth moved together, with a correlation of about 0.56 in one run of the data. Population growth and active-population growth were close to the same thing, as expected, with a correlation near 0.9. The simulated figure below shows what such a relationship looks like for 18 economies: an upward slope with a lot of scatter around it.

<div id="fig-demography-growth">

![](index_files/figure-commonmark/fig-demography-growth-output-1.png)

Figure 1: Growth of the economically active population against projected potential growth, 18 economies, shaded by inequality tercile (simulated data).

</div>

**Inequality travels with weaker growth.** Higher income inequality was associated with lower projected growth, and the inequality-growth association was the strongest of the social indicators in one run (a correlation of about −0.74). Literacy and urbanisation correlated negatively with projected growth in the sample, which looks perverse until one notices who is in it: economies that are already highly urbanised and literate are the mature ones, with lower growth ceilings. These are level effects, not evidence that schooling hurts. The note says so plainly, because a naive reading would recommend the opposite of what the development literature shows.

**The standout cases are the instructive ones.**

- India combines a growing workforce, with its working-age population peaking around 2032, with the highest projected potential growth of the group, about 6.2% a year, despite the weakest social scorecard on literacy and urbanisation. Its case rests on scale and on the scope for upward mobility if policy delivers.
- South Africa has a similarly favourable demographic profile but a projected potential growth of only about 1.0% a year. Inequality and weak human capital are the standard explanation, and it is the clearest example of a dividend that goes uncollected.
- Korea and Taiwan show the opposite: shrinking workforces, high literacy and low inequality, and growth sustained by productivity.

**Two factors, four quadrants.** Plotting the demographic factor against the social fabric factor sorts the economies into four groups: strong on both, strong demography with weak social fabric, the reverse, and weak on both. Each factor, alone, accounted for about 0.37 and 0.38 of the variation (R-squared) in projected growth, and the composite did better than either. The factors themselves summarise their blocks unevenly: the first demographic component captured about 63.0% of the variance of its six variables, the social component about 44.5% of its twelve.

<div id="fig-quadrants">

![](index_files/figure-commonmark/fig-quadrants-output-1.png)

Figure 2: Demographic factor against social fabric factor for 18 economies, grouped by quadrant, with the equal-weight composite as the diagonal (simulated data).

</div>

**The timing matters as much as the level.** The most useful single variable for a decision-maker is not the growth rate of the population but when the dependency ratio crosses one half, and when the workforce peaks. Some economies are decades from that threshold, others have already passed it. The stylised paths below show three types of profile.

<div id="fig-dependency">

![](index_files/figure-commonmark/fig-dependency-output-1.png)

Figure 3: Stylised dependency-ratio paths, 2024-2044, for a young, a maturing and an ageing economy; the dashed line is the one-half threshold (simulated data).

</div>

## Insights

1.  **Demography sets the ceiling; social fabric sets how much of it is reached.** The same working-age growth appears alongside very different projected growth, and inequality and human capital are the most natural candidates for the gap.
2.  **Productivity can offset shrinking numbers.** The high-literacy, low-inequality economies with falling workforces still show respectable projected growth, which says that the weight falls on output per worker.
3.  **Timing beats averages.** The year a workforce peaks and the year the dependency ratio crosses one half say more about the investment horizon than a twenty-year average growth rate.
4.  **Level effects mislead.** Negative correlations for literacy and urbanisation reflect mature economies with lower growth ceilings, not a harm from education.
5.  **Disagreement among scenarios is information.** Long-run growth scenarios from different institutions can differ by several percentage points for the same country, so a single projection should not be treated as a fact.

## Limits and next steps

The comparison is cross-sectional, with 18 observations, and the growth variable is itself a projection rather than an outcome. It therefore shows how forecasts line up with fundamentals, not what fundamentals cause. The projections already embed demographic assumptions, so some of the demography-growth link is built in.

The demographic factor, as constructed, was dominated by population size rather than by the speed or shape of change, which is not the dimension that the dividend argument cares about. A better version would build the factor from growth and timing variables only. Early summaries also reported different correlations for the same relationship, a reminder to freeze one dataset, regenerate every figure from it, and quote only that version. Next steps are to add dependency-ratio timing as an explicit regressor, to include a measure of productivity growth, and to test whether the inequality effect survives once the sample is widened beyond 18 economies.

The investment-style tiering that accompanied the early drafts was a presentation device, not a result, and is not offered here as advice.

## About the evidence

The note and presentation were produced in spring 2025, using published population projections, published long-run growth scenarios and public development indicators for 18 emerging economies. Statements of correlation and explained variance in the text are the project’s own results; the specific values are those reported in the working outputs. All charts on this page are simulated to share the structure of the analysis and are not the project’s results.

Figures and tables marked *simulated* are generated from simulated data built to share the structure of the analysis (its variables, horizons and frequencies). They show how the method works and what its output looks like; they are not the project’s results. Results stated in the text are the project’s own. Methods are described at the level of a methods section. Code and data pipelines are not reproduced here.
