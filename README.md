# Key Terminology

## Questions

A question is a thing that can be predicted. Questions have creators who are are responsible for resolving \(answering\) them.

### Distribution vs. Binary Questions

There are two main kinds of questions types in Foretold. _Distribution_ questions are for continuous variables, like, "How many days will it snow in 2020?". _Binary_ questions are for specific events, like, "Will it snow at least once in January 2020?"

### Resolution Endpoint

Questions could have **resolution endpoints**. This is a URL that returns some sort of number. When the **expected resolution date** occurs, this URL will be called, and the result submitted as a **resolution**.

### Expected Resolution Date

The expected resolution date is the date that the question creator thinks the question will be resolvable. When this date passes, the question will move from an "**Open**" state to a "**Pending Resolution**" state to indicate this change. The owner is expected to resolve this question after this date, or **edit** it to have a later expected resolution date, in which case the state will change back to "**Open**".

## Predictions

A prediction is a forecast for a question. There are a few types of predictions. 

### Competitive Predictions

Competitive predictions are the ones most users will submit. These are formal predictions. They will later be judged on accuracy when their corresponding questions are resolved.

### Aggregations

Some bots could be set to make non-competitive aggregations. These are meant for bots that compute aggregates given previous data. These are different from competitive predictions, mainly because bots can post aggregations applicable for historical times. It's important to distinguish these to make it clear that they weren't exactly posted at the signified time. When evaluating which predictions were the most valuable, typically these will not be included for that reason.

### **Resolutions**

Resolutions aren't strictly predictions, but work similarly. They are meant to signify the actual answer to a question.

It's possible that the question owner may realize that a recorded resolution is incorrect. In this case they can enter a new resolution. 

Resolutions can be distributions. This is useful for cases where the answer to a question itself is a distribution. 

## Communities

Communities act as groups with custom membership and privacy settings. They can be useful both to organize privacy of questions and predictions, and also to organize questions into different clusters.

## Series

Series are clusters of organized questions. These are useful for structured questions, like "What are the ratings and box office returns of these 100 movies, at 3 different years in the future?" These are not well supported yet, but are planned to have improvements in the future.

## Entities

Entities refer to a set of concepts with unique IDs. There is currently one list of entities that is hardcoded. If you would like to see more formal entities get added to the system, contact Ozzie.

The entity system uses the [Ken](https://kenstandard.com) library. In the future it is planned that channels will be able to create their own lists of custom entities.

