# DATA512-A1: DATA512 course assignment 1
The goal of this project is to construct, analyze, and publish a dataset of monthly traffic on English Wikipedia from January 1 2008 through August 30 2019.

### Data Source
The data about Wikipedia page traffic from two different [Wikimedia REST API](https://www.mediawiki.org/wiki/REST_API) endpoints have been combined into a single dataset.

**Two different API endpoints have been used for data acquision:**
- Legacy Pagecounts API ([documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts)): It contains the view counts from desktop and mobile traffic from December 2007 through July 2016.
- Pageviews API ([documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews)): It contains the view counts from desktop, mobile web and mobile app traffic data from July 2015 till the present month.

_Note:_
- The Pageview API allows us to filter out the traffic from web crawlers and spiders by specifying ```agent=user```, but this support is not present in the Legacy Pagecounts API.
- There is 13 months of overlapping traffic data between the two APIs.
- The name of few keys varies across the APIs: Pagecounts API result contains the view counts in the key 'count', whereas the Pageviews API has the view counts in the key 'views'.

**Licence:** Please read the licence and terms of use of Wikimedia Foundation REST API from [here](https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions).

### Aggregated Final Data
The final data is present in the file ```en-wikipedia_traffic_200801-201908.csv```.

**Description of fields of the final data:**
The following are the fields of this data:
- _year_: The year in the YYYY format.
- _month_: The month in MM format.
- _pagecount_all_views_: The view counts from both desktop and mobile collected from Legacy Pagecounts API.
- _pagecount_desktop_views_: The number of views from desktop collected from Legacy Pagecounts API.
- _pagecount_mobile_views_: The number of views from mobile collected from Legacy Pagecounts API.
- _pageview_all_views_: The number of views from desktop, mobile-web and mobile-app users collected from Pageviews API.
- _pageview_desktop_views_: The number of views from desktop users collected from Pageviews API.
- _pageview_mobile_views_: The number of views from mobile-web and mobile-app users collected from Pageviews API.

### Analysis
The following graphs shows a simple exploratory analysis of the aggregated final data.
![alt text](https://github.com/bhuvi3/DATA512-A1/blob/master/en-wikipedia_traffic_200801-201908.png)

**Note:** From May 2015, a new pageview definition took effect, which eliminated all crawler traffic. Solid lines mark new definition.
