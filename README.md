# COVID-19-Modelling (nrshaida, rmani1, tphilli6, dcheong)

## Complete Data Specification

Included in "dataspec" file (in project_data directory)

## Link to Full Data in Downloadable Form

https://github.com/desmondcheongzx/COVID-19-Modelling

## Sample Data

Included in "sample.db" file (in project_data directory)
Can utilize http://sqliteonline.com/ for easy visualization of tables as needed.

## Tech Report
### *Where is the data from?*

Data on confirmed COVID-19 cases (including data on the number of recoveries and deaths) was obtained from the data repository for the 2019 Novel Coronavirus Visual Dashboard operated by the Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE). This is effort is also supported by ESRI Living Atlas Team and the Johns Hopkins University Applied Physics Lab (JHU APL).

The population data was compiled from multiple sources based on relevancy and availability. Most country tables were obtained from worldpopulationreview.com, a website that posts population tables from UN sources. The UN, in turn, generates this data using country censuses and estimates modern-year values using historical trends. Canada was an exception, their data had to come directly from a government website. The only other source used was simplemaps, used for mapping countries to cities as well as providing a host of data about them. They get their data from sources like "NGIA, US Geological Survey, US Census Bureau, and NASA". 

#### How did you collect your data?

COVID-19 data was collected by forking the Johns Hopkins COVID-19 GitHub repository and extracting information from the three time-series CSV files included (time_series_19-covid-Confirmed.csv, time_series_19-covid-Recovered.csv, time_series_19-covid-Deaths.csv). Daily incidence numbers (as well as the delta of incidences from day to day) for each province/state listed were then used to form a representative SQL table.

We downloaded csv files for most of the countries from our websites, which we then used to generate sql databases. Currently, we have each country assigned to their own table. The extra data, like country density and city information, were given their own tables as well. 

#### Is the source reputable?

Yes, the source for the COVID-19 data is very reputable. Data in the COVID-19 data repository is amalgamated from a wide variety of professional and governmental sources. These include the World Health Organization (WHO), DXY.cn, BNO News, the National Health Commission of the People’s Republic of China (NHC), the China CDC (CCDC), the Hong Kong Department of Health, the Macau Government, the Taiwan CDC, the US CDC, the Government of Canada, the Australia Government Department of Health, the European Centre for Disease Prevention and Control (ECDC), the Ministry of Health Singapore (MOH), as well as the Italy Ministry of Health. The primary data source for the data repository is DXY, an online platform run by members of the Chinese medical community, which aggregates local media and government reports to provide cumulative totals of COVID-19 cases in near real time at the province level in China and at the country level otherwise. Every 15 min, the cumulative case counts are updated from DXY for all provinces in China and for other affected countries and regions. For countries and regions outside mainland China (including Hong Kong, Macau, and Taiwan), they found DXY cumulative case counts to frequently lag behind other sources; they therefore manually update these case numbers throughout the day when new cases are identified. To identify new cases, they monitor various Twitter feeds, online news services, and direct communication sent through the dashboard. Before manually updating the dashboard, they confirm the case numbers with regional and local health departments, including the respective centres for disease control and prevention (CDC) of China, Taiwan, and Europe, the Hong Kong Department of Health, the Macau Government, and WHO, as well as city-level and state-level health authorities. For city-level case reports in the USA, Australia, and Canada, they rely on the US CDC, the Government of Canada, the Australian Government Department of Health, and various state or territory health authorities. All manual updates (for countries and regions outside mainland China) are coordinated by a team at Johns Hopkins University.

