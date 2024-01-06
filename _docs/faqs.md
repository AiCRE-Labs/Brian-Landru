---
layout: default  # Specifies the layout to be used for this page
title: FAQs  # Title of the document
permalink: /docs/faqs/  
collection: docs
---


<div class="centered-text">
  <div class="typing-effect">
  <h1> What is this? </h1>     
  </div>
</div> 


The tool you're using is called Dr. Fill. It's AiCRE's solution to tenant selection. It analyzes information about your properties, their tenants, the surrounding trade area, and historical data to recommend the tenant types that will be the most useful in your property's vacancies.


<h1>How are recommendations made?</h1>
Dr. Fill makes tenant type recommendations that are predicted to be the most useful across different objectives held by Retailers, Leasing Agents, and Retail CRE Management. 

The usefulness of a recommendation is measured by what we call **The Score**. **The Score** is designed to coordinate, balance, and simplify the many different objectives the three primary stakeholders have into a single number that's easy to understand. This combination of objectives is done without skewing toward any single objective. The objectives and how we measure them are:

| Objective                                   | How it’s measured                                                                                                                                                                                                                                                                                                                                        |
|---------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Minimize tenant turnover                    | Cumulative annual risk of the tenants at the property defecting at any given point. We estimate this using historical data on tenant turnover.                                                                                                                                                |
| Minimize competition at the property        | This is measured by how competitive each tenant is to every other tenant. We then average the results and weight by tenant type GLA. Competitiveness is the cross tenant type elasticity of demand. The intuition of this metric is simple: competitors affect each other's demand by increasing or decreasing their prices. For example, Jelly stores are competitive with Jam stores. We know this because if the price of jelly goes up, people buy less jelly but buy more jam. On the other hand, if peanut butter gets more expensive, sales of both jelly and jam go down. Peanut Butter stores are not competitive with Jelly stores, while Jelly stores are quite competitive with Jam stores.                                                                                                                                                                                                                                                                                                                |
| Maximize complementarity of tenant mix      |      This is the inverse of competitivenss. Peanut Butter Stores and Milk Stores are complimentary, but Jelly Stores and Jam Stores are not.                                                                                                                                                                                                                                                                                                                                                    |
| Maximize diversity at the property          | We call how diverse the set of co-tenants is **Property Diversity.** **Property Diversity** ranges from 0% to 100%. 0% is the least diverse, meaning every tenant type is the same. 100% is the most diverse, meaning every tenant type is different. Technically, it's a metric based on Shannon's Diversity Index. In the context of Dr. Fill, **Property Diversity** quantifies how hard it is to predict a tenant’s type based solely on the vacant space’s share of the property GLA. There are two important advantages in quantifying Property Diversity this way. It's nuanced. It considers both the presence and proportion of different tenant types in terms of the property’s overall GLA. It assumes that a more even distribution of GLA across tenant types indicates greater diversity.                                                                                                                                                                                                                                                                                                                |
| Maximize rents                              | We measure rent sensitivity by the elasticity of demand given the property, tenant, and trade area. This tells us how sensitive tenant types are to rent hikes. By collecting data on tenant types across a variety of circumstances like geography, urban density, trade are types, etc., we can figure out what characteristics certain tenant types are willing to pay more for. |
| Maximize consumer draw                      | Average foot traffic volume to the property.                                                                                                                                                                                                                                                                                                    |
| Maximize consumer visit duration            | Average time spent per visit to the property.                                                                                                                                                                                                                                                                                                   |
| Minimize Tenant Improvement Allowance (TIA) | We estimate how many tenant improvement dollars it would take to convert a space from the current tenant type to the target tenant type. We can do this because we have data on common industry requirements for the space infrastructure, utility composition, etc., across tenant types                                                                                      |

<h1> What data are you using? </h1>
### At a high level, data comes from four sources: 

1. **Property profiles**
2. **Property tenant-mix profiles**
3. **Trade area demographics**
4. **Trade area competition**

Each of these sources is broken down so we can measure, optimize, and balance specific aspects of tenant selection that each stakeholder cares about. Let's break them down.

#### Property Profiles 
*Property profiles* consist of the U.S. state, property GLA, and GLA of the vacant space(s).

#### Property Tenant Mix Profiles
*Property Tenant Mix Profiles* are a combination of proprietary metrics that measure how competitive and diverse the property's tenant mix is.

We created a single metric, called the **Tenant Mix Index (TMI)**, that combines two things that both leasing agents and prospective retailers care about: how competitive the property is and how diverse the property is. The **TMI** reflects a balance between these, and has the ability to emphasize one over the other through weighting. A higher score indicates that the property is strong in both aspects, or exceptionally strong in one if heavily weighted. 100% is the maximum **TMI**, 0% is the minimum. Diversity and competitiveness default to equal weighting when calculating **TMI** for a property. But if customers prefer, Dr. Fill can reverse engineer if your tenant mix strategy values diversity or competitiveness more and adapt recommendations accordingly. 


#### Trade Area Competition
Trade Area Competition is measured in terms of the level of competition and the quality of that competition. 
* *Level of Competition.* How many businesses of the same tenant type are within the trade area.
* *Quality of Competition.* The average 5 star Google Review of those businesses.

#### Trade Area Demographics

We analyze demographics of the trade area as well. Specifically: 
* Average household income
* Average education levels
* Average  home values  

Recommendations prioritize these four sources because they drive outcomes that many Retail CRE stakeholders care about. 
Retailers care about finding a location that helps their business thrive.
Leasing agents care about making retailers happy, reducing time off market, and fulfilling corporate tenant mix strategy. 
Commercial Real Estate management cares about financial stability, minimizing tenant turnover, maximizing consumer draw and visit duration, and maximizing overall property desirability. 

