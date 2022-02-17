# GDP Machine Learning Model
### Ravi Shankar
### 2/17/22

GDP is an important indicator of economic activity in a nation. GDP is the sum of values (in USD) of products produced in a nation during a year, including net exports. The GDP/ capita (The GDP of a nation divided by its population) varies significantly among countries of the world, and has major impacts on the people.

We want to find a model to see what factors correlate with GDP/ capita. 

**Data comes via the World Bank, and the data across all listed countries was taken from 2018** because that was the most complete and recent year.

Worldbank's [GDP](https://data.worldbank.org/indicator/Ny.Gdp.Mktp.Cd) data will be compared with these other indexes:

- [Population](https://data.worldbank.org/indicator/SP.POP.TOTL)
- [Number secure internet servers/ million people](https://data.worldbank.org/indicator/IT.NET.SECR.P6)
- [Exports (as percentage of GDP)](https://data.worldbank.org/indicator/NE.EXP.GNFS.ZS)
- [Imports (as percentage of GDP)](https://data.worldbank.org/indicator/NE.IMP.GNFS.ZS?view=chart)

We will create a [Regression Decision Tree](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeRegressor.html) to see which features best seperate GDP/capita and tease out any trends or relationships between the features. This is an example of explanatory modelling. 

This model will also give us the ability to predict GDP. If there was a hypothetical new country where we knew their population, what percentage of their GDP is imports/exports, number of internet servers, etc., then we would have a data-based estimate of what their GDP would be.

# Resulting Model

![GDPTree](./GDPtree2.png)

# Conslusions

It was found that internet servers per capita was the best feature for seperating GDP per capita.


After that, population is the feature with the strongest effect on determining GDP/capita.

Also some nodes had only one sample, indicating outliers with unique combinations of statistics. For instance:
- 13 countries had over 42,700 internet servers/ million population, but only 1 country out of those had exports over 194% of their GDP (**Luxembourg**)
- 37 countries had between 8,112 and 42,748 internet servers/ million population, but only 1 country out of those had a population less than 223,495 (**Bermuda**)