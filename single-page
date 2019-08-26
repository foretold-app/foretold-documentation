# Best Practices For Writing Questions

Writing questions can be surprisingly challenging. Many people have a hard time with it at first.

### Cover all likely possibilities

Make sure to cover all of the conditions that could happen.

Bad: **"**_**How much will project X cost?"**_  
Better:  **"**_**How much will project X cost? If it does not happen or is cancelled, it counts as 0."**_

### Use clear terminology or use standardized dictionaries

Lots of colloquial language is not precise enough for great forecasts. For example, the question "_When will project X be complete?_", may leave the definition of both "project X" and "complete" vague. People may have different impressions of what things are and aren't part of "Project X", and different impressions of what "complete" means.

Bad: _**"When will project X be complete?"**_  
Better: _"**When will Project X be complete? This is according to our Asana schematic of Project X, and our Kanban definition of complete."**_

### Make sure you have a way of resolving a question

When you write a question on Foretold, you are responsible for eventually resolving that question. If it's not crystal clear how you would actually get or determine the number, either say that you will judge it yourself, or better yet, reference a specific authority you will use for question resolution.

Bad: _**"How much will the current trade deal hurt the economy?"**_  
Better: _**"Authority X routinely estimates the net benefit of trade deals. If they do so on this deal, what number will they give?"**_  
Better\(alternative\): _**"In Jan 2025, I will personally estimate the benefit of trade deal X. What number will I give it?"**_

### Further tips

There are subtle ways in which your question can break even if you get the above right. 

For example, measuring the productivity of your team in terms of number of lines of code written written will fail to capture things like code readability and performance, which might be what you really care about. 

Just because a question measures _something_ does not mean that it measures _what you care about_. 

You can find a more in-depth discussion of how to avoid these failure modes in [this page from the AI Forecasting Dictionary](https://parallel-forecast.github.io/AI-dict/docs/best-practices.html). 


# Cumulative Distribution Functions  Format

Continuous measurements can be made with either points \(reserved for resolutions\) or distributions. Distributions are saved in one specific format for cumulative distribution functions \(CDFs.\)

CDFs are stored as arrays of x and y point values. These have the following restrictions:

* All Y points must be equal to or between 0 and 1. 
* All X points must be in order.
* Users can only submit up to 1,000 points for one CDF.

Note that while you can only submit 1,000 points, you can choose which points to submit. For example, there may be a case where you want extra precision around the tails of a distribution, so submit more points in those areas.

Because of the simplicity of this format, Foretold CDFs only represent continuous functions. This means that they do have some significant limitations.

These limitations are important for all functions that happen on them. Aggregations and scoring metrics assume these distributions are continuous, so will have challenges in other cases.

### CDF Format Restrictions with Limits

The current format for CDFs assumes that distributions represent continuous functions. There are no ways of specifying limits or discontinuities. Often discontinuities can be approximated as continuous parts, but this is imprecise.

The proper way to write arbitrary CDFs is [with intervals](https://en.wikipedia.org/wiki/Cumulative_distribution_function). Discontinuities and limits are often drawn as empty circles, as in the diagram below.

![](.gitbook/assets/image%20%283%29.png)

Limits are often written mathematically, as is shown below.

![A uniform distribution from 0 to 1](.gitbook/assets/image%20%282%29.png)

### CDF Format Restrictions with Discrete Data

There are many times where distributions are made up of discrete data. In mathematical dynamics, [discrete data and continuous data](https://en.wikipedia.org/wiki/Discrete_time_and_continuous_time) are handled very different.

For example, say that you try to estimate how much time a project will take. You may think that there's a 30% chance the project will take 0 time, because it will be unnecessary. This would be a discrete point, and is not currently very well supported. 

Another example would be a situation you want to estimate how many people will come to a small gathering. At most, you expect 6 to come. In this case, there is no chance that 2.3 people will come; only integers are possible. This would be an example of a distribution over discrete numbers. 

Continuous distributions can approximate discrete ones, especially for large discrete numbers. For example, if you were estimating the population of Russia in 2020, the range would be so wide that future analytics you do may not be influenced significantly by the fact that the answer must be discrete. But for small numbers this could be an issue.

# Probability Distributions

One of the two types of question in Foretold is the "distribution" type, made for estimating continuous distributions.

Currently a very similar distribution input method is used as with the application [Guesstimate](https://getguesstimate.com). All [Guesstimate functions](https://docs.getguesstimate.com/functions/) and distributions are supported. 

## Basic Input

The recommended way of entering most numbers is by using the basic input. Type 

```text
"10 to 30"
```

In order to submit a lognormal distribution with a 5th percentile at 10 and a 95th percentile at 30. 

![](.gitbook/assets/image%20%281%29.png)

If the first number of these two is negative, then the distribution will be normal.

## Function Input

If you would like to pick a specific distribution and it's corresponding parameters, you can use the function input. If you are entering a distribution, then you will need to refer to call a specific distribution. Here are a few common ones available. A longer list is [here](https://docs.getguesstimate.com/functions/distributions.html). 

| Distribution | Use Cases | Syntax |
| :--- | :--- | :--- |
| Beta | Estimations proportions or percentages, where the answer must be between 0 and 1. | =beta\(α,β\) |
| Normal | Most uncertain things, where the uncertainty is symmetric around the median. | =normal\(μ,σ\) |
| Lognormal | Similar to normal, but with a long tail on the right. Cannot be 0 or less.  | =lognormal\(μ,σ\) |
| Uniform | A flat distribution, where everything inside is equally likely. | `=uniform`\(a,b\) |
| Multimodal | Weighted combination of distributions, giving multiple peaks. | =mm\(d1, ...,  \[w1, ...\]\) |



# Communities

Communities act as groups with custom membership and privacy settings. They can be useful both to organize privacy of questions and predictions, and also to organize questions into different clusters.

## Adding New Members

1. In your community page, click the "N Members" tab.
2. Click the "Add Members" button on the right side.
3. Search for the names of the users you would like to add. Click "Add to Community" next to their name.

![](.gitbook/assets/image.png)

## Community Permissions

Communities can be either private or public. If they are public, anyone can see them, including non-users of Foretold. If they are private, the contained information is only available to invited members.

A community can have multiple admins. Admins can add or remove members, convert viewers to admins, and convert admins to viewers. There must always be one admin in a community, so if you are the only admin, you cannot remove yourself from the community.

Anyone in a community can create new questions. If you would like to restrict non-admins from being able to create questions, please let message Ozzie. This feature is not yet possible but is being considered for future releases.