<h1>How do you know the recommendations are good? </h1>

Our first priority is making *useful* recommendations. And we can’t do that if they’re not good. We evaluate the goodness of recommendations by looking at many different metrics across many different geographies, property profiles, and trade areas, to figure out when recommendations are good. In fact, we have no single definition or dimension of ‘goodness’. Our many evaluation metrics and what they are are:

| Evaluation Metric | What it is & why it matters                                                                                                                                                                                                                                                                                                                                                                                                                             | How It’s Measured                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Utility           | The expected value in KPI’s like dollars that REITs get from the recommendation.                                                                                                                                                                                                                                                                                                                                                                       | The cumulative reward functions for each objective above. Each objective has its own cumulative reward. The sum of all the rewards is the total utility of a recommendation. The higher a recommendation’s utility, the more useful it is and ultimately the more valuable it is if followed.                                                                                                                                                                                                |
| Risk              | How variable utility is.                                                                                                                                                                                                                                                                                                                                                                                                                               | In some cases a recommendation may be associated with a potential risk. For example, some users may wish to be risk-averse, preferring tenants with lower rent willingness, but also a lower risk of turnover. We measure this as the variance of the utility metric.                                                                                                                                                                                                                   |
| Adaptiveness      | The ability to use recent information, like the most recent trade area data, in recommendations                                                                                                                                                                                                                                                                                                                                                         | The average age of each data point from its last refresh times how much weight the data point carries in the recommendation.                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Accuracy          | How close to the truth the model is.                                                                                                                                                                                                                                                                                                                                                                                                                   | We measure how accurately we can rank tenant types from most useful to least useful. We train a model on all the data we have on properties, mask the actual correct tenant type, then ask the model to see if it can predict the masked tenant type. How far down the list of its recommendations the correct tenant type falls tells us how accurate it is. If the masked tenant is recommended first, the model is maximally accurate. If the actual tenant type is 10th in a top 10 list, it’s not accurate. |
| Coverage          | How much of the Retail CRE landscape it works for. This is measured for customers and properties.                                                                                                                                                                                                                                                                                                                                                      | Customer space coverage: not all REITs are created equal. While our model is training on new properties all the time, we have more data on some kinds than others. The more data we have, the better the “coverage” the model has for customers and properties with certain characteristics. Coverage here can be measured by the richness of the customer or property profile required to make a reliable recommendation. For example, maybe we learned that the model requires examples of 100 tenant types before it can make a good recommendation. |
| Confidence        | How much the machine learning models trust their own recommendations.                                                                                                                                                                                                                                                                                                                                                                                  | The most common measurement of confidence is the probability that the predicted value is indeed true, or the interval around the predicted value where a predefined portion (e.g. 95%) of the true values lie.                                                                                                                                                                                                                                                                         |
| Trust             | Your trust in its recommendations.                                                                                                                                                                                                                                                                                                                                                                                                                      | Subject matter experts consider recommendations to be intuitive, reasonable, useful, and insightful.                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Novelty           | Novel recommendations are recommendations for tenants that the user did not know about or wouldn’t have chosen themselves (but are nevertheless useful)                                                                                                                                                                                                                                                                                                 | Popular tenant types are less likely to be novel. So novelty can be taken into account by using an accuracy metric where the system does not get the same credit for correctly predicting popular tenants as it does when it correctly predicts unpopular tenants.                                                                                                                                                                                                                       |
| Serendipity       | How surprising the successful recommendations are.                                                                                                                                                                                                                                                                                                                                                                                                     | One can think of serendipity as the amount of relevant information that is new to the user in a recommendation. E.g., if the user has no history of managing a tenant type at a property like the one it’s being recommended for.                                                                                                                                                                                                                                                       |
| Diversity         | How heterogenous the set of recommendations are.                                                                                                                                                                                                                                                                                                                                                                                                          |   Count of unique tenant types in the recommendations.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |




<h1>How does the AI work? </h1>
Dr. Fill is a special breed of AI known as a [Deep Reinforcement Learning Agent](https://en.wikipedia.org/wiki/Deep_reinforcement_learning). This is just a fancy way of saying that it learns the best thing to do by exploiting strategies that have worked in the past and exploring better strategies through careful experimentation. Dr. Fills actions are its recommendations, its rewards are the expected utility of optimizing the above objective functions, and its environment is the combination of the property profile, trade area, and other defining physical details in the real world.


<h1>Where’s the data come from? </h1>

| Data                    | Source                                                               |
|-------------------------|----------------------------------------------------------------------|
| Property Profiles       | Public websites for non-customers.                      |
| Tenant Profiles         | Public websites for non-customers.                      |
| Vacancy Information     | Public websites for non-customers.                      |
| Site Plans              | Public websites for non-customers.                      |
| Trade Area Demographics | US Census Bureau                                                     |
| Trade Area Competition  | Level of competition: OSM OverPass API, Quality of competition: Google |



<h1>Where did the tenant type categories come from?</h1> 

We use 40+ tenant type descriptions from ULI Descriptions as the base and harmonize that with the tenant type information a customer has on file. We harmonize a customer’s tenant type data into the 40+ categories based on how semantically similar the tenant names and tenant category names are. E.g., Fast Casual - Asian and Asian Style Restaurant are both very similar semantically so belong in the same Tenant Type.

<h1>How do I use this info?</h1>

Anyway you’d like! We recommend using it to learn about specific drivers of your property’s dynamics and in conversations with prospective tenants to help close deals.


<h1> What's on your product roadmap? </h1>

Our AI Engineering team is actively working on a number of useful features. Check out the most recent product roadmap [here](https://github.com/orgs/AiCRE-Labs/projects/1/views/1). 
