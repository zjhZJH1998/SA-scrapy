# Scrapy--A Fast and Powerful Scraping and Web Crawling Framework

![](https://s2.ax1x.com/2019/10/01/uUDwhF.jpg)

## Abstract

Scrapy (/ ˈ s k r eɪ p i / SKRAY -pee) is a free and open-source web-crawling framework written in Python. Originally designed for web scraping, it can also be used to extract data using APIs or as a general-purpose web crawler. It is currently maintained by Scrapinghub Ltd., a web-scraping development and services company.

Written in: Python\
Initial release: 26 June 2008\
Developer(s): Scrapinghub, Ltd.\
Stable release: 1.7.3, / 1 August 2019; 6 days ago

While the development is open-source, the amount of documentation about contributing is limited. This results in a project where programming is not done through conventions or guidelines but with a strong focus on getting things to work. Therefore, this document as a whole can serve as a helpful introduction to prospective developers looking to better understand the architecture to which they might contribute.

## Table of contents

- [Introduction](#Introduction)
- [Stakeholders](#Stakeholders)
- [Context View](#Context-view)
- [Development View](#Development-view)

## Introduction

## Stakeholders

## Stakeholders

>   A stakeholder is a member of "groups without whose support the organization would cease to exist".

As the definition above, stakeholders in Scrapy are people who are interested in and influence Scrapy. More specificly, stakeholders can adivce to it and make some influence on Scrapy's policy and so on. So, we will firstly have a glimpse on the overview of the stakeholders which includes developers, maintainers, users and other kinds of stakeholders which are of vital importance. After we have had an overview of those kinds of stakeholdes, we will have a deeper appreciation of those stakeholders and try to give the Power Interest Graph of Scrapy in which we will analyze the reason.

### Overview 

-   Acquirers
    
    Scrapy is now managed by **Scrapinghub**. Scrapinghub is specializes in web crawling, and it was founded by Scrapy creators.

-   Developers

    Because Scrapy is an open source project, so developers can be found on Github. Although there are thousands of brilliant developers who have contributed to Scrapy, in order to specify the core developers of Scrapy more clearly, we will mainly discuss the core team which based on the statistics on Github to show the most contributed developers in this case, such as: @[dangra](https://github.com/dangra), @[redapple](https://github.com/redapple), @[kmike](https://github.com/kmike). And the following table contains those Most contributed developers in trems of commit number.

    Developer     | Commits | Additions | Deletions
    --------------|---------|-----------|----------
    dangra        | 738     | 83,176    | 95,953
    redapple      | 392     | 9,643     | 3,146
    kmike         | 327     | 8,441     | 6,586
    void          | 246     | 20,266    | 13,201
    curita        | 174     | 12,211    | 10,056
    lopuhin       | 133     | 1,221     | 701
    elacuesta     | 128     | 4,049     | 2,476
    eliasdorneles | 116     | 2,725     | 2,956

    *Table 1: Most contributed developers in trems of commit number*

-   Maintainers

    Maintainers are responsible for managing the development and evolution of Scrapy. In Scrapy, the core teams described above work as maintainers. They discuss the development direction of Scrapy and they accept and review pull-requests. We can view the main contributors from the statistics on Github. And the core mintainers are the same as those developers above.
 
-   Users

    Scrapy has been used by both big companies like **PARSE.LY**, **Direct Employers Foundation**, government institution like **DATA.GOV.UK** and many other personal users who want to extracte the data you need from websites.

-   Suppliers
    
    The development of Scrapy is coordinated by **Github**, which can be clearly classified as a supplier. Meanwhile, **Python** is the scripting language that Scrapy uses, so we also regard Python as a supplier.

-   Communicators
    
    Scrapy has large and active communities on **Github**, **Reddit** and **StackOverflow**. These communities have tens of thousands of communicators which can help explaining the system to other stakeholders via documentation and the experiences they have.

-   Competitors
    
    As we all know, there are tons of framework that can extracte data from the Internet. For Scrapy, there are competitor as **PySpider**, **Crawley** and **Portia**. Competitor can help Scrapy to be better and supervise it to move forward.

The following figure shows the stakeholders mentioned above, and it proides a channel through which people can have a more direct impression of those stakeholders.

![](https://s2.ax1x.com/2019/10/01/uUrhV0.jpg)

*Figure 1: Stakeholders of Scrapy*

### Power Interest Grid

The following figure shows the Power Interest Grid. Power Interest Grid contains the main stakeholder categories and more detailed explanation will be listed.

![](https://s2.ax1x.com/2019/10/01/uUr55T.jpg)

*Figure 2: Power Interest Grid*

-   Low power and low interest
    
    Suppliers like GitHub are stakeholders that have no control over Scrapy, and they do not have directly benefit from it. For Github, they should be in the low power and low interest part.

-   Low power and high interest
    
    Users, Communicators and Competitors of Scrapy are stakeholders who have high interest in Scrapy and will be greatly affected by the changes in Scrapy, but they have nearly no power to influence it.

-   High power and low interest
    
    Suppliers like Python provide necessary library and tools to develop Scrapy. The changes of Python will directly affect the development of Scrapy but Scrapy has little influence on Python on the contrary.

-   High power and high interest
    
    Core developers and acquirers of Scrapy are stakeholders who have significant interest and power in the development of Scrapy. And in Scrapy, developers are also maintainers, so those people will guarantee it to run without error and provide new features. At the same time, acquirers will provide many kinds of support. Both of them can also largely influence Scrapy, so they will be in the high power and low interest part.


### References
[1] Wikipedia. Stakeholder (corporate)[EB/OL］.Stakeholder (corporate) - Wikipedia，https://en.wikipedia.org/wiki/Stakeholder_(corporate)

## Content-view

## Development-view
