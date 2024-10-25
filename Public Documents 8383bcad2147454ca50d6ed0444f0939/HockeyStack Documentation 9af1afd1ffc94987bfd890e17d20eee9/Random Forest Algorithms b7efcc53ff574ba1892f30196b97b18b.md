# Random Forest Algorithms

HockeyStack uses Random Forest algorithms for attribution, using data from all the journeys to dynamically identify what touchpoints influenced a given stage and hence should receive credit.

These models look at all journeys simultaneously, granting them the capacity to determine shared aspects across journeys.

HockeysSack's data-driven model works by developing a tree ensemble, a technique used in random forests, for each customer journey leading to a conclusion stage. Every stage has a distinct tree ensemble representing all account interactions along the journey. The model quantifies how probable it is for an account to encounter a certain touchpoint. To quantify a touchpoint's significance, HockeyStack calculates the feature importance – the change in conversion rate that would result if that touchpoint was absent from the analysis.

In essence, the 'feature importance' explains: the significance of a touchpoint is determined by how much the conversion rate changes when Touchpoint X is omitted from all journeys. Therefore, Touchpoint X must be crucial to the model and deserves more credit compared to other touchpoints that don't cause a substantial change in the conversion rate when omitted.

Through this approach, HockeyStack determines the weighting of different touchpoints, continuously recalibrating the model as it consumes more data.

**How much data do I need?**

You don't necessarily need a significant amount of data to start seeing valuable results with HockeyStack's algorithms.

Random Forest models are designed to handle a multitude of data sets, from small to large, providing actionable insights from whatever amount of data you can provide. They are just as effective at identifying patterns and trends in small datasets as they are in processing vast amounts of information.

That said, having an adequate volume of data provides a more comprehensive view of your customer journeys and touchpoints, allowing for a more accurate attribution.

**Random Forests vs Markov Chains, why did we choose Random Forests?**

1. Flexibility: Random Forests are non-parametric models, meaning they make few assumptions about the underlying data structure and patterns. This capability allows us to incorporate data from diverse sources, such as CRMs and various integrations.

2. Interpretability: Random Forests produce easily understood metrics, such as importance scores for each touchpoint, empowering teams to rapidly enhance their strategies based on these insights.

3. Scalability: Random Forests prove to be more efficient when it comes to large datasets. They maintain their accuracy and do not slow down in terms of computational speed, while Markov Chains can become computationally cumbersome with a surge in data size and complexity.