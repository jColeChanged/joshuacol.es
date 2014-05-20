---
layout: post
title: K Nearest Neighbors
published: true
---

The eighth chapter of [ Programming Collective Intelligence ][1] was on building a price model. This was significant as prior to this all the classification algorithms that we had been looking at were intent on classifying things into categories. To do this the chapter introduced [K Nearest Neighbors][2]. The approach was actually really similar to what we saw all the way back in chapter two when we built a recommendation system.

The first step is to define a distance function. You use this distance function to determine what the ``k`` closest users are. Then to estimate an attribute that you are predicting you take the average of that attribute. And that is pretty much it. Well, not really, but that is the core idea. It turns out that there are some gotchas with the distance function that are worth re-visiting.

Lets say that you have date of birth as one attribute and the month you first spoke as another attribute. Chances are when your computing distance you don't want the age that someone spoke to be factoring into the distance. It would throw off the computation, because it really isn't very relevant. So how do you go about solving thing? Just normalizing things doesn't help. Some of this stuff doesn't matter. The solution? Weighted averages let you weight some attributes more then others.

But wait theres more. Once you've given things weights you suddenly have the ability to choose the best weights. The goal is to minimize the error of the algorithm and the solution is naturally a set of weights to use. See where this is going? An optimization problem! You can use the optimization algorithms discussed a while back to compute really good weights.

The only catch is how you compute the error. To do that you have to use something called cross-validation. Basically, you split up the dataset into a training set and a test set and run the predictions on the test set.

[1]: http://www.amazon.com/Programming-Collective-Intelligence-Building-Applications/dp/0596529325/
[2]: http://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm