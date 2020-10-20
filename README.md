# Treatments analysis (Which is the best?)

## By Rodrigo Guarneros

Note: In order to attend the analysis requierements and give an screen shot about the results. I start here with the technical executive report and the top-level summary. After this both sections, you'll find every data analysis and code in python so as to replicate results.

# Technical report
### ✏️ Exploring datasets and cleaning process:
Having in mind the objective: "Compare the performance of Pymaceutical's drugs of interest", based on an study with 249 mice which were monitored so as to know their evolution over the course of 45 days.

The dataset "mouse_metadata" is perfect because there is not missing values, there are 249 unique mice and is ready to joint with the other dadaset.

The dataset "study_results" has also valuable information regarding the evolution of each mice inside the mouse_metadata dataset, it brings us 1,893 observations relted with the evolution about every mice, but there is some risks (v.gr. duplicated observations).

First, those dataset were explored with descriptive statistics before a cleaning process, following the next steps:

Look for dimension of each dataset
Know, as far as possible, each dataset and the information available in each column as well as the class of information
Look for missing data
Look for duplicated observations
Merge both datasets with "left" criteria in order to get all the information
Identify every duplicate observation in Mouse ID and Timepoint
Drop duplicated observations so as to get a cleaned data frame. This point was crucial. Having in mind that duplicated()return a boolean serie denoting duplicate rows, see documentation.

### ✏️ Main findings:
As was said, the test considers 249 mice divided in 10 drug treatments, including a placebo regimen. With almost the same proportion by gender and number of mice.

image info

Every mice was monitored during a period of 45 days in order to get the evolution the following variables: Tumor Volume (mm3) and Metastatic Sites. With an average age of 12.8 months and weight average of 25 grams.

The standard error o the mean (SEM) describes how far a sample's mean is from the population's "true" mean.

The first fact finded shows that, having in mind that the SEM is descriptive of the random sampling process. In other words, is a probabilistic statement about how the sample size will provide a better bound on estimates of the population mean, thinking on the central limit theorem, we can see that SME is relatively lower regarding Tumor Volume (mm3) for two drug regimens, which means they are relatively more near from the poblational mean: Ramicane (0.320955) and Capomulin (0.329346).

The rate of mortality in several drug regimens are less than others. Particularly in Capomulin (4 mice of 25) and Ramicane (5 mice of 25). Even considering the Placebo Regimen, there are worst regimens such as: Propriva, Infubinol, Ketapril and Stelasyn.

image info

In order to identify the promising regimens, the distributions and means of each drug tested were compeared, finding as the most promising the following:
- Capomulin
- Ramicane
- Propriva
- Infubinol

![Alt Text](https://github.com/RodGuarneros/Pymaceuticals/blob/main/RegimenComp.png)

Even, the distribution for those champions does not present outliers that we should manage.

Based on the measures of central tendency and boxplots, the promising treatments have the folowing distributions, means and standar deviation.

image info

Based also on the measures of central tendency and boxplots, the promising treatments have the folowing distributions, means and standar deviation.

The reduction of the tumor volume is sustainded in every mice subject to Capomulin regime (with only one exception).

image info

There is a strong linear relationship between weaight and tumor volume (R2=0.70). Although this does not necessarily imply causality, it is suggested that the weight of the subjects should be very similar.

image info

## Top-level summary

- In terms of rate mortality the best treatment is Capomulin.

- The average reduction in tumor volume attributed to Capomulin is very similar to that registered for the best regimen tested (Ramicane).

- Capomulin is a serious contender in the market for Ramicane.

- There is no comparison with the rest of the treatments, Capomulin and Ramicane do present significant and sustained results reducing tumor volume.

- The weight seems to be a driver for the tumor volume, this result is important considering that every mice should have the same opportunity of gain weight so as to avoid bias the research.


