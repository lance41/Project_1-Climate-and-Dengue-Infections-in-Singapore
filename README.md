# Project 1: Exploring Climate Data and Dengue Infections of Singapore 

### Overview

In an article on ChannelNewsAsia [Rising temperatures could increase risk of new infectious diseases in Singapore: Experts](https://www.channelnewsasia.com/singapore/climate-change-infectious-diseases-zika-monkeypox-dengue-singapore-2973651#:~:text=In%20recent%20years%2C%20Singapore%20has,of%202021%2C%20which%20was%205%2C258.), it mentions that there is studies that found that infectious diseases are exacerbated by climate change. These infectious diseases include dengue and zika which are seeing record rising numbers with rising temperatures in Singapore. 

Some secondary research may point to similar conclusions: 

1. Based on a study conducted by a group of Iranian researchers [Climate Change and Infectious Diseases: Evidence from Highly Vulnerable Countries](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6974868/), the conclusion was temperature has a positive relationship with the number of patients affected from infectious diseases. Similarly, population density had similar effects on patients; however, income was statistically insignificant. Negative impact of education with reference to the number of patients was found where the increase in awareness will facilitate the people to take preventive measures to avoid infectious diseases.

2. Based on a study conducted by a group of Chinese reasearchers [The effect of temperature on dengue virus transmission by Aedes mosquitoes](https://www.frontiersin.org/articles/10.3389/fcimb.2023.1242173/full#:~:text=Abundant%20studies%20indicated%20that%20temperature,et%20al.%2C%202022).), Abundant studies indicated that temperature was positively correlated with dengue cases (Fan et al., 2014). The most suitable minimum temperature for the transmission of DENV is 14.8°C (Feldstein et al., 2015), while the optimal maximum temperature ranges from 32°C to 33°C (Stephenson et al., 2022).

Based on these three studies, we can probably see that Singapore, being a tropical country, would likely have a strong increase in dengue numbers as temperature increases (ie. positive correlation).

---
### Problem Statement

The problem statement is "Examine the relationship between specific climate-related variables and the incidence of dengue cases":

**<center>Singapore experiences varying weather conditions, predominantly sunny or rainy, which may increase the risks of contracting dengue. This project aims to analyze trends in Singapore weather and dengue fever incidence across different regions to identify high-risk areas and vulnerable populations prone to dengue outbreaks under specific weather conditions. By leveraging exploratory data analysis techniques, the objective is to uncover patterns, trends, and correlations in the data.</center>**

This analysis will provide actionable insights for urban planning, mosquito control efforts, and public health campaigns aimed at mitigating the spread of dengue fever in identified hotspots.

---
### Datasets

For this project, I'll be using a number of weather datasets from data.gov.sg. These are:
1. **Monthly Total Rainfall**: Measure of monthly total rainfall from 1982 to 2022
2. **Monthly Number of Rain Days**: Measure of number of rainy days from 1982 to 2022
3. **Monthly Mean Surface Air Temperature**: Measure of monthly mean surface air temperature from 1982 to 2022
4. **Monthly Mean Sunshine Duration**: Measure of mean sunshine hours 1982 to 2022
5. **Monthly Mean Relative Humidity**: Measure of monthly mean relative humidity from 1982 to 2022

In addition, I'll be using a dataset from data.gov.sg:
1. **Weekly Number of Dengue and Dengue Haemorrhagic Fever Cases**: Measure of weekly dengue and dengue haemorrhagic fever cases from 2014 to 2018

---

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|number|float|Weekly-Number-of-Dengue-and-Dengue-Haemorrhagic-Fever-Cases|Weekly dengue numbers| 
|total_rainfall|float|rainfall-monthly-total|Total rainfall in mm| 
|no_of_rainy_days|integer|rainfall-monthly-number-of-rain-days|Monthly number of rain days| 
|mean_temp|float|surface-air-temperature-monthly-mean|Monthly mean surface air temperature| 
|mean_sunshine_hrs|float|SunshineDurationMonthlyMeanDailyDuration|Monthly mean sunshine hours per day| 
|mean_relative_humidity|float|relative-humidity-monthly-mean|Monthly mean relative humidity| 


---

### Summary of Analysis

Based on our heatmap, we see a mild positive correlation between the dengue infection numbers, with the mean temperature of the month, with a correlation coefficient of 0.23. We also see a milder correlation with the mean sunshine hours at 0.12. There are negative correlation between the dengue infection numbers with the number of rainy days and total rainfall with the correlation coefficients of -0.21 and -0.15 respectively.  

Based on our boxplots and outlier calculations, there are a couple of outliers in the distribution of dengue numbers. This could possibly skew calculations of mean and standard deviation for the dengue numbers

---

### Conclusions / Recommendations

Based on our data exploration exercise, we have found the following:
1. There is a mild positive correlation between the mean monthly temperature in Singapore, as well as the number of dengue cases. Based on the linear best fit line, an increase in 1 degree in temperature will result an increase in the number of dengue cases of 220 on average.
2. The distribution of number of dengue cases and the total monthly rainfall is positively skewed (right skewed) with a greater concentration of data on the left side while the distributions of mean temperature is left skewed.
3. There are anomalies in the distribution of number of dengue cases (outliers).

Due to the mild positive correlation between number of dengue cases and mean temperature, we can expect that there will be an increase in the number of dengue cases as temperature rises. With the current fluctuations of weather in the short term, coupled by the continued global warming long term, it is paramount for the government to ensure that these are taken into account when doing capacity planning in health resources both in the short and long run.

However, do note that correlation does not imply causation, and more studies need to be done in order to identify other factors that affect the number of dengue cases. Additionally, there might be other factors that are correlated with both temperature and the number of dengue cases that are true causal factors of the latter.

Based on the results, I would recommend the following next steps:
1. Clean the data of outliers, and plot the graphs again to see if there's a stronger correlation between the mean temperature and the number of dengue cases, as well as an improved R^2 value.
2. Understand the relationship between temperature and number of dengue cases on a more granular level, by breaking down into different dengue clusters as well as different serotypes for these dengue cases.
3. Build machine learning models to predict possible future temperature fluctuations and trends, and include these predictions in the planning of health resources for Singapore.