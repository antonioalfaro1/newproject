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

![example image](/promotionai.png)


## Data sources and AI methods

The information will come from the company's databases for each client:

-Product 1: dates on which it has been frequently requested on each date
-Product 2: ...

-Product No.

-Frequency of consumption on Monday

-Frequency of consumption on Tuesday

....

-Frequency of consumption on Sunday

Techniques:

- tf-idf technique for products by adding a weighting factor (positive or negative) at the company's discretion. Choice of 1 or 2 products to promote.

-Days of the week: obtaining a value based on log10 to make it more uniform by applying: frequency x intercept term = weighted value. Log10(weighted value)= value (between 0 and 1). Days with a weighted value lower than a ratio, for example 0.20, the least common for the client, will be chosen as the promotion day.

## Challenges

This promotional mechanism aims to attract customers with their favorite product/s on days when they do not usually go to the restaurant.
If the reason is unavoidable (for example, on days when they do not work or do not rest, they do not go because of the distance, or those are days with incompatible schedules) the promotion will not be effective.

The model could be adapted to new formulas:

-Offer promotions on the client's usual days but offering new products on sale
-Reduce the offers to a single day but make them more aggressive to see the clients' behavior.
etc.

## What next?

The challenge of this model is to determine whether loyalty program databases allow all the required information to be extracted and processed en masse.


## Acknowledgments

Thank you to our restaurant customers for so many years of teaching us that we love extensive menus, but we are creatures of habit.
