# COVID-19-Modelling


## Tech Report
### *Where is the data from?*

Data on confirmed COVID-19 cases (including data on the number of recoveries and deaths) was obtained from the data repository for the 2019 Novel Coronavirus Visual Dashboard operated by the Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE). This is effort is also supported by ESRI Living Atlas Team and the Johns Hopkins University Applied Physics Lab (JHU APL).

#### How did you collect your data?

  COVID-19 data was collected by forking the Johns Hopkins COVID-19 GitHub repository and extracting information from the three time-series CSV files included (time_series_19-covid-Confirmed.csv, time_series_19-covid-Recovered.csv, time_series_19-covid-Deaths.csv). Daily incidence numbers (as well as the delta of incidences from day to day) for each province/state listed were then used to form a representative SQL table.

#### Is the source reputable?

  Yes, the source for the COVID-19 data is very reputable. Data in the COVID-19 data repository is amalgamated from a wide variety of professional and governmental sources. These include the World Health Organization (WHO), DXY.cn, BNO News, the National Health Commission of the People’s Republic of China (NHC), the China CDC (CCDC), the Hong Kong Department of Health, the Macau Government, the Taiwan CDC, the US CDC, the Government of Canada, the Australia Government Department of Health, the European Centre for Disease Prevention and Control (ECDC), the Ministry of Health Singapore (MOH), as well as the Italy Ministry of Health. The primary data source for the data repository is DXY, an online platform run by members of the Chinese medical community, which aggregates local media and government reports to provide cumulative totals of COVID-19 cases in near real time at the province level in China and at the country level otherwise. Every 15 min, the cumulative case counts are updated from DXY for all provinces in China and for other affected countries and regions. For countries and regions outside mainland China (including Hong Kong, Macau, and Taiwan), they found DXY cumulative case counts to frequently lag behind other sources; they therefore manually update these case numbers throughout the day when new cases are identified. To identify new cases, they monitor various Twitter feeds, online news services, and direct communication sent through the dashboard. Before manually updating the dashboard, they confirm the case numbers with regional and local health departments, including the respective centres for disease control and prevention (CDC) of China, Taiwan, and Europe, the Hong Kong Department of Health, the Macau Government, and WHO, as well as city-level and state-level health authorities. For city-level case reports in the USA, Australia, and Canada, they rely on the US CDC, the Government of Canada, the Australian Government Department of Health, and various state or territory health authorities. All manual updates (for countries and regions outside mainland China) are coordinated by a team at Johns Hopkins University.

#### How did you generate the sample? Is it comparably small or large? Is it representative or is it likely to exhibit some kind of sampling bias?

#### Are there any other considerations you took into account when collecting your data? This is open-ended based on your data; feel free to leave this blank. (Example: If it's user data, is it public/are they consenting to have their data used? Is the data potentially skewed in any direction?)

### *How clean is the data? Does this data contain what you need in order to complete the project you proposed to do? (Each team will have to go about answering this question differently, but use the following questions as a guide. Graphs and tables are highly encouraged if they allow you to answer these questions more succinctly.)*

The COVID-19 data is very clean, as it is closely monitored and updated every single day by JHU CSSE. The CSV files used to obtain our ultimate SQL table are neatly formatted. As the name implies, the values in these files are separated by commas, making the reading in and parsing of the data very simple and straightforward. This COVID-19 table contains nearly all we need in order to complete our proposed project, as it provides information about the number of infected indiviudals, the number of individuals who have recovered, as well as the number of individuals who have died as a result of COVID-19, with all that remains to be determined is the number of people susceptible to the disease (which can be calculated using the relevant province/state/country populations.

#### How many data points are there total? How many are there in each group you care about (e.g. if you are dividing your data into positive/negative examples, are they split evenly)? Do you think this is enough data to do what you hope to do?

The initial Johns Hopkins CSVs contain 199 rows of data, with each row representing cases of COVID-19 at the province level in China; at the city level in the USA, Australia, and Canada; and at the country level otherwise. For each row, there's a column demarcating the relevant province/state, the relevant country/region, the latitude, the longitude, and incidence numbers for every date until the present starting at January 22nd, 2020. The repository is updated daily, with a column being added accordingly. Since we care about three primary groups with regard to our COVID-19 data -- confirmed COVID-19 cases, recovered COVID-19 cases, and fatal COVID-19 cases -- and there is one CSV file for each of these groups, we essentially have 199 rows for each group we care about, with the number of data points continuing to increase each day (since the data repository is updated daily and began recording on January 22nd, 2020). Since we have hundreds of provinces/states to work with, and our data points are continuing to update and increase on a daily basis, we are confident that we have enough data to do what we hope to do.

#### Are there missing values? Do these occur in fields that are important for your project's goals?
There do not appear to be any missing values whatsoever, so there is no consequent effect on our project's goals.

#### Are there duplicates? Do these occur in fields that are important for your project's goals?
There do not appear to be any duplicates whatsoever, so there is no consequent effect on our project's goals.

#### How is the data distributed? Is it uniform or skewed? Are there outliers? What are the min/max values? (focus on the fields that are most relevant to your project goals)

#### Are there any data type issues (e.g. words in fields that were supposed to be numeric)? Where are these coming from? (E.g. a bug in your scraper? User input?) How will you fix them?

#### Do you need to throw any data away? What data? Why? Any reason this might affect the analyses you are able to run or the conclusions you are able to draw?

### *Summarize any challenges or observations you have made since collecting your data. Then, discuss your next steps and how your data collection has impacted the type of analysis you will perform. (approximately 3-5 sentences)*
