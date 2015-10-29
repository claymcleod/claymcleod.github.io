% Machine Learning in Wireless Sensor Networks
% Clay McLeod
% October 2015

## References

### Paper
> [M. A. Alsheikh, S. Lin, D. Niyato, and H. Tan, "Machine Learning in Wireless Sensor Networks: Algorithms, Strategies and Applications," CoRR, vol. abs/1405.4463, 2014. [Online]. Available: http://arxiv.org/pdf/1405.4463v2.pdf](http://arxiv.org/pdf/1405.4463v2.pdf)

\vspace{12 mm}

> Viewable at [http://bit.ly/wsn-ml](http://bit.ly/wsn-ml)

## Overview

1. Brief introduction to Machine Learning
2. Applications of ML to Wireless Sensor Networks.
3. Drawbacks of using ML in Wireless Sensor Networks.
4. Two concrete solutions where ML is applied.

# Machine Learning

## Machine Learning

### Summary of ML

1. The development of computer models for learning processes that provide solutions to the problem of knowledge acquisition and enhance the performance of developed systems.

. . .

2. The adoption of computational methods for improving machine performance by detecting and describing consistencies and patterns in training data.

. . .

*Summary: exploit historical data to improve WSN performance at a given task*

## Machine Learning

### Supervised ML

Uses labelled data to build a predictive model (answer is known).

. . .

*Examples*

1. k-NN: Querying processing subsystem
2. Decision Tree: Assess link reliability (loss rate, corruption rate, mean time to failure, mean time to restore)
3. Neural networks: Any number of applications with high complexity (Big data tuning of parameters and dimensionality reduction)
4. Support vector machines: Security and localization
5. Bayesian statistics: Assessing event consistency, investigating knowledge about environment 

## Machine Learning

[svm]: assets/img/svm.png "Non-linear support vector machine"
![Non-linear support vector machine][svm]

## Machine Learning

### Unsupervised ML

Tries to find underlying patterns in data (answer not known).

. . .

*Examples*

1. K-means clustering: Clustering of nodes within a WSN

2. Principle component analysis (PCA): Reduce amount of transmitted data through dimensionality reduction.

## Machine Learning

![Principal component analysis](assets/img/principal.png "Principal component analysis")

## Machine Learning

### Reinforcement ML

Maximizes long-term rewards by using its own experience (find answers along the way).

. . .

*Example*:

1. Q-Learning: Routing optimization problems (multicast routing, geographic routing, feedback routing, Q-probabilistic routing).

## Machine Learning

![Visualization of Qlearning](assets/img/qlearn.png)

# Applications

## Applications

> * Monitor dynamic environments that change rapidly over time. (Ex. monitor a node's geographical location).

> * Calibrate a WSN to new knowledge about the environment (Ex. volcano eruption and waste water monitoring).

> * Modelling systems with high complexities/dimensions that make it difficult for mathematicians to model.

> * Extract important correlations between sensor data to propose further improvements to the system.

> * Intelligent decision making and autonomous control.

# Detriments

## Detriments

> * *Power consumption*: Many ML techniques are computationally expensive. Utilizing them in a wireless sensor network could have negative effects depending on how often the calculations are run.

> * *Data purity*: Generally speaking, ML perform better as the amount of data you have increases. Since WSNs are generally deployed in unpredictable environments, we cannot be sure what data we have coming into the system (except in supervised learning).

# Brief Note on Bayesian Statistics

## Bayesian Statistics

### Process

> * Model inputs/outputs as random variables, build model based on the distributions

> * Update bayesian model using existing data (prior)

> * Run thousands of random simulations to determine true distrobution of inputs/outputs.

## Bayesian Statistics

### Benefits for WSNs

> 1. Very fast execution, straightforward implementation

> 2. Low power consumption

> 3. **Works well on small amounts of sparse data/small amount of data**

> 4. Output is generally probabilities (except in ML paradigms, like Bayes network).

# Solutions

## Solutions

### Routing in WSNs

![Overview of ML routing techniques](assets/img/routing.png)

## Solutions

### Route Optimization

**Solution**: Q-Probabilistic Routing

QoS enabled routing protocol that uses reinforcement learning (specifically, Q-learning) and a Bayesian decision model to route packets.

\small{
1. Each node maintains a simple lookup table containing information on neighbors expected delivery rate (based on previous actions) and power constraints.

2. Bayesian model uses information in this lookup table, the importance of the message, and other metadata about a node (such as activity rate) to asses which node has the highest probability of giving us the fastest transmission time.

3. Node sends the packet and periodically communicates with its neighbor node to find out delivery times between the two nodes.

}

## Solutions

![QPR visualization of nodes](assets/img/qpr.png)

## Solutions

![QPR visualization of table](assets/img/qpr-table.png)

## Solutions

### Security Intrusion Detection

**Solution**: Distributed Bayesian Belief Network

Idea is simple: 

\small{
1. Given that the majority of nodes will have similar sensor readings, each node constantly monitors each of its neighbor nodes and builds a model of what an "average" node should look like (at each iteration).

2. This becomes the prior, causing the BBN to infer conditional relationships in the data.

3. Outlier detection is as trivial as setting a probability threshold for an outlier and communicating that to some centralized datastore.

\textbf{Bonus} - Quorum decision function: have each of the neighbor nodes vote on whether or not they think a certain node is an outlier. This prevents local outliers from being reported.
}

## Future Applications

* *Compressive Sensing and Sparse Coding*: data compression and dimensionality reduction to reduce communications across network, saving energy.

* *Distributed and Adaptive ML Techniques*: Distributed learning methods use less energy than centralized due to less communication. Spreading out computations across nodes will spread out energy consumption across the WSN, leading to longer overall life.

* *Resource Management*: Using ML to cease "nonfunctional and energy wasteful" activities, such as looping of packets.

* *Detect Spatial and Temporal Correlations*: Cluster based on temporal and spatial conditional correlations, decreasing communications and saving energy.

# Questions?
