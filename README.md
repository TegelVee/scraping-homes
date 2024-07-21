# Scraping home sales in Helsinki

## My goal:
I wanted to practice scraping by getting house sales data from Asuntojen hintatiedot webpage. https://asuntojen.hintatiedot.fi/haku/ It is a database provided by the Finnish Ministry of the Environment, and the data is produced by five big realtors. My aim was to get all data of apartments sold in Helsinki by scraping the page with requests using python in VS Code and analyze it using pandas.

## Data collection:
I used requests and BeautifulSoup. On the webpage, the Helsinki data was split on over 40 tabs, which all needed to be fetched to get a comprehensive dataset. Each tab had its own URL and on each tab the data was in table format.

## Data cleaning and analysis:
The data required a lot of cleaning, because of extra characters and the fact that the data is entered in the system by individual real estate brokers, which makes it somewhat disorganized. I used many basic tools for cleaning (e.g. .isna, .dropna, .replace and changing column types with .astype). I also created new columns in the data frame.

I had dozens of interesting questions that I wanted to ask my data, e.g. I checked what kind where the most expensive and cheapest flats. First, I wanted to do mapping, but I would have needed more time for cleaning, because there were no postal codes in my data. Also, the result could have been misleading.

Eventually I decided to find an answer to a debate concerning modern home sizes. I asked the data, have homes built since 2010 been smaller than earlier. Even though my data does not include all homes existing in Helsinki, it offers a comprehensive material to investigate this question. 

I collected the data on July 20, 2024, and it encompassed information of 374 studios, 755 two-rooms and 583 three-rooms. These are the most popular apartment types to be bought in Helsinki, so I focused on them. In total, the cleaned dataset included information over 2,100 apartments sold in Helsinki during last 12 months. 
To have reasonable big comparison groups, I divided the data into groups that include 20 years: flats built before 1929, between 1930 and 1949, between 1950 and 1969 etc.

## Findings:
Sold apartments that had been built in 2010 or later, were on average smaller than the ones built in 1970-1989 and 1990-2009. This explains why people feel that home sizes are shrinking. But to compare to previous decades, the true era of small apartments was the time before and after the World War II. It can be said, based on my data, that Helsinki is returning to the era of small apartments. At the same time, it must be remembered, that every year less people live together in a same apartment. Even though apartments get smaller, many people have more space around them to compare to the time of baby boomers. 

## New skills learned:
In this Lede Program project, I strengthened my scraping skills. It makes me especially happy that I was able to solve how to navigate through the changing URL of the webpage and to form a comprehensive dataset.

A new library for me was numpy which I used to make conditions for a new column that I needed to create. This was essential for my project. Without it, it would have been impossible to group same type of apartments together and analyze the data.

I also learned how to clean data by creating my own variable of permitted characters and then write a piece of code using ‘~’ to rule out all results that do not meet rules defined in my variable. 

Third new thing I learned was how to find and delete duplicates.

## What I still would have liked to do:
I really wanted to map the data to see, on which neighborhoods the price per square meter was lowest or highest and are there neighboring areas that are totally an opposite for each other. This would have been a choropleth map.

Another nice mapping exercise would have been a location map on which I could have pointed out top 3 most expensive and cheapest homes and offer detailed information about them, e.g. construction year, who owns the plot or on which floor are they located. This could have been a scrolly tell.

From the data analyzes point of view, it would have been also interesting to collect data of the whole metropolitan area that encompasses also cities of Espoo, Kauniainen and Vantaa.
