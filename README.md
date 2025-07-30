### Problem Definition
1. Data Set: WHR2018Chapter2OnlineData.csv
2. What will you be predicting? What is the label?
In this unsupervised learning problem, I am aiming to discover inherent groupings of countries based on their well-being indicators. Unlike supervised learning, there isn't a pre-defined target label. Instead, the K-Means algorithm will generate clusters, and I will interpret these clusters as "labels" that represent different profiles of countries based on their happiness attributes.

NOTE: I use the information gained from the clusters to do a supervised learning problem. See the part after the cluster analysis.

3. What type of ML problem is this?
- Type: Unsupervised learning
- Subtype: Clustering
- Method: K-Means clustering
4. Features:
- Log GDP per capita
- Social support
- Healthy life expectancy at birth
- Freedom to make life choices
- Generosity
- Perceptions of corruption
5. Explain why this is an important problem:
Clustering countries based on these well-being indicators allows researchers, policymakers, and economists to:
- Identify groups of nations with similar social and economic patterns
- Inform targeted policy recommendations for improving well-being
- Understand regional or developmental disparities in quality of life

### Analysis of Cluster Means:
Cluster 0 (Profile: High Well-being and Developed Nations):
Log GDP per capita: High (10.62)
Social support: High (0.93)
Healthy life expectancy at birth: High (70.65)
Freedom to make life choices: High (0.90)
Generosity: High (0.18)
Perceptions of corruption: Low (0.44 - indicating low perceived corruption)

Cluster 1 (Profile: Lower Well-being and Developing Nations with Challenges):
Log GDP per capita: Low (7.73)
Social support: Low (0.69)
Healthy life expectancy at birth: Low (52.21)
Freedom to make life choices: Low-Moderate (0.67)
Generosity: Moderate (0.03)
Perceptions of corruption: High (0.79)

Cluster 2 (Profile: Moderately Developed Nations with Mixed Well-being):
Log GDP per capita: Moderate (9.54)
Social support: Moderate-High (0.84)
Healthy life expectancy at birth: Moderate (65.01)
Freedom to make life choices: Moderate (0.70)
Generosity: Low/Negative (-0.06)
Perceptions of corruption: High (0.83 - indicating high perceived corruption)


### Predictive Modeling (Classification based on Clusters)
Now that I have clustered the countries into "happiness profiles," I will treat these clusters as a new categorical label. This allows me to explore a supervised learning problem: can we predict a country's happiness cluster based on other features not used in the original clustering? This could be useful for identifying the characteristics that primarily drive a country into a certain happiness group.

The results of this supervised classification task demonstrate that the derived happiness clusters are indeed predictable using other measurable features.

- Predictability of Clusters: The accuracy scores of 62.5% (Decision Tree) and 68.5% (Random Forest) indicate that year, Confidence in national government, Positive affect, and Negative affect collectively hold significant predictive power for a country's happiness cluster membership. The Random Forest's higher accuracy suggests it's a more robust model for this task.
- Driving Factors: The feature importances consistently highlight that 'Confidence in national government' is the strongest predictor. This is a very insightful finding. It implies that a population's trust in its governing bodies is a primary factor in distinguishing between countries in the high, moderate, and lower well-being clusters you identified. 'Positive affect' and 'Negative affect' are also critical, showing that the emotional landscape of a country's citizens directly correlates with their broader happiness profile.
- Actionable Insights: This new analysis provides a different layer of insight. Beyond simply knowing what defines each cluster, you now know what other factors might predict a country's belonging to a particular cluster. For instance, if policymakers aim to shift a country from a "Lower Well-being" cluster to a "Moderately Developed" or even "High Well-being" cluster, these results suggest that focusing on building trust in government and fostering positive emotional environments could be impactful strategies. Businesses could also use these insights to tailor their approaches in countries with different levels of government confidence or prevailing emotional states.
