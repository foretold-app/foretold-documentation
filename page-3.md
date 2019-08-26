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



