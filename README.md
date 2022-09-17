# house_rocketHouse Rocket

disclosure: House Rocket is a fictional company and all the procedures and dicussions presented here are intended to practice and show my data science skills, and also for educational purposes. The assumptions, questions and conclusions/proposals are all made solely to fill the requirements of this fictional business. The data used for this project are available in the Kaggle website (https://www.kaggle.com/datasets/shivachandel/kc-house-data) in a public domain for download.

1. Understanding the company
The real estate businesses possess diverse ways to generate revenue, including real estate agent, wholesaling, wholetailing, buy and hold investing, house flipping, and remote investing to mention a few. These options have their pros and cons and the model of choice depends on the context and goals of the company. For the purpose of this project, the fictional company House Rocket uses a model where the company search for good purchasing opportunities, with low prices and properties in good conditions where they can potentially make a profit when selling.

2. Business question
The company has big challenges such as finding the best market opportunities and generate revenue. The company’s CEO, fortunatelly, is a data-driven person and makes his decisions on solid evidences, backed up by data. Currently, the company has a large database and the information it contains should drive the purchasing and selling decisions. Therefore, the House Rocket’s CEO had approached the Data Science team of the company with two questions, with which the answer would provide support for the decisions of the company:

    1. What are the properties House Rocket should buy and at what price?
    2. Once the property is bought, when is the best time to sell the property? And for what price?

 
2.1 The database
The company has a large database of properties located in King’s County in Washington, USA. The properties attibutes are described in table 1.


Property attibute
Description
id
Single identification code of the property
date
Date the property has been sold
price
Property’s selling price
bedrooms
Property’s number of bedrooms
bathrooms
Property’s number of bathrooms
sqft_living
Building’s size
sqft_lot
Size of the land’s lot
floors
Property’s number of floors
waterfront
Does the property have waterview? (0=no; 1=yes)
view
Property’s quality of view index - from 0 to 4
condition
Property’s overall condition index - from 1 to 5
grade
Property’s overall quality index (construction and design)- from  1 to 13
sqft_above
Property’s space above the ground
sqft_basement
Property’s basement size
yr_built
Property’s construction year
yr_renovated
Year of the las renovation
zipcode
Postal code
lat
Latitude position of the property
long
Longitude position of the property
sqft_living15
15 neighbours property’s interior size
sqft_lot15
15 neighbours property’s land lot

2.2 Premisses about the database

    • Bathrooms with ratio numbers are considered as not having all bathroom items;
    • The scores of the “view” column mean: 0 = no view, 1 = regular, 2 = medium, 3 = good, 4 = excellent;
    • The scores of the “condition” column mean: 1 = very bad, 2 = bad, 3 = medium, 4 = good, 5 = very good;
    • The scores in the column called “grade” were classified using a score band for each level: 1 to 3 – very low; 4 to 6 – low, 7 = medium, 8 to 10 = high, and 11 to 13 = very high;
    • The seasonality influence the price of the property. The price fluctuates depending on the warmer or colder seasons of the year

3. Solution plan
There are three components in the solution that makes up the solution plan: the deliverable, the tools and the process. Take a look below for further details:

3.1 The deliverable
	This is the product that will be sent for the CEO to fullfill his requirements:
    • A table with the suggested buying properties;
    • A table with the suggested time and price for selling;
    • A web application for data exploration.

3.2 Tools
	For this project, I have used the following tools:
    • Python 3.10.4
    • Microsoft Visual Studio Code
    • Streamlit
    • Streamlit share







3.3 Proccess

This project aims to respond to business questions using exploratory analysis of the available data. Therefore, the dataset was processed to answer these questions:


       3.3.1. What are the properties House Rocket should buy and at what price?

Location and condition play an important role on property pricing. Therefore, the dataset was filtered using location as a grouping factor and the median was calculated, to avoid influence of extreme scores. Then, those properties with price below the median for that region and presented condition above agood condition were selected.

       3.3.2. Once the property is bought, when is the best time to sell the property? And for what price?
Considering the seasonality, the chosen properties were re-grouped by location and season of the year and a new median was calculated. After this processing, the following conditions were applied for selling:
	3.3.2.a. If the purchasing price was above the regional median, ocnsidering the seasonality, the selling price should be 10% above the purchasing price;
	3.3.2.b. If the purchasing price was below the regional median, ocnsidering the seasonality, the selling price should be 30% above the purchasing price;

4. Main insights from the data

Assessing the data allowed the establishment of few hipotheses. After the verification of these initial hipotheses, it was possible to better understand the real estate market in King County, Washington.

4.1. The hipotheses:

4.1.1: Properties with waterview are 30% more expensive than those without waterviews.
FALSE – properties with waterviews presented higher prices, but they are 68.0% more expensive.

4.1.2: Properties built before 1955 are 50% cheaper than those built after 1955.
FALSE – even though the properties built before 1955 are cheaper than those built after 1955, the difference is 0.8% lower.

4.1.3: Properties without basement are 40% larger than properties with basement
FALSE – properties without basement are 18.4% larger than properties with basement.

4.1.4: There is a 10% year-over-year(YoY) price growth of the properties
FALSE – the YoY growth is -0.1%.

4.1.5: Properties with 3 bedrooms present a 15% month-over-month (MoM) growth.
FALSE – the MoM growth is 0%.

5. Financial impact
The strategies implemented in this project, the financial impact was an average profit of $71,700.00 per property.
6. Conclusion and next steps
This project successfully responded to the CEO business questions, addressing the issues related to the company’s business model. Additionally, the project showed that there is room for improvement  in a future analysis, including further insights that may be generated using the metrics present in the data and evaluate the best selling predictors using regression models.
