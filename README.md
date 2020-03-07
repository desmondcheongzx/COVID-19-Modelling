# COVID-19-Modelling


## Tech Report
### - *Where is the data from?*

Data on confirmed COVID-19 cases (including data on the number of recoveries and deaths) was obtained from the data repository for the 2019 Novel Coronavirus Visual Dashboard operated by the Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE). This is effort is also supported by ESRI Living Atlas Team and the Johns Hopkins University Applied Physics Lab (JHU APL).

###   - *How did you collect your data?*

  COVID-19 data was collected by forking the Johns Hopkins COVID-19 GitHub repository and extracting information from the three time-series CSV files included (time_series_19-covid-Confirmed.csv, time_series_19-covid-Recovered.csv, time_series_19-covid-Deaths.csv). Daily incidence numbers (as well as the delta of incidences from day to day) for each province/state listed were then used to form a representative SQL table.

###   - *Is the source reputable?*

  Yes, the source is very reputable. Data in the COVID-19 data repository is amalgamated from a wide variety of professional and governmental sources. These include the World Health Organization (WHO), DXY.cn, BNO News, the National Health Commission of the People’s Republic of China (NHC), the China CDC (CCDC), the Hong Kong Department of Health, the Macau Government, the Taiwan CDC, the US CDC, the Government of Canada, the Australia Government Department of Health, the European Centre for Disease Prevention and Control (ECDC), the Ministry of Health Singapore (MOH), as well as the Italy Ministry of Health. The primary data source for the data repository is DXY, an online platform run by members of the Chinese medical community, which aggregates local media and government reports to provide cumulative totals of COVID-19 cases in near real time at the province level in China and at the country level otherwise. Every 15 min, the cumulative case counts are updated from DXY for all provinces in China and for other affected countries and regions. For countries and regions outside mainland China (including Hong Kong, Macau, and Taiwan), they found DXY cumulative case counts to frequently lag behind other sources; they therefore manually update these case numbers throughout the day when new cases are identified. To identify new cases, they monitor various Twitter feeds, online news services, and direct communication sent through the dashboard. Before manually updating the dashboard, they confirm the case numbers with regional and local health departments, including the respective centres for disease control and prevention (CDC) of China, Taiwan, and Europe, the Hong Kong Department of Health, the Macau Government, and WHO, as well as city-level and state-level health authorities. For city-level case reports in the USA, Australia, and Canada, they rely on the US CDC, the Government of Canada, the Australian Government Department of Health, and various state or territory health authorities. All manual updates (for countries and regions outside mainland China) are coordinated by a team at Johns Hopkins University.

###   - *How did you generate the sample? Is it comparably small or large? Is it representative or is it likely to exhibit some kind of sampling bias?*

###   - *Are there any other considerations you took into account when collecting your data? This is open-ended based on your data; feel free to leave this blank. (Example: If it's user data, is it public/are they consenting to have their data used? Is the data potentially skewed in any direction?)*

### - *How clean is the data? Does this data contain what you need in order to complete the project you proposed to do? (Each team will have to go about answering this question differently, but use the following questions as a guide. Graphs and tables are highly encouraged if they allow you to answer these questions more succinctly.)*

###   - *How many data points are there total? How many are there in each group you care about (e.g. if you are dividing your data into positive/negative examples, are they split evenly)? Do you think this is enough data to do what you hope to do?*

###   - *Are there missing values? Do these occur in fields that are important for your project's goals?*

###   - *Are there duplicates? Do these occur in fields that are important for your project's goals?*

###   - *How is the data distributed? Is it uniform or skewed? Are there outliers? What are the min/max values? (focus on the fields that are most relevant to your project goals)*

###   - *Are there any data type issues (e.g. words in fields that were supposed to be numeric)? Where are these coming from? (E.g. a bug in your scraper? User input?) How will you fix them?*

###   - *Do you need to throw any data away? What data? Why? Any reason this might affect the analyses you are able to run or the conclusions you are able to draw?*

### - *Summarize any challenges or observations you have made since collecting your data. Then, discuss your next steps and how your data collection has impacted the type of analysis you will perform. (approximately 3-5 sentences)*