As for the population data, The UN is the foremost source on country statistics (it's their job), so there probably isn't a more reputable source. We trust the distributors (worldpopulationreview and similar) to deliver accurate versions of the data. 

#### How did you generate the sample? Is it comparably small or large? Is it representative or is it likely to exhibit some kind of sampling bias?

This project does not really involve any sort of sampling. The COVID-19 data we get (number of infections, deaths, and recovered) pertains to the global population and is consistently updated. Additionally, a big part of our data is solely population numbers to help us obtain the number of susceptible individuals 

#### Are there any other considerations you took into account when collecting your data? This is open-ended based on your data; feel free to leave this blank. (Example: If it's user data, is it public/are they consenting to have their data used? Is the data potentially skewed in any direction?)

When collecting and cleaning our data, we took into account areas of geopolitical tensions and if/how they were represented in our data. To deal with these complex issues, as a general guiding principle we aimed to be as inclusive as possible, whenever possible. For example, China did not include Tibet, so we personally took it upon ourselves to add Tibet. In the country_population data from the UN data Taiwan was labeled as Taiwan (Province of China), which we felt was not fair for Taiwan (in addition to it generation some very weird edge cases), so we changed it to just Taiwan.

Another consideration we had to make was with regard to the accuracy of the number of reported incidences of COVID-19. Although we know our data source is reputable, the numbers reported by the U.S. CDC and those of countries across the globe might not be one hundred percent accurate (due to human error, politics, etc.). Since this is outside of the scope of our project, for the sake of this project, we are assuming that all reported numbers are accurate.

### *How clean is the data? Does this data contain what you need in order to complete the project you proposed to do? (Each team will have to go about answering this question differently, but use the following questions as a guide. Graphs and tables are highly encouraged if they allow you to answer these questions more succinctly.)*

The COVID-19 data is very clean, as it is closely monitored and updated every single day by JHU CSSE. The CSV files used to obtain our ultimate SQL table are neatly formatted. As the name implies, the values in these files are separated by commas, making the reading in and parsing of the data very simple and straightforward. This COVID-19 table contains nearly all we need in order to complete our proposed project, as it provides information about the number of infected indiviudals, the number of individuals who have recovered, as well as the number of individuals who have died as a result of COVID-19, with all that remains to be determined is the number of people susceptible to the disease (which can be calculated using the relevant province/state/country populations.

The population data is also very clean. This largely results from the distributor websites having cleaned the data already. What we download is complete and fully formatted. The data indeed contains what we need to do in order to complete, since these population numbers will largely be used as starting points for our simulation. The one inconsistency is that some of the tables comes from different years, but the difference is so miniscule that it won't really affect the end results of our project. In addition, there were some special cases 
we thought were worth noting. They are: 

-Australia 2019, by state
-China (provinces) 2018
-China (cities) 2020
-Canada (provinces) 2019
-Tibet 2010

Most of our country tables use solely cities, not provinces, so we may need to account for that somehow. The reason for Tibet is that governmental issues prevent them from showing statistics from after 2010. 

#### How many data points are there total? How many are there in each group you care about (e.g. if you are dividing your data into positive/negative examples, are they split evenly)? Do you think this is enough data to do what you hope to do?

The initial Johns Hopkins CSVs contain 199 rows of data, with each row representing cases of COVID-19 at the province level in China; at the city level in the USA, Australia, and Canada; and at the country level otherwise. For each row, there's a column demarcating the relevant province/state, the relevant country/region, the latitude, the longitude, and incidence numbers for every date until the present starting at January 22nd, 2020. The repository is updated daily, with a column being added accordingly. Since we care about three primary groups with regard to our COVID-19 data -- confirmed COVID-19 cases, recovered COVID-19 cases, and fatal COVID-19 cases -- and there is one CSV file for each of these groups, we essentially have 199 rows for each group we care about, with the number of data points continuing to increase each day (since the data repository is updated daily and began recording on January 22nd, 2020). Since we have hundreds of provinces/states to work with, and our data points are continuing to update and increase on a daily basis, we are confident that we have enough data to do what we hope to do.

For the population data, we chose the selected countries because they were the top 10 countries hit by coronavirus. Most tables' number of rows are simply the number of cities we have for that country, but in total we have 19973 rows, with the vast majority coming from city_country, because that table encompasses all the cities in the world. I think we have more than enough data. 

#### Are there missing values? Do these occur in fields that are important for your project's goals?

There do not appear to be any missing values whatsoever, so there is no consequent effect on our project's goals. The question is not relevant to our data. 

#### Are there duplicates? Do these occur in fields that are important for your project's goals?

There do not appear to be any duplicate values whatsoever, so there is no consequent effect on our project's goals. The question is not relevant to our data. 

#### How is the data distributed? Is it uniform or skewed? Are there outliers? What are the min/max values? (focus on the fields that are most relevant to your project goals)

For the most part, our COVID-19 data seems to be normally and uniformly distributed (incidences per day increasing and decreasing roughly along a bell curve). There are some outliers, such as countries that are continuing to face increasing incidences per day (for example, South Korea), but at the end of the day, the data for these countries may end up being uniformly distributed anyways as data continues to accumulate and time goes on. Our maximum values by far are definitely obtained from the Hubei province in China, which serves as the epicenter of the COVID-19 crisis. Our minimum values are obtained from countries/states/provinces that have a single incidence of COVID-19 (since our dataset only includes those countries that have at least one such case). As of March 9th, 2020, these include the country of Brunei, as well as the following U.S. counties: Bennington County, VT; Carver County, MN; Charlotte County, FL; Cherokee County, GA; Collin County, TX; Jefferson County, KY; Jefferson Parish, LA; Shasta County, CA; and Spartanburg County, SC.

#### Are there any data type issues (e.g. words in fields that were supposed to be numeric)? Where are these coming from? (E.g. a bug in your scraper? User input?) How will you fix them?

In the initial Johns Hopkins CSVs, column data for particular states/provinces only exist for China, USA, Australia, and Canada, so the corresponding column was left blank for all other countries. To deal with this, in the SQL database we generated, we appended the row value for province/state with the row value for country/region to generate a complete, unique identifier for each row of data.

There was very little trouble involved in the population data because the websites provided them free in csv format. 

#### Do you need to throw any data away? What data? Why? Any reason this might affect the analyses you are able to run or the conclusions you are able to draw?

With regard to the COVID-19 data, we will have to eliminate the very first date (January 22nd, 2020) since we are dealing with change in numbers per day (and the first date recorded doesn't have any numbers for the day prior (it would not make sense to suddently jump from 0 to 4000, for example) because the data repository wasn't constructed the day of the very first coronoavirus incidence back in 2019.

We may need to throw away most of the data in city_country, simply because it contains data on so many cities that aren't in our tables for infection rates. 

### *Summarize any challenges or observations you have made since collecting your data. Then, discuss your next steps and how your data collection has impacted the type of analysis you will perform. (approximately 3-5 sentences)*

Some of the challenges we anticipate as a result of our data are due to the fact that there are differences in country/state/province names across tables, as our COVID-19 database is obtained from a completely separate data source than our population database. Additionally, we anticipate some issues that may arise due to the fact that some row identifiers are represented by country, some by state, some by province, and some by city so we will have to determine a way to normalize these representations. We also realize that we will have to be flexible in our upcoming statistical analysis, since data is continuously being updated and added each and every day, meaning that conclusions we make at one point in time may not be relevant at another, for instance. Data collection has significantly impacted the type of analysis we will perform, since we were unable to find free/cheap and comprehensive travel data, thus prohibiting us from testing for the correlation between global travel and rate of COVID-19 spread.
