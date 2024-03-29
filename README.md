<!-- README.md is generated from README.Rmd. Please edit that file -->

OpenCaseStudies
===============

<!-- badges: start -->

[![render-README](https://github.com/opencasestudies/ocs-bp-opioid-rural-urban/workflows/render-README/badge.svg)](https://github.com/opencasestudies/ocs-bp-opioid-rural-urban/actions)
[![render-index](https://github.com/opencasestudies/ocs-bp-opioid-rural-urban/workflows/render-index/badge.svg)](https://github.com/opencasestudies/ocs-bp-opioid-rural-urban/actions)
<!-- badges: end -->

### Important links

-   Static version:
    <a href="https://www.opencasestudies.org/ocs-bp-opioid-rural-urban/" class="uri">https://www.opencasestudies.org/ocs-bp-opioid-rural-urban/</a>
-   Interactive version:
    <a href="https://rsconnect.biostat.jhsph.edu/ocs-bp-opioid-rural-urban-interactive/" class="uri">https://rsconnect.biostat.jhsph.edu/ocs-bp-opioid-rural-urban-interactive/</a>
-   GitHub:
    <a href="https://github.com/opencasestudies/ocs-bp-opioid-rural-urban/" class="uri">https://github.com/opencasestudies/ocs-bp-opioid-rural-urban/</a>
-   Bloomberg American Health Initiative:
    <a href="https://americanhealth.jhu.edu/open-case-studies" class="uri">https://americanhealth.jhu.edu/open-case-studies</a>

### Disclaimer

The purpose of the [Open Case Studies](https://www.opencasestudies.org)
project is **to demonstrate the use of various data science methods,
tools, and software in the context of messy, real-world data**. A given
case study does not cover all aspects of the research process, is not
claiming to be the most appropriate way to analyze a given dataset, and
should not be used in the context of making policy decisions without
external consultation from scientific experts.

### License

This case study is part of the
[OpenCaseStudies](https://www.opencasestudies.org) project. This work is
licensed under the Creative Commons Attribution-NonCommercial 3.0 ([CC
BY-NC 3.0](https://creativecommons.org/licenses/by-nc/3.0/us/)) United
States License.

### Citation

To cite this case study:

Wright, Carrie and Wang, Kexin and Meng, Qier and Jager, Leah and Taub,
Margaret and Hicks, Stephanie. (2020).
[https://github.com/opencasestudies/ocs-bp-opioid-rural-urban/](https://github.com/opencasestudies/ocs-bp-opioid-rural-urban)
Opioids in the United States (Version v1.0.0).

### Acknowledgments

We would like to acknowledge [Brendan
Saloner](https://www.jhsph.edu/faculty/directory/profile/2929/brendan-saloner)
for assisting in framing the major direction of the case study.

We would like to acknowledge [Michael
Breshock](https://mbreshock.github.io/) for his contributions to this
case study and developing the `OCSdata` package.

We would also like to acknowledge the [Bloomberg American Health
Initiative](https://americanhealth.jhu.edu/) for funding this work.

### Reading Metrics

The total reading time for this case study was calculated with
[koRpus](https://github.com/unDocUMeantIt/koRpus): **About 90 minutes**

The Flesch-Kincaid Readability Index was also calculated with
[koRpus](https://github.com/unDocUMeantIt/koRpus): **Grade 9, Age 14**

### Title

Opioids in United States

### Motivation

In this case study we will be examining the number of opioid pills
(specifically
[oxycodone](https://en.wikipedia.org/wiki/Opioid_epidemic_in_the_United_States)
and
[hydrocodone](https://en.wikipedia.org/wiki/Opioid_epidemic_in_the_United_States),
as they are the top two abused opioids) shipped to pharmacies and
practitioners at the county-level around the United States (US) from
2006 to 2014.

This data comes from the [DEA](https://www.dea.gov/) [Automated Reports
and Consolidated Ordering System
(ARCOS)](https://www.deadiversion.usdoj.gov/arcos/retail_drug_summary/)
and was released by the [Washington
Post](https://www.washingtonpost.com/) after legal action by the owner
of the [Charleston Gazette-Mail](https://www.wvgazettemail.com/) in West
Virginia and the [Washington Post](https://www.washingtonpost.com/).

We will investigate how the number of shipped pills compares for rural
and urban counties. This analysis will demonstrate how different regions
of the country may have been more at risk for opioid addiction crises
due to differing rates of opioid prescription (using the number of pills
as a proxy for prescription rates). This will help inform students about
how evidence-based intervention decisions are made in this area.

This case study is motivated by this
[article](https://www.cdc.gov/mmwr/volumes/68/wr/mm6802a1.htm?s_cid=mm6802a1_w),that
explored rates of opioid prescriptions in rural and urban communities in
the United States using the [Athenahealth electronic health record (EHR)
system](https://landing.athenahealth.com/g/improvecare?cmp=10672941&utm_salesforce=7016f000001yWQMAA2&utm_medium=cpc&utm_campaign=1%20Branded%20Experimental&utm_adgroup=ModBroad&utm_source=google&utm_term=%2Bathena%20%2Bhealth&utm_type=b&gclid=Cj0KCQjwtZH7BRDzARIsAGjbK2bn_oxyd0jNBGQkPMcSSpEuGbzLUqL8m-tuAQWMZ-smUNLLjtztB7EaAgSlEALw_wcB)
for 31,422 primary care providers from January 2014 to March 2017.

They found that:

> The percentage of patients prescribed an opioid was higher in
> **rural** than in urban areas.

### Motivating questions

<b><u> Our main question: </u></b>

1.  How did opioid shipment rates differ between rural and urban regions
    over time around the US from 2006-2014?

### Data

In this case study we will evaluate the number of
[oxycodone](https://en.wikipedia.org/wiki/Opioid_epidemic_in_the_United_States)
and
[hydrocodone](https://en.wikipedia.org/wiki/Opioid_epidemic_in_the_United_States)
pills shipped to pharmacies and practitioners at the county-level around
the United States (US) from 2006 to 2014.

This data comes form the [Automated Reports and Consolidated Ordering
System
(ARCOS)](https://www.deadiversion.usdoj.gov/arcos/retail_drug_summary/)
of the [DEA](https://www.dea.gov/) and was released by the [Washington
Post](https://www.washingtonpost.com/).

According to the [Washington Post](https://www.washingtonpost.com/):

> “It’s important to remember that the number of pills in each county
> does not necessarily mean those pills went to people who live in that
> county. The data only shows us what pharmacies the pills are shipped
> to and nothing else.”

#### Learning Objectives

The skills, methods, and concepts that students will be familiar with by
the end of this case study are:

<u>**Data Science Learning Objectives:**</u>

1.  Importing data from an [API](https://en.wikipedia.org/wiki/API)
    (`httr` and `jasonlite`)  
2.  How to join data with `dplyr`  
3.  How to reshape data by pivoting between “long” and “wide” formats
    and drop rows with `NA` values (`tidyr`)  
4.  How to create formatted tables of data with `formattable`  
5.  How to look for missing data in a dataset (`naniar`)  
6.  How to create data visualizations with `ggplot2`  
7.  How to create interactive plot for plots that are difficult to label
    because they have many elements (`ggiraph`)  
8.  How to combine plots with `patchwork`

<u>**Statistical Learning Objectives:**</u>

1.  Understanding of when and why data normalization is useful  
2.  Understanding of how group definitions can change results  
3.  Understanding of when to use a Wilcoxon rank sum test (also called
    Mann Whitney U test)  
4.  How to implement a Wilcoxon rank sum test in R  
5.  How to interpret a Wilcoxon rank sum test

#### Data import

In this case study we demonstrate how to import data from an API,
however we have also downloaded the data and saved it as an RDA and a
CSV file if instructors choose to use the data for another purpose. See
the `data/simpler_import` directory for CSV files and see
`data/imported` for RDA versions.

#### Data wrangling

This case study covers the differences between the various `*_join()`
functions of the `dplyr` package, as well as use of the `case_when()`
function to recode data based on particular evaluations of existing
values.

We also cover how to use the `tidyr` functions such as `pivot_wider()`
and `pivot_longer()` for reshaping data, as well as arranging levels of
factors using the `forcats` package.

Finally, this case study also covers a few of the `stringr` functions to
manipulate character strings, including `str_sub()`, and `str_detect()`.

#### Data Visualization

In this case study we show how to make faceted plots, how to create
interactive plots with the `ggiraph` package, how to combine plots with
the `patchwork` package, how to create plots that are both box plots and
jitter plots with the `ggpol` package, how to add labels directly to
plots with the `directlabels` package, and how to create formatted
tables with the `formattable` package. We also demonstrate how to look
for missing data using the `naniar` package.

### Analysis

This case study focuses on when and how to compare groups using the
nonparametric Wilcoxon rank sum test. This case study also focuses on
the importance of data normalization and the importance of how groups
are defined.

### Other notes and resources

<a href="https://rstudio.com/products/rstudio/features/" target="_blank">RStudio</a>  
<a href="https://github.com/rstudio/cheatsheets/raw/master/rstudio-ide.pdf" target="_blank">Cheatsheet on RStuido IDE</a>  
<a href="https://rstudio.com/resources/cheatsheets/" target="_blank">Other RStudio cheatsheets</a>  
[RStudio projects](https://r4ds.had.co.nz/workflow-projects.html)

<a href="https://www.tidyverse.org/" target="_blank">Tidyverse</a>

<a href="https://cran.r-project.org/web/packages/magrittr/vignettes/magrittr.html" target="_blank">Piping in R</a>

[application prgoramming interface
(API)](https://en.wikipedia.org/wiki/API)  
[JavaScript Object Notation
(JSON)](https://fileinfo.com/extension/json#:~:text=A%20JSON%20file%20is%20a,web%20application%20and%20a%20server.)  
[Lightweight programming
languagnes](https://en.wikipedia.org/wiki/Lightweight_programming_language)

<a href="https://en.wikipedia.org/wiki/Wide_and_narrow_data" target="_blank">Table formats</a>

<a href="http://ggplot2.tidyverse.org" target="_blank"><code>ggplot2</code> package</a>  
Please see [this case
study](https://opencasestudies.github.io/ocs-bp-co2-emissions/) for more
details on using `ggplot2`  
<a href="http://vita.had.co.nz/papers/layered-grammar.html" target="_blank">grammar of graphics</a>  
<a href="https://ggplot2.tidyverse.org/reference/ggtheme.html" target="_blank"><code>ggplot2</code> themes</a>  
[Normalization](https://en.wikipedia.org/wiki/Normalization_(statistics))  
[Mann–Whitney–Wilcoxon (MWW)
test](https://en.wikipedia.org/wiki/Mann%E2%80%93Whitney_U_test) also
known as the Wilcoxon rank sum test or the two-sample Wilcox test

Also see
[here](https://www.stat.auckland.ac.nz/~wild/ChanceEnc/Ch10.wilcoxon.pdf)
for more information about this test and
[here](https://youtu.be/BT1FKd1Qzjw) for a video for a more detailed
explanation about performing this test by hand.

[Outliers](https://www.itl.nist.gov/div898/handbook/prc/section1/prc16.htm)  
[Normal
distribution](http://onlinestatbook.com/2/introduction/distributions.html)
[Q-Q plots](http://onlinestatbook.com/2/advanced_graphs/q-q_plots.html)
[Student’s
*t*-test](https://stattrek.com/statistics/dictionary.aspx?definition=two-sample%20t-test)  
[Confidence
interval](http://onlinestatbook.com/2/estimation/mean.html)  
[Sampling
distribution](https://en.wikipedia.org/wiki/Sampling_distribution)  
[Bootstrapping](https://en.wikipedia.org/wiki/Bootstrapping_(statistics))
[Resampling](https://en.wikipedia.org/wiki/Resampling_(statistics))

[Motivating report for this case
study](https://www.cdc.gov/mmwr/volumes/68/wr/pdfs/mm6802a1-H.pdf)

Also see this
[article](https://jamanetwork.com/journals/jamapsychiatry/fullarticle/1874575)
which surveyed heroin users in the [Survey of Key Informants’ Patients
Program](https://www.radars.org/radars-system-programs/survey-of-key-informants-patients.html)
and the [Researchers and Participants Interacting Directly (RAPID)
program](https://www.radars.org/radars-system-programs/researchers-and-participants-interacting-directly.html).

The data for this case study is available at this
[API](https://arcos-api.ext.nile.works/__swagger__/).

This data is from the [DEA](https://www.dea.gov/) [Automated Reports and
Consolidated Ordering System
(ARCOS)](https://www.deadiversion.usdoj.gov/arcos/retail_drug_summary/)
and was released by the [Washington
Post](https://www.washingtonpost.com/).

A wrapper package about this API is available
[here](https://github.com/wpinvestigative/arcos).

<u>**Packages used in this case study:** </u>

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
<td><a href="https://readxl.tidyverse.org/index.html">readxl</a></td>
<td>to import an excel file</td>
</tr>
<tr class="even">
<td><a href="https://httr.r-lib.org/">httr</a></td>
<td>to retrieve data from an API</td>
</tr>
<tr class="odd">
<td><a href="https://tibble.tidyverse.org/">tibble</a></td>
<td>to create tibbles (the tidyverse version of dataframes)</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/jsonlite/jsonlite.pdf">jsonlite</a></td>
<td>to parse json files</td>
</tr>
<tr class="odd">
<td><a href="https://stringr.tidyverse.org/" target="_blank">stringr</a></td>
<td>to manipulate character strings within the data (subset and detect parts of strings)</td>
</tr>
<tr class="even">
<td><a href="https://dplyr.tidyverse.org/" target="_blank">dplyr</a></td>
<td>to filter, subset, join, and modify and summarize the data</td>
</tr>
<tr class="odd">
<td><a href="https://magrittr.tidyverse.org/" target="_blank">magrittr</a></td>
<td>to pipe sequential commands</td>
</tr>
<tr class="even">
<td><a href="https://tidyr.tidyverse.org/" target="_blank">tidyr</a></td>
<td>to change the shape or format of tibbles to wide and long</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/naniar/vignettes/getting-started-w-naniar.html">naniar</a></td>
<td>to get a sense of missing data</td>
</tr>
<tr class="even">
<td><a href="https://ggplot2.tidyverse.org/" target="_blank">ggplot2</a></td>
<td>to create plots</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/formattable/formattable.pdf">formattable</a></td>
<td>to create a formatted table</td>
</tr>
<tr class="even">
<td><a href="https://forcats.tidyverse.org/" target="_blank">forcats</a></td>
<td>to reorder factor for plot</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/ggpol/ggpol.pdf">ggpol</a></td>
<td>to create plots that are have jitter and half boxplots</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/ggiraph/ggiraph.pdf">ggiraph</a></td>
<td>to create interactive plots</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/patchwork/patchwork.pdf">patchwork</a></td>
<td>to combine plots</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/directlabels/directlabels.pdf">directlabels</a></td>
<td>to add labels directly on lines within plots</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/usdata/usdata.pdf">usdata</a></td>
<td>to add full state names to plots based on the state abbreviations</td>
</tr>
</tbody>
</table>

If you or a loved one is struggling with opioid addiction, contact the
SAMHSA’s National Helpline at [1-800-662-HELP
(4357)](tel:1-800-662-HELP%20(4357)).

It is a free, confidential, 24/7, 365-day-a-year treatment referral and
information service (in English and Spanish) for individuals and
families facing mental and/or substance use disorders.

You can also contact the [Addiction
Center](https://www.addictioncenter.com/drugs/overdose/) at
[(877)871-3575](tel:877871-3575) which also has a confidential 24/7 live
chat at: <https://www.addictioncenter.com/drugs/overdose/>.

According to their website:

> Remember, that being able to treat an overdose at home is not a
> replacement for a hospital. Even if the moment has passed, and the
> victim seems fine, there is still a chance that something is going on
> that cannot be seen by the human eye. Taking the victim to the
> hospital, can mean the difference between life and death.

> Overdose is a scary word. We often associate it with death, but the
> two are not always connected. Life can go on after an overdose, but
> only if the person suffering understands and learns from it. Getting
> on the road to recovery is not easily done but it is always possible,
> and the only guaranteed way to never suffer an overdose again. If you
> don’t know where this path begins, or need help getting help for a
> loved one, please reach out to a dedicated treatment provider. They’re
> here, 24/7, to answer any questions you may have. Be it for yourself
> or someone else.

According to
[harmreduction.org](https://harmreduction.org/issues/overdose-prevention/overview/overdose-basics/recognizing-opioid-overdose/),
the following are signs of an overdose:

-   Loss of consciousness -Unresponsive to outside stimulus
-   Awake, but unable to talk
-   Breathing is very slow and shallow, erratic, or has stopped
-   For lighter skinned people, the skin tone turns bluish purple, for
    darker skinned people, it turns grayish or ashen.
-   Choking sounds, or a snore-like gurgling noise (sometimes called the
    “death rattle”)
-   Vomiting
-   Body is very limp
-   Face is very pale or clammy
-   Fingernails and lips turn blue or purplish black
-   Pulse (heartbeat) is slow, erratic, or not there at all

If someone is making unfamiliar sounds while “sleeping” it is worth
trying to wake him or her up. Many loved ones of users think a person
was snoring, when in fact the person was overdosing. These situations
are a missed opportunity to intervene and save a life.

Sometimes it can be difficult to tell if a person is just very high, or
experiencing an overdose. If you’re having a hard time telling the
difference, it is best to treat the situation like an overdose – it
could save someone’s life.

**The most important thing is to act right away!**

#### For users

There is a [`Makefile`](Makefile) in this folder that allows you to type
`make` to knit the case study contained in the `index.Rmd` to
`index.html` and it will also knit the [`README.Rmd`](README.Rmd) to a
markdown file (`README.md`).

The case study is designed to be modular, so for example if users wish
to skip Data Import and start with the Data Wrangling section they can
do so.

#### For instructors

The case study is designed to be modular, so for example, instructors
can skip sections like the Data Import, Data Wrangling, and Data
Visualization to start with the Data Analysis section if they wish.

Note: Monthly data about opioid shipments is also available within the
`data/extra` directory. This could be used for time series analysis.

#### Target audience

This case study is appropriate for those new to R programming. It is
also appropriate for more advanced R users who are new to the Tidyverse.
This particular case study may require some introductory knowledge of
statistics.

#### Suggested homework

Students could focus on the counties of a particular state and perform
the same analyses and visualizations to see how the different types of
counties compared for opioid pill shipments. Students could be asked to
work on different states. Discussion could follow about how and why the
states show different results.

#### Estimate of RMarkdown Compilation Time:

~ About 103 - 113 seconds

This compilation time was measured on a PC machine operating on Windows
10. This range should only be used as an estimate as compilation time
will vary with different machines and operating systems.
