# SinaWeiboScraper
This is a Web Scraper for Sina Weibo Search by Keywords

# Why use SinaWeiboScraper?
There exists some Sina Weibo Scrapers. However, they are all implemented with Weibo API. Sina Weibo limits the amount of data that can be obtained each hour, day, and month if API is used. This is a Web Scraper for Sina Weibo Search by Keywords implemented by pure url encoding so that it simulates a real browser, navigates to the page and get access to the data. It gets rid of the limits. It is possible that Weibo will let you enter verification code to prove you are not a machine, but it is not often.

# Author
[Xuzhou Yin](https://github.com/Yhinner). Personal Website: [www.xuzhouyin.com](http://www.xuzhouyin.com)

## How to Download
Open terminal, and navigate to the directory where you want to store the program, then type ```git clone address``` to download the program

## Dependences
1. Python 2.7 or above
2. Firefox browser (Other browsers may be supported in future)
3. selenium. Type ```pip install selenium```
4. time. Type ```pip install time```
5. bs4. Type ```pip install bs4```
6. urllib. Type ```pip install urllib```
7. datetime. Type ```pip install datetime```
8. unicodecsv. Type ```pip install unicodecsv```

## How to Use

### Before running the program
Sina Weibo limits the permission of search feature that only users has signed in is able to use advanced search(such as search with specific time period). So please register for a sina Weibo account and sign in through Firefox browser(So Firefox automatically signs in next time). Then find the path of the Firefox profile (Refer to [Where is Firefox profile stored](https://support.mozilla.org/en-US/kb/profiles-where-firefox-stores-user-data)). and replace the path in line 49 in ```scraper.py```.

### Query
```query.txt``` file is for storing all the queries. Please add queries in the form of ```keyword;eventDate;startDate;endDate;pageofResult```, one query per line. Sina Weibo does not support "Scroll to bottom to view more" feature in search. Instead, it separates the query results into pages. And Sina limits the page of results to 50. So for each query, only 50 pages of the results can be accessed by users. And each page contains 20 posts. Therefore, for each search there are maximum 1000 posts can be obtained. **However, it might be the case that there are less than 1000 posts from the query. So please check the maximum number of pages that contain all results of the query**. 

### Run the program
Run the program by typing ```python scraper.py```

### What happens during execution
Firefox browser will be executed, navigated to search page with keyword autimatically.

### Output
Results will be in ```output``` folder in csv format. Each query generates one csv file. Excel has problem displaying Chinese characters. So viewing through other text editor is better(If you are using Mac, you can use Numbers to open the csv files).

### How to developer
For now this program only supports query with keyword for my own purpose. everyone is free to explore new features. There is one thing needs to be noted that it does not use Sina Weibo API since Weibo limits the amount of data to query if API is used. It basically uses broswer cookie to login, url address to do search. Please submit a pull request if you are read to contribute.

### License
This project is licensed under the MIT License - see the [LICENSE.txt](LICENSE.txt) file for details
