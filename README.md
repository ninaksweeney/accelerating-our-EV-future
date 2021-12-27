# Accelerating Our EV Future: Increasing Electric Vehicle Adoption through Machine Learning

## Abstract

In recent years, electric vehicles (EVs) have gained wide notoriety, and a number of car companies are shifting heavily toward EV manufacturing. However, EVs still represent quite a low share of annual car sales due to variables like a lack of nationwide charging infrastructure, lack of vehicle options, and the up-front cost of switching away from gas. If manufacturers want more EVs on the road, consumers need to be excited enough about new EVs to justify paying for them. Using the features and consumer ratings of thousands of cars scraped from Kelly Blue Book's website, I built a regression model to identify car features that are predictive of a high consumer rating to guide the design decisions of global manufacturers.   

To dig deeper into this project, please see: 
* The [Jupyter Notebook containing project code](https://github.com/ninaksweeney/Metis_Project_2/blob/main/Project2_Notebook.ipynb)
* Final presentation [slides/visuals](https://github.com/ninaksweeney/Metis_Project_2/blob/main/Project2_Presentation.pdf)

## Design

This project was designed around the target variable Consumer Ratings from Kelly Blue Book. I also considered focusing on sales numbers, but for lack of data I decided to pursue this more qualitative route. Though consumer reviews are notoriously biased, they are also *incredibly* important to buyers, ranking as the 2nd most trusted source of brand information after family & friend recommendations. So whether brands want to focus on them or not, consumer reviews affect sales. This means that any insights I can glean from KBB reviews could potentially impact future EV ratings and subsequently, sales. While the project focused on building a prediction model, I realize that consumer ratings are a very human, behavioral target. From the start, my main priority was intepretability of insights from the model, rather than high predictive accuracy. 


## Data

This project's dataset was scraped from kbb.com/car-finder/ using Selenium and BeautifulSoup. Cars were filtered from 2010-2022, and about 4500 cars were pulled from the website. After cleaning & dropping electric vehicles, nulls, and outliers like passenger vans and supercars, I was left with around 3000 data points. The dataset included features like peak horsepower, seating capacity, entertainment features, number of doors, combined MPG, and many others. 

## Algorithms

*Feature Engineering*  
1. Added two polynomial features, combined_MPG^2 and entertainment features^2
2. Converted categorical variables such as drivetrain and brand to binary dummies
3. Analyzed multicollinearity of features and removed certain features accordingly

*Models*
Throughout the model building process, I consistently trained and cross-validated a Linear Regression, Ridge, and Lasso model to compare their performance. All models performed similarly, and even with many iterations, did not see much change in performance. 

*Model Evaluation & Selection*
The dataset was split into 80/20 train vs. holdout and consistently trained & validated with 5-fold cross-validation. I consistently evaluated the models using R^2 and Mean Absolute Error. Predictions on the holdout set were limited to the very end, when I tested a final Lasso, Ridge, and Regression model on the holdout data. In the end, I moved forward with the Lasso model because it matched the performance of the others while maintaining the interpretability of the coefficients. 

**Performance on the Holdout Data**
R^2: 0.218
MAE: 0.23 stars

## Tools

Scraping: Selenium & BeautifulSoup
Data Manipulation: Numpy & Pandas
Modeling: Scikit Learn
Plotting: Matplotlib & Seaborn 

## Communication

I completed a 5-minute presentation of my insights from the model and recommendations for future EV manufacturers. Slides and visuals for this project are included in this repository. Future work may include using NLP to analyze themes from individual reviews, incorporating data from a wider variety of sources, and using sales data to predict a different, more concrete target. 
