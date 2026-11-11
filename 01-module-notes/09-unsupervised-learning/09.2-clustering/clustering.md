
# PART 1: UNDERSTANDING CLUSTERING

###### What is Clustering?
Clustering is an **unsupervised machine learning technique** that groups similar observations together based on their characteristics or features.

In simple terms, clustering allows a computer to discover natural groups in a dataset without being told beforehand which observation belongs to which group.

**Example: Student activity preferences**
Imagine collecting information from 100 students about their weekend activities:
* Hiking
* Swimming
* Going to the gym
* Watching sports
* Attending parties
* Shopping
* Going to concerts

Each student provides a rating from 1 to 10 for each activity.
You do not know which students are sporty, social, adventurous or artistic.

Using clustering, the algorithm examines their responses and identifies students with similar preferences.

<img src="img/example_clustering.png" alt="Example clustering" width="500">

The algorithm might identify groups such as:

**Cluster**	 ---   **Possible interpretation**

Cluster 1	---    Sporty and adventurous students

Cluster 2	---    Social and outgoing students

Cluster 3	---    Relaxed and less adventurous students

These descriptions are assigned by examining the characteristics of the resulting clusters. The algorithm itself does not know what a sporty or social student is.


**Important Terminology**

- **Observation / Individual**: One record or entity in the dataset, e.g. one student.
- **Feature / Variable**: A characteristic measured about an observation.
- **Dataset**: The complete collection of observations.
- **Cluster**: A group of similar observations.
- **Similarity**: How alike two observations are.
- **Dissimilarity**: How different two observations are.
- **Centroid**: The centre or average position of a cluster.
- **Cluster label**: The number assigned to identify a cluster.

**Understanding the dataset structure**

Suppose we have the following dataset:
| Student | Hiking | Swimming | Gym |
| --- | --- | --- | --- |
| Student A | 9 | 8 | 9 |
| Student B | 8 | 9 | 8 |
| Student C | 2 | 1 | 3 |
| Student D | 3 | 2 | 2 |
| Student E | 9 | 2 | 8 |

In this example:
- Number of observations (n) = 5 students.
- Number of features (p) = 3 activities.
- Each row represents one student.
- Each column represents one feature.

The objective is to allocate the five observations into \(k\) clusters, where \(k\) represents the number of groups.

For example, if \(k=2\), the algorithm attempts to divide the students into two groups based on their activity preferences.

**Remember**: In clustering, the correct group labels are not provided during training.

## Why do we use clustering?
Its three main objectives are:
1. Discover structure and patterns in data.
2. Group observations with similar patterns together.
3. Reduce complexity and make data easier to interpret.


## Real-life Applications
| Industry | Application |
| --- | --- |
| Marketing | Grouping customers according to purchasing behaviour |
| Banking | Identifying customers with similar financial behaviour |
| Healthcare | Grouping patients according to symptoms or medical characteristics |
| Education | Identifying students with similar learning patterns |
| E-commerce | Grouping customers according to shopping preferences |
| Agriculture | Grouping farms according to production patterns |
| Human Resources | Grouping employees according to skills and performance |

**Example: Customer Segmentation**
A retail company collects information about customers' spending habits.
Clustering may identify:
- Customers who frequently purchase expensive products.
- Customers who mainly purchase discounted products.
- Customers who purchase occasionally.
- Customers who spend heavily during promotions.
The company can then develop different marketing strategies for each group.

**Key takeaway**: Clustering helps businesses understand their data and make decisions based on discovered patterns.

## Supervised vs. Unsupervised Learning
| Supervised Learning | Unsupervised Learning |
| --- | --- |
| Training data contains known labels. | Training data has no known class labels. |
| Learns from labelled examples. | Discovers patterns from the data. |
| Predicts a known target or outcome. | Identifies hidden structures or groups. |
| Examples: classification and regression. | Examples: clustering and dimensionality reduction. |
| Cross-validation can evaluate predictive performance. | Ordinary supervised cross-validation is not directly applicable. |

