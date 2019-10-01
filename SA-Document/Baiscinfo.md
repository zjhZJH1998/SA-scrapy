组员名单
#4.Development View
This section describes the architecture that supports React development process. First, we will describe principles and guidelines that govern the development of Scrapy. This will be followed by source code and module organizaton.
##4.1 Development characteristics
Scrapy is a fast high-level web crawling framework, used to crawl websites and extract structured data from their pages. It can be used for a wide range of purposes, from data mining to monitoring and automated testing[[1]](). It's normal for us to compare Scrapy to Request lib, so the developent of characteristics of Scrapy should be  recounted.

####Asynchronous processing
One of the main advantages about Scrapy is that: requests are scheduled and processed asynchronously. This means that Scrapy doesn’t need to wait for a request to be finished and processed, it can send another request or do other things in the meantime. This also means that other requests can keep going even if some request fails or an error happens while handling it.[[2]]()
####Convenient request settings
Scrapy  gives you control over the politeness of the crawl through a few settings You can do things like setting a download delay between each request, limiting amount of concurrent requests per domain or per IP, and even [using an auto-throttling extension](https://docs.scrapy.org/en/latest/topics/autothrottle.html#topics-autothrottle) that tries to figure out these automatically.
####Built-in parser
 Built-in support for selecting and extracting data from HTML/XML sources using extended CSS selectors and XPath expressions, with helper methods to extract using regular expressions.
#### interactive shell console
The Scrapy shell is an interactive shell where you can try and debug your scraping code very quickly, without having to run the spider. It’s meant to be used for testing data extraction code, but you can actually use it for testing any kind of code as it is also a regular Python shell.[[3]]()
####wild middlewares for handling
Scrapy privides wide range of built-in extensions and middlewares for handling:cookies and session handling, http compression,authentication, caching, user-agent spoofing, robots.txt, crawl depth restriction and more.[4]()

##4.1 Code Organization
The following figure shows the source code organization of scrapy.
![Figure1 code organization of scrapy](https://upload-images.jianshu.io/upload_images/17534427-80fbf5f00989de4e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
*  ####Test files
Source code attachs a test project, placed in the tests folder. This test project create ```TestSprider``` object to implement spider and use ```ScrapyRedisBloomFilter``` to remove duplication. We can use console to ```scrapy crawl test``` to run this test project. It casts most of functions of scrapy.
*  ####Funtional  files
The functionality part contains the components that are responsible for functions of the project. *Commands* implements the console tool of scrapy. *http* integrate the HTTP processing functions. The most important  is *core* , which includes the significant module of scrapy such as *engine*, *scheduler*, *scraper* and so on. These core modules'  relationship will be analized later.
*  ####Documentations
The documentation section contains codes used to demonstrate and generate the documentation of Scrapy. They are often written in RST format. *README.rst* contains the usage and installation of  Scrapy. *docs* contains the Materials used by documents like pictures and logo.
*  ####Others
Scrapy has other files, such as version log files, contributor log files, and relatively independent script files.

##4.3 Module Organization
This section focuses on the main modules of scrapy and their interactions.
####Modules introduction
*  #####Scrapy Engine
The engine is responsible for controlling the data flow between all components of the system, and triggering events when certain actions occur. 
*  #####Scheduler
The Scheduler receives requests from the engine and enqueues them for feeding them later (also to the engine) when the engine requests them.
*  #####Downloader
The Downloader is responsible for fetching web pages and feeding them to the engine which, in turn, feeds them to the spiders.
*  #####Spiders
Spiders are custom classes written by Scrapy users to parse responses and extract items (aka scraped items) from them or additional requests to follow.
*  #####Item Pipeline
The Item Pipeline is responsible for processing the items once they have been extracted (or scraped) by the spiders. Typical tasks include cleansing, validation and persistence (like storing the item in a database). 
The following diagram shows an overview of the Scrapy architecture with its components and an outline of the data flow that takes place inside the system (shown by the red arrows).
####Modules' relationship and Data flow

The following diagram shows an overview of the Scrapy architecture with its components and an outline of the data flow that takes place inside the system (shown by the red arrows). The data flow is also described below.[5]()

![Figure 2 data flow](https://upload-images.jianshu.io/upload_images/17534427-a835f7ea3b5767fa.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
The data flow in Scrapy is controlled by the execution engine, and goes like this:

1.  The *Engine* gets the initial Requests to crawl from the *Spider*
2.  The *Engine*  schedules the Requests in the *schedules*  and asks for the next Requests to crawl.
3.  The *Schedules* returns the next Requests to the *Engine* 
4.  The *Engine* sends the Requests to the *Downloader*, passing through the *Downloader Middlewares*
5.  Once the page finishes downloading the [Downloader] and sends it to the Engine, passing through the *Downloader Middlewares*
6.  The*Engine* receives the Response from the *Downloader* for processing, passing through the *Spider*
7.  The *Spider* processes the Response and returns scraped items and new Requests (to follow) to the *Engine*
8.  The *Engine* sends processed items to *Item Pipelines*, then send processed Requests to the *Scheduler* and asks for possible next Requests to crawl.
9.  The process repeats (from step 1) until there are no more requests from the *Schedules*






[1][https://docs.scrapy.org/en/latest/](https://docs.scrapy.org/en/latest/)

[2][https://www.cnblogs.com/jclian91/p/9799697.html](https://www.cnblogs.com/jclian91/p/9799697.html)

[3][https://docs.scrapy.org/en/latest/topics/shell.html#topics-shell](https://docs.scrapy.org/en/latest/topics/shell.html#topics-shell)

[4][https://www.cnblogs.com/xieqiankun/p/know_middleware_of_scrapy_1.html](https://www.cnblogs.com/xieqiankun/p/know_middleware_of_scrapy_1.html)

[5][https://docs.scrapy.org/en/latest/topics/architecture.html](https://docs.scrapy.org/en/latest/topics/architecture.html)
