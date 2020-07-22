<!-- README.md is generated from README.Rmd. Please edit that file -->
OpenCaseStudies
===============

[![Build
Status](https://travis-ci.org/opencasestudies/ocs-bloomberg-vaping-case-study.svg?branch=master)](https://travis-ci.org/opencasestudies/ocs-bloomberg-vaping-case-study)

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

Wright, Carrie, and Ontiveros, Michael and Jager, Leah and Taub,
Margaret and Hicks, Stephanie. (2020).
<a href="https://github.com/opencasestudies/ocs-bloomberg-vaping-case-study" class="uri">https://github.com/opencasestudies/ocs-bloomberg-vaping-case-study</a>.
Vaping Behaviors in American Youth (Version v1.0.0).

### Title

Vaping Behaviors in American Youth

### Motivation

Recent research suggests that overall use of tobacco by youths (middle
shcool and high school aged students) has increased in the last few
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
    &gt;" What flavors of tobacco products have you used in the past 30
    days?"

4.  Is there a relationship between e-cigarette/vaping use and other
    tobacco use?

### Data

Survey data from the
<a href="https://www.cdc.gov/tobacco/data_statistics/surveys/nyts/index.htm" target="_blank">National Youth Tobacco Survey (NYTS)</a>
for 2015, 2016, 2017, 2018, and 2019. Each year has it’s own code book
and excel file. Questions were slightly different for each year.

#### Data import

In this case study we cover data import using the tidyverse `readxl`
package to import the excel files for each year of the survey. We also
use the `map()` function of the tidyverse `purrr` package to efficiently
perform the data imporation on all the files we one command.

#### Data wrangling and exploration

Ths case study goes into great detail about using codebooks to select
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
visualizations to compare groups over time using the tidyverse `ggplot2`
package.

We also cover how to add confidence intervals error bars to
`geom_line()` plots using `geom_segment()`.

#### Data Analysis

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
function of the `srvyr` package. AVOCADO this might change?

#### Statistical concepts

We provide an introduction of the following concepts:

1.  Understanding of different types of longitudinal data
2.  Usage of code books
3.  Conceptual understanding of survey weighting
4.  Implementing logistic regression with survey weighting

### Other notes and resources

#### For users

There is a [`Makefile`](Makefile) in this folder that allows you to type
`make` to knit the case study contained in the `index.Rmd` to
`index.html` and it will also knit the [`README.Rmd`](README.Rmd) to a
markdown file (`README.md`).

#### For instructors

#### Target audience

For individules or classes with some familiarity with regression. See
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

#### Learning Objectives

Avocado… should we maybe add a learning objectives section to the readme
files? Then we might want to replace the statistical concepts section.

The skills, methods, and concepts that students will be familiar with by
the end of this case study are:

Data science skills:

1.  Import data from Excel files
2.  Merge data from multiple similar but not identical data structures
3.  Create effective longitudinal data visualizations
4.  Write functions in R
5.  Apply functions across data subsets using `purrr` and `dplyr`
    functionality.

Statistical methods:

1.  Understanding of different types of longitudinal data
2.  Usage of code books
3.  Conceptual understanding of survey weighting
4.  Implementing logistic regression with survey weighting