_Example_
**Supervised learning**:

You provide a model with student information and already-known labels:
- Student A: Sporty.
- Student B: Social.
- Student C: Academic.

The model learns to predict the category of new students.

**Unsupervised learning**:

You provide student information without labels.

The algorithm discovers groups based on similarities in the data.

- Clustering is unsupervised because the actual class labels are unknown during the clustering process.

# PART 2: TYPES OF CLUSTERING ALGORITHMS

Introducing 3 `three` main approaches
1. Hierarchical clustering.
2. K-means clustering.
3. Model-based clustering.

<img src="img/clustering_algorithms.png" alt="Clustering Algorithms" style="max-width: 500px; width: 100%;">

| Method | Main Idea |
| --- | --- |
| Hierarchical | Builds a hierarchy of clusters by merging or splitting groups. |
| K-means | Divides observations into a predefined number of clusters using centroids. |
| Model-based | Assumes the data comes from a mixture of probability distributions. |

# PART 3: HIERARCHICAL CLUSTERING

###### What is hierarchical clustering?
Hierarchical clustering is an unsupervised learning method that creates a hierarchy of groups by progressively merging similar observations or separating existing groups.

***Agglomerative hierarchical clustering***.

- Agglomerative means bottom-up clustering.

It starts by treating every observation as an individual cluster. It then repeatedly merges the closest clusters until all observations belong to one large cluster.

**How does it work?**
Consider six observations:
A, B, C, D, E and F.

Initially, every observation is its own cluster:

<img src="img/agglomerative_hierarchical_clustering.png" alt="Agglomerative Hierarchical Clustering" width="70%">

- The exact order of merging depends on the distance measure and linkage method selected.

**The Two Main Types of Hierarchical Clustering**


| Agglomerative | Divisive |
|---|---|
| Bottom-up approach. | Top-down approach. |
| Starts with individual observations. | Starts with one large cluster. |
| Repeatedly merges clusters. | Repeatedly splits clusters. |
| Commonly used in practice. | Less commonly used. |


## What is a Dendrogram?

A Dendrogram is a tree-like diagram that visually represents the sequence of merges performed during hierarchical clustering.

<img src="img/dendrogram.png" alt="Dendrogram" width="70%">

**Understanding the Dendrogram**
A dendrogram contains four important elements:
1. **Leaf nodes**: The individual observations at the bottom of the diagram. 
2. **Branches**: Connections showing how observations or groups are merged.
3. **Internal nodes**: Points where two groups are joined.
4. **Root node**: The final group containing the entire dataset. 

**How to read a Dendrogram**

The vertical axis normally represents the distance or dissimilarity at which clusters are merged.
- Merges occurring at low heights indicate that the groups are relatively similar.
- Merges occurring at high heights indicate that the groups are more dissimilar.
- Large vertical gaps between merges can suggest useful places to cut the tree.

**How do we determine the number of clusters?**
We draw a horizontal line across the dendrogram.

The number of branches that the line intersects represents the number of clusters.

<img src="img/dendrogram_clustering.png" alt="Dendrogram Clustering" width="500">

For example:
- A cut intersecting 2 branches gives 2 clusters.
- A cut intersecting 3 branches gives 3 clusters.
- A cut intersecting 4 branches gives 4 clusters.

**Important**: Hierarchical clustering allows us to inspect the data structure before deciding how many clusters to retain.

## Dissimilarity and Distance Measures
Hierarchical clustering needs a way of determining which observations or groups are closest to one another.
- This is called **dissimilarity**.

Dissimilarity should satisfy these properties:

1. **Symmetry**:
$$d(a,b) = d(b,a)$$

- The distance from A to B is the same as the distance from B to A.

2. **Positivity**:
$$
d(a,b)\geq 0
$$

- Distance cannot be negative.

3. **Increasing Dissimilarity**

The distance increases as two observations become more different.




























































