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

