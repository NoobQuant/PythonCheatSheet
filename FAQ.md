# Frequently asked questions Statistics/Econometrics

## General statistics

- Correlation and independence: [No-correlation does not imply independence](https://en.wikipedia.org/wiki/Correlation_and_dependence#Correlation_and_independence). Why? Since correlation is [linear relationship similar to regression coefficient](https://stats.stackexchange.com/a/344619/162538).

- What does '*certainty equivalence*' mean?: [Answer 1](https://economics.stackexchange.com/a/19898/5764), [Answer 2](https://economics.stackexchange.com/a/9554/61).

- What is the difference between *factor* and *covariate*? See [here](https://stats.stackexchange.com/a/70826/162538).

- Expectation is minimizing squared deviation and median is minimizing absolute deviation: [here](http://gregorygundersen.com/blog/2019/10/04/expectation-median-opt/), [here](https://math.stackexchange.com/questions/113270/the-median-minimizes-the-sum-of-absolute-deviations-the-ell-1-norm), and [here](https://stats.stackexchange.com/questions/118/why-square-the-difference-instead-of-taking-the-absolute-value-in-standard-devia).

- Variance of random variables does not always exist: [here](https://math.stackexchange.com/q/4007718).

- t-test vs z-test: [here](https://stats.stackexchange.com/a/507081/162538) and [here](https://stats.stackexchange.com/a/61292/162538).

- What is a *test statistic*? Imbens & Rubin (2015), page 64.

- Why would we add independent variables to a regression?
  - In observational studies with causal interpretations: to adjust for confounding
  - In observational studies with no explicit causal interpretation: make allow for comparisons between units, eg. "when comparing two children whose mothers have the same level of education, the child whose mother is X IQ points higher is predicted to have a test score that is 6x higher, on average" (Gelman, Hill, Vehtari 2021 p. 134)
  - In predection tasks, to increase (in-sample) goodness of fit ([non-decreasing property of R2](https://stats.stackexchange.com/a/401466/162538))

- What is the difference between an *error term* and *residual term*?
  - "Error" or "disturbance" in a structural causal model is an unobserved, exogenous (influencing outcome but not influenced by other variables) variable that is shaped by physical reality. In statistical sense, "statistical error" or "statistical disturbance" is the amount by which an observation differs from its expected value.
  - "Residual" is an artifact of the analysis, which, by definition, is uncorrelated with the regressor. It is the difference between observed value and the estimated value. In statistical sense, it is the observable estimate of the unobservable statistical error.
  - See [Wikipedia](https://en.wikipedia.org/wiki/Errors_and_residuals) and page 8 of [Pearl (2021)](https://ftp.cs.ucla.edu/pub/stat_ser/r370.pdf)
  
  the deviation of the observed value from the (unobservable) true value of a quantity 

## Estimation

- What is the difference between MLE and least-squares? [Here](https://stats.stackexchange.com/questions/143705/maximum-likelihood-method-vs-least-squares-method) and [here](https://stats.stackexchange.com/questions/12562/equivalence-between-least-squares-and-mle-in-gaussian-model).

[What does ceteris paribus mean in regression for controls? At what values are they kept?](https://stats.stackexchange.com/q/180155/162538)

## Causality

### Causality, general

- [Definition of Structural Causal Model](https://stats.stackexchange.com/a/312130/162538)

- [Why is over identified models preferred over just identified models in Structural Equation Modeling?](https://stats.stackexchange.com/questions/183021/why-is-over-identified-models-preferred-over-just-identified-models-in-structura/183024)

- What is the difference between predetermined (weak exogeneity), strictly exogenous (strong exogeneity), and Granger causality?
  - See pages 199-200 Killian & Lütkepohl 2017.
  - Super exogeneity: see Pearl (2009, section 5.4.3, p.165)

- [Under which assumptions a regression can be interpreted causally?](https://stats.stackexchange.com/a/493905/162538)

- [How are interaction terms representented in DAGs?](https://stats.stackexchange.com/a/350132/162538)

- Pearl's view of Lucas critique: [Pearl 2015](https://ftp.cs.ucla.edu/pub/stat_ser/r391-reprint.pdf) page 5

- [Granger Causality vs. Pearl's/Rubin's causality frameworks](https://stats.stackexchange.com/q/144328/162538)

- How propensity scores differ from adding covariates in a regression?
  - [In theory the same](https://stats.stackexchange.com/a/8610/162538)
  - [Regressions extrapolates](https://stats.stackexchange.com/a/8655/162538)
  - [Using both is "doubly robust"](https://stats.stackexchange.com/a/248967/162538), see [this paper](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2943670/) section 5.

- [Gelman on identification strategies vs. estimation](https://statmodeling.stat.columbia.edu/2009/07/05/disputes_about/): "*here’s too much focus on technique and not enough thought put into what the estimates are really telling you*"

### Causality, PO vs SCM

- [Pearl's comments on Imben's paper *Potential Outcome and Directed Acyclic Graph Approaches to Causality*](http://causality.cs.ucla.edu/blog/index.php/2020/01/29/on-imbens-comparison-of-two-approaches-to-empirical-economics/)

- Pearl's view on "No causation without manipulation": Pearl (2009, section 11.4.5, p.361)

- Pearl's view on ignorability assumption: Pearl 2009, pages 79, 100, 341

- Interpretation of potential outcomes as error terms of a SCM: Pearl 2009, p.343.

- Advantage of POs
  - "*While DAGs illuminate the entire causal structure, the potential outcomes framework clarifies the assumptions about treatment assignment mechanism*" (Imai & Kim 2019)
  - "*[P]otential outcome model of causality [...] is valuable precisely because it helps researchers to stipulate assumptions, evaluate alternative data analysis techniques, and think carefully about the process of causal exposure. [...] [Language of potential outcomes] permits the analyst to conceptualize observational studies as if they were experimental designs controlled by someone other than the researcher.*" (Morgan & Winship 2015, p. 7)

- [Gelman on the difference between SCM and PO](https://statmodeling.stat.columbia.edu/2009/07/05/disputes_about/)

### Causality, time series

- [What is the difference between identification, calibration and estimation?](https://economics.stackexchange.com/a/36639)

### Causality, cross-section and panel

 - What is *analysis of covariance*?
   - In panel context, it is the fixed effects within estimator (Angrist & Pischke 2008, p.167).
   - "*ANCOVA evaluates whether the means of a dependent variable (DV) are equal across levels of a categorical independent variable (IV) often called a treatment, while statistically controlling for the effects of other continuous variables that are not of primary interest, known as covariates (CV) or nuisance variables. [...]  Intuitively, ANCOVA can be thought of as 'adjusting' the DV by the group means of the CV(s)*" ([Wikipedia](https://en.wikipedia.org/wiki/Analysis_of_covariance))

 - Connection between DiD and TWFE estimators
   - When there are two time periods and the treatment is administered to some units only in the second period, DiD and TWFE estimators are numerically equivalent (see e.g. [here page 19](https://imai.fas.harvard.edu/research/files/tscs.pdf), but find a better source). Does not hold e.g. when there are more periods or when each unit may receive the treatment multiple times.

## Cross-section

### Cross-section, standard errors

- When to use clustered stadard errors?
  - Based on [this paper](https://www.nber.org/system/files/working_papers/w24003/w24003.pdf), clustering of SEs is either *experimental design* or *sampling design* issue.
  - *Experimental design*: so-called "Moulton" problem where cluster of units, rather than individual units, are assigned to a treatment. See [this](https://blogs.worldbank.org/impactevaluations/when-should-you-cluster-standard-errors-new-wisdom-econometrics-oracle) and Angrist & Pischke (2008) chapter 8.2.1
  - *Sampling design*: What matters for clustering is how the sample was selected and whether there are clusters in the population of interest that are not represented in the sample. See [this ](https://blogs.worldbank.org/impactevaluations/when-should-you-cluster-standard-errors-new-wisdom-econometrics-oracle).
  - Note that fusing fixed effects vs. SE clustering answer different thins, see [this](https://stats.stackexchange.com/questions/185378/when-to-use-fixed-effects-vs-using-cluster-ses) and also the reference paper.

## Panel data

### Panel data, standard errors

- When to use clustered stadard errors in panel models?
  - In addition to cross-section case, one might need to think about serial correlation. See Angrist & Pischke (2008) section 8.2.2.

- What is a triple-difference (DiDiDi) design?
  - See section 18.3.3 of Huntington-Klein (2021) and [this pdf](https://www.nber.org/lecture/summer-institute-2007-methods-lecture-difference-differences-estimation).
  - Probably the same as difference-in-difference with heterogenous treatment effects, see [this](https://stats.stackexchange.com/questions/183302/difference-in-difference-with-interaction).

## Time series

### Time series, general

- What is ergodicity? See equation 1 of [Peters (2019)](https://www.nature.com/articles/s41567-019-0732-0.pdf).

### VAR - reduced form

### VAR - structural form

## Quantile regression

- What are assumptions behind quantile regression?: [here](https://stats.stackexchange.com/a/321001/162538) and [here](https://stats.stackexchange.com/a/39003/162538)

## References
 - Angrist & Pischke (2008): Mostly harmless econometrics
 - Gelman, Hill, Vehtari (2021): Regressions and other stories
 - [Huntington-Klein (2021)](https://theeffectbook.net/index.html): The effect
 - Imbens & Rubin (2015): Causal inference for statistics, social, and biomedical sciences
 - Pearl (2009): Causality