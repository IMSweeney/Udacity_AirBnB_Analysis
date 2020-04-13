# Determining market price for an AirBnB listing

Say you are a perspective AirBnB lister with a property in Seattle. You might want to know how you can get the most out of this property. Using the Seattle AirBnB data from [Kaggle](https://www.kaggle.com/airbnb/seattle/data) along with some example code from the [Udactiy Data Scientist](https://www.udacity.com/course/data-scientist-nanodegree--nd025) course we will find the range of market price for a property and how to land on the high side. All of the source code is available in a Jupyter notebook on [github]()

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

From these statistics we can much more easily see what similar properties are going for. On average, properties like the example go up on AirBnB for $231 per night, but there is still a range of $200! The next step will be to figure out how to land on the high side of the range.

## Q2. What factors contribute most to properties being selected?

After doing some cleaning of the data, here are the top 5 factors sorted by the effect that they have on the availability:
Factor | Weight
------ | ------
asd | 2

The largest is **afsdfsafd**. Tragically, an owner can't do much about this. On the bright side, further down this list are a couple factors that we can influence. Namely, the price range we were speaking about earlier.

## Q3. What would the best list price for this property be?




### Resources:
-[Kaggle](https://www.kaggle.com/airbnb/seattle/data)

-[Udacity](https://www.udacity.com/course/data-scientist-nanodegree--nd025)
