![SeattleSkyline](/oakie-seattle-skyline.jpg)
# Determining market price for an AirBnB listing

Say you are a perspective AirBnB lister with a property in Seattle. You might want to know how you can get the most out of this property. Using the Seattle AirBnB data from [Kaggle](https://www.kaggle.com/airbnb/seattle/data) along with some example code from the [Udactiy Data Scientist](https://www.udacity.com/course/data-scientist-nanodegree--nd025) course we will find the range of market price for a property and how to land on the high side. All of the source code is available in a Jupyter notebook on [github](https://github.com/IMSweeney/Udacity_AirBnB_Analysis).


## Q1. What is the market price for my property?

The [Kaggle](https://www.kaggle.com/airbnb/seattle/data) data source contains a bunch of info on listings in the Seattle area, such as the price of the listing, the location, information about reviews, and information about the property. Using some information on the property in question we can generate some usefull statistics about similar properties and get an estimate for the market value. Let's take, for example, a 2 bedroom, 2 bathroom property in the Queen Anne district. After filtering the data we can generate some usefull statistics:

Property Statistics | Price
------ | ---------
count  |  13
mean   |  $231
std    |  $73
min    |  $115
25%    |  $180
50%    |  $200
75%    |  $275
max    |  $349

From these statistics we can much more easily see what similar properties are going for. On average, properties like the example go up on AirBnB for $231 per night, but there is still a range of $200! How then should we decide the price of a our listing? To answer this we have to look at the other half of the puzzle, people actually choosing a listing to rent.


## Q2. What factors contribute most to properties being selected?

Availability is the metric I will use to try to determing the popularity of a given listing. The assumption being that a less available listing is getting booked more often and is therefore more popular. After doing some cleaning of the data, here are the top 10 factors sorted by the absolute value of the correlation that they have with the availability:

Factor | Correlation
------ | ------
calculated_host_listings_count  |  0.14
host_response_rate              | -0.09
number_of_reviews               |  0.09
review_scores_value             | -0.07
cleaning_fee                    |  0.06
guests_included                 | -0.05
bedrooms                        | -0.05
review_scores_rating            | -0.04
review_scores_accuracy          | -0.04
square_feet                     |  0.03

Wow! It looks like none of the numeric values in this dataset are particularly correlated with the availability of a property. You could make the arguement that the number of listings (*calculated_host_listings_count*) has some impact so let's dive a little deeper. We can look at this relationship specifically with a scatterplot:

![Q2b](/Q2b.png)

From the plot it could be argued that having many listings actually correlates with more availability (so less bookings). Although, in the 0-5 listing range where the majority of listers fall, there seems to be no correlation. Since this factor had the highest correlation and even this was insignificant, it would seem that there are no simple linear correlations between the numeric variables and booking rates.


## Q3. What would the best list price for this property be?

Although we haven't had any luck yet, let's go back to the start and re-examine the original question. What is the best price point for our booking. Looking at all of the data available for other 2 bedroom, 2 bathroom listings, we can chart the relationship between listing price and availability:

![Q3a](/Q3a.png)

Looking at this data we can see that the only properties that are booked more than half the time have a listing price on the lower half of the spectrum (<$400). But, sadly these properties still have a huge variability in booking time, so I must conclude that there are other factors contributing to bookings.


## Summary:

I would guess that the lack of linear correlation of any of the data to availability is because people take much more than one factor into consideration when deciding whether or not to book. I would suspect that is some combination of price, location, reviews, and other factors that determine a prospective renter's willingness. To find these effects however, a deeper modeling technique would be necessary. Maybe there are some neural networks in my future. 




### Resources:
-[Kaggle](https://www.kaggle.com/airbnb/seattle/data)

-[Udacity](https://www.udacity.com/course/data-scientist-nanodegree--nd025)
