# climate-population-growth-1990-2020
# The Influence of Climate on Population Growth in Eight Countries, 1990–2020

## Group members
- Yeye Jin
- Antony Taylor

- ## Colab worksheet
- View on Colab: [https://colab.research.google.com/……](https://colab.research.google.com/drive/1Q5onDLpXZELtnoQGucZNWDMvxwn0eLoA?usp=sharing)
- Notebook file: `Data_Science_Final.ipynb`



## Introduction
This project investigates whether a country’s climate is related to how fast its population grows. The main questions are, first, whether changes in climate and population growth appear to move together over time within a country, and second, whether countries with warmer climates tend to have higher average population growth than cooler countries.
	The analysis focuses on eight countries that span a range of climates and development levels: The Bahamas, China, Ethiopia, India, Japan, Nigeria, Tanzania, and South Africa. Monthly country-average temperature data come from the World Bank’s Climate Change Knowledge Portal (CRU TS 0.5-degree collection), which aggregates observed station data on a 0.5° by 0.5° grid over land areas (World Bank, Climate Change Knowledge Portal; “CRU TS”). Annual population data are taken from the “Population with UN projections” series provided by Our World in Data, which is based on the United Nations World Population Prospects (Our World in Data; United Nations, DESA, Population Division). GDP per capita data, when used, follow the World Bank World Development Indicators as distributed by Our World in Data.
	The raw climate files contain monthly means for every country from 1901 onward. For this project, the time span is restricted to 1990–2020 and to the eight selected ISO-3 country codes. The data are reshaped into a tidy format with one row per country–year–month, and for each country–year the annual mean, minimum, and maximum of the monthly temperatures are calculated. The population file is trimmed to the same years and countries, and the “estimates” series is used to construct annual population change and population growth rates. After cleaning, the climate and population tables are merged by country code and year, so that each row of the analysis dataset contains both climate summaries and population outcomes.


## Methods and Results
First, I plotted the annual mean temperature against the year for all eight countries. This confirmed that temperatures fluctuate within a relatively narrow band and, in most countries, show a slight upward trend over 1990–2020. Next, I added annual population levels to the same graph, using a second vertical axis. For example, in the graph for The Bahamas, population increases almost smoothly over time while the temperature series moves up and down around its mean. Visually, the two lines do not move together in a way that suggests a simple, short-run relationship between the level of population and annual mean temperature.


To see more of the variation in the climate data, I then calculated, for each country and year, the minimum and maximum of the twelve monthly temperatures. Plotting the annual mean temperature together with the yearly minimum and maximum creates a band that shows the full range of typical conditions in each year. Although this graph gives a better sense of how hot and cool years differ, the population series still increases steadily and does not track the climate band in any obvious way. It remains difficult to see any direct link between temperature levels and population levels in the time-series plots. Because population levels are trending upward almost everywhere, I turned to population change instead. For each country, I computed the annual change in population by subtracting the previous year’s population from the current year’s value. I then graphed population change and annual mean temperature together over time:
 
This transformation allows the population to move up and down from year to year, making it easier to compare with climate fluctuations. However, the resulting graphs again show no clear co-movement: years with relatively high population increases do not consistently line up with unusually hot or unusually cool years. This pattern is the same across all eight countries.
Since the within-country time-series approach did not reveal a strong relationship, I shifted to a cross-country view. I summarized the data by computing, for each of the eight countries, the average annual temperature and the average annual population growth rate over the period 1990–2020. 

	Plotting these eight points on a scatterplot of mean population growth versus mean temperature reveals a clear upward trend: warmer countries such as Ethiopia, Tanzania, Nigeria, India, and The Bahamas have higher average population growth, while cooler countries such as Japan and China have much lower growth, with South Africa in between. Adding an ordinary least squares trendline emphasizes this pattern.
To quantify the strength of this relationship, I calculated the Pearson correlation coefficient between average temperature and average population growth across the eight countries using:
corr=country_summary["mean_temp"].corr(country_summary["mean_pop_growth"]). The result is r= 0.71, which indicates a fairly strong positive linear association. In this small sample, roughly half of the variation in average population growth between countries can be associated with differences in their average temperatures (since r2≈0.50). This contrast between weak year-to-year associations and a strong cross-country association is the main finding of the project.

## Conclusion
(paste Conclusion)
