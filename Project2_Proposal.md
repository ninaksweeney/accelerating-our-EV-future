# Increasing Electric Vehicle Adoption through Machine Learning

## Question/Need
In recent years, electric vehicles (EVs) have gained wide notoriety as a vital ingredient for a decarbonized society. [By 2030,](https://www.caranddriver.com/news/g35562831/ev-plans-automakers-timeline/) companies like Kia, Mazda, Subaru, Volkswagon, Mitsubishi, and Volvo all plan for a large portion of their car sales to come from EVs. However, while EVs have gained prominence and ownership is growing year-over-year, at the moment they still represent quite a [low share of annual car sales](https://www.iea.org/reports/global-ev-outlook-2020). Numerous reasons for these low adoption rates have been identified in the US, including a lack of nationwide charging infrastructure, lack of vehicle options, and for many young people, the up-front cost of switching away from gas. Faced with the choice to pay more for an electric vehicle - whether to align with personal values, save money in the long term, or just upgrade to newer tech - buyers are having to weigh a wide variety of factors. If the vehicle manufacturers above want to make their EV production pay off,  the switch to EVs needs to be friction-free for consumers. I plan to guide manufacturers' decision-making by exploring the question:  

**Which features of popular gas cars should manufacturers prioritize in their EV production to convert consumers from gas to electric, despite a higher EV price tag?**

Using the features and consumer ratings of thousands of cars scraped from Kelly Blue Book's website, I plan to identify the features of gas cars that are most predictive of a high consumer rating. With this knowledge, I will recommend a path forward for manufacturers to incorporate consumers' favorite features into EV production in an effort to reduce friction in the switch to electric.

## Data Description
* ~5,000 observations of car models manufactured between 2010-2022, scraped from [KBB.com/car-finder/](https://www.kbb.com/car-finder/?years=2010-2022)
* If it cannot be scraped, I also hope to add in car price data from a separate source (though with Selenium, this may be possible in my original scraping process)

An individual unit of analysis for this project is a unique car make/model/year. Some potential features are:
* Drivetrain
* Car length/width
* Trunk/cargo space
* Seating Capacity
* Technology amenities
* Consumer & Expert ratings   
...and others along these lines, provided by Kelly Blue Book. My initial scraped data has ~25 features, and my target feature will be **Consumer Rating**. 

## Tools
* Majority of scraping will be completed with BeautifulSoup, using Selenium to navigate the site
* Pandas and Numpy, Matplotlib, Seaborn
* With extra time, would like to try some more interactive visualizations

## MVP

In the MVP I plan to include:
* Initial EDA/visualizations of scraped data 
* First attempt at a model, with a path forward to optimize it