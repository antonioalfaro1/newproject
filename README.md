# Project Title

Final project for the Building AI course

## Summary

The goal is to apply AI techniques to massive data processing generating personalized promotions in both, content and dates, for restaurant customers with loyalty cards. Incorporating criteria defined by the company regarding possible promotions to be offered and the dates on which they are applicable.

## Background

Many restaurant chains offer loyalty cards to get to know their customers habits and trying to generate more sales. They use these cards to launch promotions that are not always as effective as intended, since they are aimed at customers with very diverse habits and tastes. These are the problems they face:

1. Extracting useful information from each customer's sales history
2. Using this information to promote sales
3. Difficulty in generating personalized promotions on a customer-by-customer basis
4. Making these promotions both attractive to the customer and in line with the company's objectives (for example, not cannibalizing sales with promotions on inappropriate days or products).


## How is it used?

First, we will need to process the customers' habits. From the loyalty card database, we will generate a table with the following data:

-Most requested products (using only the items on our menus that are eligible for promotions) with details of the frequency of consumption of each one in each invoice recorded. We will consider, for example, consumption over the last year, thus discarding older consumption that may no longer be relevant.

-Days of the week on which the customer has registered a visit to the restaurants, computing the frequency of visits each Monday, Tuesday, etc.

On this basis:

1 We will apply the tf-idf technique to the products to consider both the repetition in the consumption of the products and the weighted frequency. In this way, we will know the products that the customer consumes the most in order to offer them discounts or some extra in their consumption.

2 For the products, we will apply an upward or downward weighting depending on whether the restaurant considers it appropriate to promote it or not. For example, increasing the consumption figure for products with a wide margin by 20% and penalizing by -20% the products that barely generate profits. [other criteria could be the difficulty of producing them or the interest or not in promoting consumption]

3 As for the days of the week, we will be interested in knowing the days with LOWEST consumption by each client to encourage them to come on those days. In this way, we will make a quantification by weighting the frequency inversely on each day. The usual days of a client will get the worst score and the days on which they do not usually consume will have a higher score.

4. Regarding the date, we can also weight according to our criteria. Perhaps if a client does not consume on Saturdays, but that day we have a full restaurant, it is not a good idea to encourage them to come. And vice versa with the bad days on which we can add a bonus so that they score better than those with higher sales.

Finally, we will generate a personalized offer for each client to whom we will offer:

a- Their preferred product (although there could be a bias towards the second or third due to weighting factors that we have defined)

b- On the day when they do not usually consume (there could also be a slight bias defined by us)


## Data sources and AI methods

The information will come from the company's databases for each client:

-Product 1: dates on which it has been frequently requested on each date
-Product 2: ...

-Product No.

-Frequency of consumption on Monday

-Frequency of consumption on Tuesday

....

-Frequency of consumption on Sunday


AI methods:

-


Where does your data come from? Do you collect it yourself or do you use data collected by someone else?
If you need to use links, here's an example:
[Twitter API](https://developer.twitter.com/en/docs)

| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |

## Challenges

What does your project _not_ solve? Which limitations and ethical considerations should be taken into account when deploying a solution like this?

## What next?

How could your project grow and become something even more? What kind of skills, what kind of assistance would you  need to move on? 


## Acknowledgments

* list here the sources of inspiration 
* do not use code, images, data etc. from others without permission
* when you have permission to use other people's materials, always mention the original creator and the open source / Creative Commons licence they've used
  <br>For example: [Sleeping Cat on Her Back by Umberto Salvagnin](https://commons.wikimedia.org/wiki/File:Sleeping_cat_on_her_back.jpg#filelinks) / [CC BY 2.0](https://creativecommons.org/licenses/by/2.0)
* etc
