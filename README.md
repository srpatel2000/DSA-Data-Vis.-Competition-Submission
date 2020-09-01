# Data Science Alliance Data Visualization Competition Submission

# Medium Article Webscraper
The Medium-Webscraping notebook contains code that webscrapes [medium.com](https://medium.com/) in order to gain key variables about articles written under the 'Data Science' tag. This webscraper scrapes the following variables related to an article:
- __title__: Title of the article
- __article_url__: URL link to the article
- __claps__: The number of claps
- __reading_time__: The time it takes to read the article in minutes
- __date__: The date that the article was published 
- __tag_list__: Other tags that the article uses other than 'Data Science'

Ultimately I used this data (look at the Data-Manipulation notebook for more info) to enter into the Data Science Alliance's Data Visualization Competition. I created a parallel coordinates plot and a bubble chart to convey different things. Here is the [final visualization](https://public.tableau.com/profile/siddhi.patel5749#!/vizhome/MediumExploratoryDataAnalysis/Dashboard1?publish=yes).

### Code Overview
The webscraper is built on Python using BeautifulSoup and Selenium to scrape the medium archives and articles themselves. The data listed above is extracted via the archive and individual article links. 

### Future Improvements
* This code takes a while to run since it has to parse over 200 articles for every day of the month. One URL is not being parsed, but rather 200 per day of the month. In order to minimize the runtime I used the following tactics:
    1. I automated a random start and end date of the month so that not every day is taken into account
    2. I used SoupStrainer on the lxml code to only parse relevant parts of the page
    
  Even then, the code took 24+ hours to run. In order to decrease run time, grabbing related article tags can be eliminated since this is the part of the code that   parses different lxml sources. However, I want to decrease runtime in the future without having to eliminate any parts of the code. 

* In the Python script, some tags are being extracted incorrectly. Instead the headers of paid articles for 'Towards Data Science' are being extracted. Although this was filtered out in the Data-Manipulation notebook, this could cause anyone using the script code to obtain incorrect information. 

### Sources: 
[1] https://github.com/harrisonjansma/Medium_Scraper

[2] https://medium.com/the-innovation/scraping-medium-with-python-beautiful-soup-3314f898bbf5
