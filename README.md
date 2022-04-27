<!-- README.md is generated from README.Rmd. Please edit that file -->

OpenCaseStudies
===============

<!-- badges: start -->

[![render-README](https://github.com/opencasestudies/ocs-bp-vaping-case-study/workflows/render-README/badge.svg)](https://github.com/opencasestudies/ocs-bp-vaping-case-study/actions)
[![render-index](https://github.com/opencasestudies/ocs-bp-vaping-case-study/workflows/render-index/badge.svg)](https://github.com/opencasestudies/ocs-bp-vaping-case-study/actions)
<!-- badges: end -->

### Important links

-   HTML:
    <a href="https://www.opencasestudies.org/ocs-bp-vaping-case-study/" class="uri">https://www.opencasestudies.org/ocs-bp-vaping-case-study/</a>
-   GitHub:
    <a href="https://github.com/opencasestudies/ocs-bp-vaping-case-study/" class="uri">https://github.com/opencasestudies/ocs-bp-vaping-case-study/</a>
-   Bloomberg American Health Initiative:
    <a href="https://americanhealth.jhu.edu/open-case-studies" class="uri">https://americanhealth.jhu.edu/open-case-studies</a>

### Disclaimer

The purpose of the [Open Case
Studies](https://opencasestudies.github.io) project is **to demonstrate
the use of various data science methods, tools, and software in the
context of messy, real-world data**. A given case study does not cover
all aspects of the research process, is not claiming to be the most
appropriate way to analyze a given dataset, and should not be used in
the context of making policy decisions without external consultation
from scientific experts.

### License

This case study is part of the
[OpenCaseStudies](https://opencasestudies.github.io) project. This work
is licensed under the Creative Commons Attribution-NonCommercial 3.0
([CC BY-NC 3.0](https://creativecommons.org/licenses/by-nc/3.0/us/))
United States License.

### Citation

To cite this case study:

Wright, Carrie and Ontiveros, Michael and Meng, Qier and Jager, Leah and
Taub, Margaret and Hicks, Stephanie. (2020).
<a href="https://github.com/opencasestudies/ocs-bp-vaping-case-study" class="uri">https://github.com/opencasestudies/ocs-bp-vaping-case-study</a>.
Vaping Behaviors in American Youth (Version v1.0.0).

### Acknowledgments

We would like to acknowledge [Renee
Johnson](https://www.jhsph.edu/faculty/directory/profile/2848/renee-m-johnson)
for assisting in framing the major direction of the case study and for
reviewing the case study for subject matter content.

We would like to acknowledge [Michael
Breshock](https://mbreshock.github.io/) for his contributions to this
case study and developing the `OCSdata` package.

We would also like to acknowledge the [Bloomberg American Health
Initiative](https://americanhealth.jhu.edu/) for funding this work.

### Reading Metrics

The total reading time for this case study was calculated with
[koRpus](https://github.com/unDocUMeantIt/koRpus): **About 75 minutes**

The Flesch-Kincaid Readability Index was also calculated with
[koRpus](https://github.com/unDocUMeantIt/koRpus): **Grade 10, Age 15**

### Title

Vaping Behaviors in American Youth

### Motivation

Recent research suggests that overall use of tobacco by youths (middle
school and high school aged students) has increased in the last few
years, despite longer trends of declined use in previous years. This
increase has been attributed to a rapid and dramatic increase in the use
of e-cigarettes and other vaping products starting in 2017. This case
study explores the trends of tobacco product usage among american youths
surveyed in the
<a href="https://www.cdc.gov/tobacco/data_statistics/surveys/nyts/index.htm" target="_blank">National Youth Tobacco Survey (NYTS)</a>
which is an annual survey that asks students in high school and middle
school (grades 6-12) about tobacco usage in the United States of
America. Although this survey was started in 1999, data from
**2015-2019** will be used in this case study as these are the only
years that asked questions about e-cigarette usage.

### Motivating questions

1.  How has tobacco and e-cigarette/vaping use by American youths
    changed since 2015?

2.  How does e-cigarette use compare between males and females?

3.  What vaping brands and flavors appear to be used the most
    frequently?  
    This is based on the following survey questions:  
    &gt; “During the past 30 days, what brand of e-cigarettes did you
    usually use?”  
    &gt; “What flavors of tobacco products have you used in the past 30
    days?”

4.  Is there a relationship between e-cigarette/vaping use and other
    tobacco use?

### Data

Survey data from the
<a href="https://www.cdc.gov/tobacco/data_statistics/surveys/nyts/index.htm" target="_blank">National Youth Tobacco Survey (NYTS)</a>
for 2015, 2016, 2017, 2018, and 2019. Each year has it’s own code book
and excel file. Questions were slightly different for each year.

#### Learning Objectives

The skills, methods, and concepts that students will be familiar with by
the end of this case study are:

<u>**Data Science Learning Objectives:**</u> 1. Import data from Excel
files 2. Merge data from multiple similar but not identical data
structures 3. Create effective longitudinal data visualizations 4. Write
functions in R 5. Apply functions across data subsets using `purrr` and
`dplyr` functionality.

<u>**Statistical Learning Objectives:**</u>

1.  Understanding of different types of longitudinal data
2.  Usage of code books
3.  Conceptual understanding of survey weighting
4.  Implementing logistic regression with survey weighting

#### Data import

In this case study we cover data import using the Tidyverse `readxl`
package to import the excel files for each year of the survey. We also
use the `map()` function of the Tidyverse `purrr` package to efficiently
perform the data importation on all the files we one command.

#### Data wrangling

This case study goes into great detail about using codebooks to select
the survey questions of interest and to recode the numeric data using
the `recode` function of the `dplyr` package to reflect the responses of
the students surveyed. As multiple questions needed to be similarly
recoded across the different survey years, we demonstrate how to write
functions and use the `purrr` package to apply these functions
efficiently to all the data for the various years.

We also cover how to create new variables using the `mutate()` function
and the `case_when()` function of the `dplyr` package to represent
specific subgroups of surveyed students that meet various conditions.

Finally we also demonstrate how to use the `bind_rows()` function and
the `dplyr` package to combine data.

#### Data Visualization

This case study particularly focuses on creating effective
visualizations to compare groups over time using the Tidyverse `ggplot2`
package.

We also cover how to add confidence intervals error bars to
`geom_line()` plots using `geom_segment()`.

### Analysis

This case study covers the use of the `srvyr` package to calculate
survey weighted means of various groups using information about the
survey design, strata, survey weights, and Primary Sampling Unit (PSU)
from the
<a href="https://www.cdc.gov/tobacco/data_statistics/surveys/nyts/index.htm" target="_blank">codebooks</a>
and
<a href="./docs/2019-nyts-dataset-and-codebook-microsoft-excel/2019-nyts-methodology-report-p.pdf" target="_blank">Methodology Reports</a>.for
the respective survey years.

We also perform a logistic regression analysis comparing vaping rates
among males and females using survey weighting using the `svyglm`
function of the `srvyr` package.

### Other notes and resources

<a href="https://www.tidyverse.org/" target="_blank">Tidyverse</a>  
<a href="https://r4ds.had.co.nz/functions.html" target="_blank">Writing functions</a>  
<a href="https://www.lib.ncsu.edu/data/icpsrfaq#whatare" target="_blank">Codebooks</a>  
<a href="https://www.bmj.com/about-bmj/resources-readers/publications/epidemiology-uninitiated/7-longitudinal-studies" target="_blank">Longitudinal studies</a>  
<a href="https://en.wikipedia.org/wiki/Panel_data" target="_blank">Panel data</a>  
<a href="https://en.wikipedia.org/wiki/Cross-sectional_data" target="_blank">Cross-sectional data</a>  
<a href="http://www.applied-survey-methods.com/weight.html" target="_blank">Survey weighting</a>  
<a href="https://en.wikipedia.org/wiki/Confidence_interval" target="_blank">Confidence intervals</a>  
<a href="https://www.mathsisfun.com/algebra/logarithms.html" target="_blank">Introduction to Logarithms</a>  
<a href="https://en.wikipedia.org/wiki/Logarithm" target="_blank">Logarithm</a>
<a href="https://www.rapidtables.com/math/algebra/Logarithm.html#log-rules" target="_blank">Rules of logs</a>
<a href="https://en.wikipedia.org/wiki/Odds_ratio" target="_blank">Odds ratio</a>  
<a href="https://en.wikipedia.org/wiki/Logit" target="_blank">Log odds</a>  
<a href="https://en.wikipedia.org/wiki/Contingency_table" target="_blank">2x2 table</a>  
<a href="https://en.wikipedia.org/wiki/Probability" target="_blank">Probability</a>  
<a href="https://en.wikipedia.org/wiki/Likelihood_function" target="_blank">Likelihood function</a>  
<a href="https://en.wikipedia.org/wiki/Maximum_likelihood_estimation" target="_blank">Maximum likelihood estimates</a>  
<a href="https://en.wikipedia.org/wiki/Linear_regression" target="_blank">Linear regression model</a>  
<a href="https://en.wikipedia.org/wiki/Logistic_regression" target="_blank">Logistic regression</a>  
<a href="https://en.wikipedia.org/wiki/Quasi-likelihood" target="_blank">Quasi-likelihood</a>  
<a href="https://en.wikipedia.org/wiki/Binomial_distribution" target="_blank">Binomial distribution</a>

For more information on linear regression see this
<a href="https://rafalab.github.io/dsbook/linear-models.html#linear-regression-in-the-tidyverse" target="_blank">book</a>
and this
<a href="https://opencasestudies.github.io/ocs-bp-diet/" target="_blank">case study</a>.

For more information on survey designs see
<a href="http://www.asasrms.org/Proceedings/y2008/Files/301835.pdf" target="_blank">here</a>
and
<a href="http://ocw.jhsph.edu/courses/StatMethodsForSampleSurveys/PDFs/Lecture5.pdf" target="_blank">here</a>.

For more information on survey analysis in R
<a href="https://r-survey.r-forge.r-project.org/survey/exmample-lonely.html" target="_blank">here</a>
and
<a href="http://r-survey.r-forge.r-project.org/survey/html/surveyoptions.html" target="_blank">here</a>.

If you are interested in an info-graphic summary of the 2019 findings,
and links to many more resources about this topic and data set, see the
FDA’s website
<a href="https://www.fda.gov/tobacco-products/youth-and-tobacco/youth-tobacco-use-results-national-youth-tobacco-survey" target="_blank">here</a>.

<u>**Packages used in this case study:**</u>

<table>
<colgroup>
<col style="width: 43%" />
<col style="width: 56%" />
</colgroup>
<thead>
<tr class="header">
<th>Package</th>
<th>Use in this case study</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="https://github.com/jennybc/here_here" target="_blank">here</a></td>
<td>to easily load and save data</td>
</tr>
<tr class="even">
<td><a href="https://readxl.tidyverse.org/" target="_blank">readxl</a></td>
<td>to import the data in the excel files</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/magrittr/vignettes/magrittr.html" target="_blank">magrittr</a></td>
<td>to use the compound assignment pipe operator <code>%&lt;&gt;%</code></td>
</tr>
<tr class="even">
<td><a href="https://stringr.tidyverse.org/articles/stringr.html" target="_blank">stringr</a></td>
<td>to manipulate the character strings within the data</td>
</tr>
<tr class="odd">
<td><a href="https://purrr.tidyverse.org/" target="_blank">purrr</a></td>
<td>to import the data in all the different excel and csv files efficiently</td>
</tr>
<tr class="even">
<td><a href="https://dplyr.tidyverse.org/" target="_blank">dplyr</a></td>
<td>to arrange/filter/select/compare specific subsets of the data</td>
</tr>
<tr class="odd">
<td><a href="https://readr.tidyverse.org/" target="_blank">readr</a></td>
<td>to import the CSV file data</td>
</tr>
<tr class="even">
<td><a href="https://tidyr.tidyverse.org/" target="_blank">tidyr</a></td>
<td>to rearrange data in wide and long formats</td>
</tr>
<tr class="odd">
<td><a href="https://ggplot2.tidyverse.org/" target="_blank">ggplot2</a></td>
<td>to make visualizations with multiple layers</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/scales/scales.pdf" target="_blank">scales</a></td>
<td>to allow us to look at the colors within the viridis package</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/viridis/vignettes/intro-to-viridis.html" target="_blank">viridis</a></td>
<td>to make plots with a color palette that is compatible with color blindness</td>
</tr>
<tr class="even">
<td><a href="https://forcats.tidyverse.org/" target="_blank">forcats</a></td>
<td>to allow for reordering of factors in plots</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/naniar/vignettes/getting-started-w-naniar.html" target="_blank">naniar</a></td>
<td>to make a visualization of missing data</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/srvyr/srvyr.pdf" target="_blank">syrvr</a></td>
<td>to use survey weights</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/cowplot/vignettes/introduction.html" target="_blank">cowplot</a></td>
<td>to allow plots to be combined</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/broom/vignettes/broom.html" target="_blank">broom</a></td>
<td>to create nicely formatted model output</td>
</tr>
<tr class="odd">
<td><a href="http://r-survey.r-forge.r-project.org/survey/index.html" target="_blank">survey</a></td>
<td>to fit survey-weighted logistic regression</td>
</tr>
</tbody>
</table>

#### For users

There is a [`Makefile`](Makefile) in this folder that allows you to type
`make` to knit the case study contained in the `index.Rmd` to
`index.html` and it will also knit the [`README.Rmd`](README.Rmd) to a
markdown file (`README.md`).

#### For instructors

Instructors can start at the Data Visualization section or at the Survey
Weighting section. However, if instructors choose to start at the Survey
Weighting section, then they need to comment out or delete the Summary
Plot section.

#### Target audience

For individuals or classes with some familiarity with regression. See
this
<a href="https://opencasestudies.github.io/ocs-bp-diet/" target="_blank">case study</a>
for an introduction to regression.

#### Suggested homework

Calculate confidence intervals for the unweighted estimates and add the
appropriate error bars to the main figures. Apply survey weights to one
of the figures produced in this case study in which weighted estimates
were not produced. Include error bars in the updated figure. Does the
figure change after the application of survey weights? If so, describe
how.  
Reproduce `final_plot` above for a different cohort of your choice.
Focusing on a single year of data, explore demographic factors that
contribute to tobacco use of some kind. Compare results of unweighted
and weighted analysis (for example, using the `svyglm` function to
calculate survey-weighted logistic regression estimates).

#### Estimate of RMarkdown Compilation Time:

~ About 107 - 117 seconds

This compilation time was measured on a PC machine operating on Windows
10. This range should only be used as an estimate as compilation time
will vary with different machines and operating systems.
