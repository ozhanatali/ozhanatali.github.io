---
layout: post
title: Clustering-Algorithms
categories: AI
tags: AI Artificial+Intelligence
konum: İstanbul
---

| **Clustering   Algorithm**                                                           | **Type**                                                                                           | **Logic**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | **Pros**                                                                                                                                                                                         | **Cons**                                                                                                                                                                                | **Best Use Cases**                                                                                                                         |
|--------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| K-means                                                                              | centroid-based                                                                                     | This algorithm tries to minimize   the variance of data points within a cluster. It's also how most people are   introduced to unsupervised machine learning.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |     - Simple and computationally efficient for large datasets.<br>       - Easy to interpret and understand;   performs well with spherical clusters.                                            |     - Sensitive to initial centroid positions and can converge to local   minima.<br>       - Not effective for non-spherical   or unevenly sized clusters; does not handle noise well. |     - Customer segmentation, image compression, and other tasks where   clusters are roughly spherical and well-separated.                 |
| DBSCAN   - Density-based spatial clustering of applications with noise.              | density-based                                                                                      | DBSCAN uses two parameters to   determine how clusters are defined: minPts (the minimum number of data points   that need to be clustered together for an area to be considered high-density)   and eps (the distance used to determine if a data point is in the same area   as other data points).                                                                                                                                                                                                                                                                                                                                                                                |     - Can detect arbitrary-shaped clusters and works well with   outliers.<br>       - Does not require the number of   clusters in advance.                                                     |     - Struggles with clusters of varying density; sensitive to parameter   selection.<br>       - Does not perform well with   high-dimensional data.                                   |     - Geospatial data clustering, noise detection in large datasets, and   situations where clusters are non-spherical.                    |
| Gaussian   Mixture Model (GMM)                                                       | Distribution-based   (Probabilistic)                                                               | Uses multiple Gaussian   distributions to fit arbitrarily shaped data. The model calculates the   probability that a data point belongs to a specific Gaussian distribution and   that's the cluster it will fall under.                                                                                                                                                                                                                                                                                                                                                                                                                                                            |     - Can model clusters of different shapes and sizes, assuming a   Gaussian distribution for each cluster.<br>       - Provides probabilistic cluster   membership, allowing soft assignments. |     - Sensitive to the initial parameters and can converge to local   optima.<br>       - Computationally intensive for   high-dimensional data.                                        |     - Financial modeling and anomaly detection, tasks with overlapping or   ellipsoidal clusters.                                          |
| BIRCH -   The Balance Iterative Reducing and Clustering using Hierarchies            | Hierarchical-based (although it   combines elements of centroid-based and hierarchical approaches) | Works better on large data sets   than the k-means algorithm. It breaks the data into little summaries that are   clustered instead of the original data points. The summaries hold as much   distribution information about the data points as possible.                                                                                                                                                                                                                                                                                                                                                                                                                           |     - Scalable to large datasets; efficient in terms of memory   usage.<br>       - Can be used to initialize other   clustering methods.                                                        |     - Performs poorly with non-spherical clusters.<br>       - May merge clusters prematurely if   thresholds are not chosen carefully.                                                 |     - Large datasets requiring efficient clustering, such as retail   customer data and sales analysis.                                    |
| Affinity   Propagation                                                               | Uses a message-passing approach   that can be loosely categorized as graph-based                   | This clustering algorithm is   completely different from the others in the way that it clusters data. Each   data point communicates with all of the other data points to let each other   know how similar they are and that starts to reveal the clusters in the data.   You don't have to tell this algorithm how many clusters to expect in the   initialization parameters.<br>     As messages are sent between data points, sets of data called exemplars are   found and they represent the clusters.<br>     An exemplar is found after the data points have passed messages to each   other and form a consensus on what data point best represents a   cluster.<br>      |     - Automatically determines the number of clusters based on the   data.<br>       - Works well for non-spherical   clusters and does not require initial centroids.                           |     - Memory and computation-intensive for large datasets.<br>       - Sensitive to parameter choices,   especially the preference parameter.                                           |     - Situations where the number of clusters is unknown, such as image   processing or document clustering.                               |
| Mean-Shift   (also referred to as the mode-seeking algorithm)                        | Centroid-based                                                                                     | Similar to the BIRCH algorithm   because it also finds clusters without an initial number of clusters being   set. This is a hierarchical clustering algorithm. It works by iterating over   all of the data points and shifts them towards the mode. The mode in this   context is the high density area of data points in a region. It will go   through this iterative process with each data point and move them closer to   where other data points are until all data points have been assigned to a   cluster.<br>                                                                                                                                                           |     - Does not require specifying the number of clusters; adaptable to   arbitrary-shaped clusters.<br>       - Effective for image processing   and segmentation.                               |     - Computationally expensive, especially for large datasets.<br>       - Performance is sensitive to the   selection of the bandwidth parameter.                                     |     - Image segmentation, object tracking, and tasks involving density   estimation.                                                       |
| OPTICS -   Ordering Points to Identify the Clustering Structure                      | Density-based                                                                                      | Only   processes each data point once, similar to DBSCAN. There's also a special   distance stored for each data point that indicates a point belongs to a   specific cluster.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |     - Similar to DBSCAN but can handle clusters with varying   densities.<br>       - Generates a reachability plot,   which can be used to determine cluster structures.                        |     - More computationally intensive than DBSCAN.<br>       - Requires parameter tuning for   optimal performance.                                                                      |     - Clustering tasks where density varies, such as geospatial data,   customer segmentation with complex density structures.             |
| Agglomerative   Hierarchy                                                            | Density-based                                                                                      | Most common type of hierarchical   clustering algorithm. It's used to group objects in clusters based on how   similar they are to each other. This is a form of bottom-up clustering, where   each data point is assigned to its own cluster. Then those clusters get   joined together. At each iteration, similar clusters are merged until all of   the data points are part of one big root cluster.<br>                                                                                                                                                                                                                                                                       | Provides a dendrogram, offering   insights into hierarchical relationships between clusters. Does not require   specifying the number of clusters in advance.                                    | Computationally expensive for   large datasets.Sensitive to the choice of distance metric.                                                                                              | Small to medium-sized datasets.   Understanding hierarchical structures in data, like social networks or   taxonomies.                     |
| Divisive   Hierarchical                                                              | Hierarchical-based                                                                                 | Starts with a top-down   clustering strategy. So it will start with one large root cluster and break   out the individual clusters from there.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Allows for soft clustering, so   data points can belong to multiple clusters with varying degrees of   membership. Useful for data with overlapping clusters.                                    | Computationally intensive,   especially for large datasets. Sensitive to the initial conditions and may   converge to local minima.                                                     | Pattern recognition in medical   imaging. Clustering in data with uncertainty, like natural language   processing.                         |
| Mini-Batch   K-means                                                                 | Centroid-based                                                                                     | Similar to K-means, except that   it uses small random chunks of data of a fixed size so they can be stored in   memory.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Provides a visual and   interpretable representation of high-dimensional data. Effective for   dimensionality reduction and clustering simultaneously.                                           | Can be challenging to tune and   interpret for non-visual purposes.Computationally intensive for large data.                                                                            | Exploratory data analysis,   particularly in customer segmentation. Image or signal processing tasks.                                      |
| Spectral   Clustering                                                                | Often considered graph-based as   it uses eigenvalues of a similarity matrix                       | This algorithm is completely   different from the others above. It works by taking advantage of graph   theory. This algorithm doesn't make any initial guesses about the clusters   that are in the data set. It treats data points like nodes in a graph and   clusters are found based on communities of nodes that have connecting edges.                                                                                                                                                                                                                                                                                                                                       |     - Effective for non-convex clusters and when clusters have complex   shapes.<br>       - Does not rely on distance metric   alone, allowing flexibility.                                     |     - Computationally expensive, especially for large datasets.<br>       - Requires constructing a   similarity matrix, which can be memory-intensive.                                 |     - Image segmentation, social network analysis, and any task where data   forms a complex graph structure.                              |
| Fuzzy   C-Means                                                                      | Centroid-based                                                                                     | Similar to K-means but with   “soft” assignments, allowing each data point to belong to multiple clusters   with varying degrees of membership (probabilistic assignment).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Allows for soft clustering, so   data points can belong to multiple clusters with varying degrees of   membership. Useful for data with overlapping clusters.                                    | Computationally intensive,   especially for large datasets. Sensitive to the initial conditions and may   converge to local minima.                                                     | Pattern recognition in medical   imaging. Clustering in data with uncertainty, like natural language   processing.                         |
| Self-Organizing   Maps (SOM)                                                         | Neural network-based                                                                               | SOMs are used to create a   low-dimensional representation of high-dimensional data and are commonly   applied in exploratory data analysis and visualization.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Provides a visual and   interpretable representation of high-dimensional data. Effective for   dimensionality reduction and clustering simultaneously.                                           | Can be challenging to tune and   interpret for non-visual purposes. Computationally intensive for large data.                                                                           | Exploratory data analysis,   particularly in customer segmentation. Image or signal processing tasks.                                      |
| Agglomerative   Information Bottleneck (AIB)                                         | Hierarchical-based                                                                                 | Focuses on clustering based on   mutual information by grouping points that provide the most information   compression. AIB is frequently used in tasks involving document clustering.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Focuses on preserving   information content, leading to meaningful clusters. Effective for tasks   requiring semantic grouping.                                                                  | Requires well-defined features   to calculate mutual information. Not commonly supported in standard   clustering libraries.                                                            | Document clustering and text   data. Any task where information preservation is key, like summarizing user   behavior data.                |
| CURE   (Clustering Using Representatives)                                            | Hierarchical-based with   representation-based techniques                                          | Uses representative points to   form clusters, which helps better handle outliers and clusters with irregular   shapes.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | Handles irregularly shaped   clusters and outliers well. Scalable to larger datasets compared to   traditional hierarchical clustering.                                                          | Can be computationally expensive   compared to simpler algorithms. Needs a good representation strategy for   optimal clustering.                                                       | Data with noise and outliers,   like geographical clustering. Image segmentation tasks with irregular cluster   shapes.                    |
| HDBSCAN   (Hierarchical Density-Based Spatial Clustering of Applications with Noise) | Density-based                                                                                      | An extension of DBSCAN, HDBSCAN   performs well on datasets with varying densities and automatically finds the   optimal number of clusters. It’s highly effective for complex clustering   tasks.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Can identify clusters of varying   densities. Automatically determines the optimal number of clusters.                                                                                           | More complex to understand and   implement than DBSCAN. Sensitive to the selection of minimum cluster size.                                                                             | Clustering biological or genetic   data with complex structures. Large, noisy datasets with variable densities.                            |
| K-medoids   (or Partitioning Around Medoids - PAM)                                   | Centroid-based                                                                                     | Similar to K-means but more   robust to noise and outliers. It uses actual data points (medoids) instead of   centroids, making it a better choice for categorical data or cases where   centroids aren't representative.                                                                                                                                                                                                                                                                                                                                                                                                                                                           | More robust to noise and   outliers than K-means. Uses actual data points as cluster centers, making it   more interpretable.                                                                    | Slower than K-means, especially   for large datasets. Sensitive to initialization.                                                                                                      | Categorical data clustering,   like user preferences. Small to medium datasets where interpretability is   essential.                      |
| Subspace   Clustering                                                                | Subspace-based                                                                                     | Specifically designed to handle   high-dimensional data by clustering in subsets of dimensions (subspaces).   Commonly used for gene expression data and image analysis.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Designed to handle   high-dimensional data by clustering in relevant subspaces.Effective for data   with clusters embedded in different feature subspaces.                                       | Computationally intensive due to   subspace search.Requires careful parameter tuning to find meaningful   subspaces.                                                                    | High-dimensional data like gene   expression datasets.Any task where features are only partially relevant for   different clusters.        |
| Spectral   Biclustering                                                              | Graph-based, specifically for   biclustering                                                       | Clusters rows and columns   simultaneously, ideal for applications like gene expression data where both   samples and features form meaningful clusters.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Simultaneously clusters both   rows and columns, making it suitable for data with dual structure. Effective   for tasks where relationships between both samples and features are   meaningful.  | More complex than standard   clustering methods.Requires careful tuning to achieve optimal results.                                                                                     | Gene expression analysis, where   both genes and conditions matter.Recommendation systems where both users and   products need clustering. |
| Principal   Direction Divisive Partitioning (PDDP)                                   | Hybrid of divisive and principal   component analysis (PCA)                                        | Uses PCA to partition data along   principal directions, combining the divisive clustering approach with   dimensionality reduction.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Combines hierarchical clustering   with PCA, helping to capture directions of maximum variance.Suitable for   large datasets due to divisive approach.                                           | Limited support in mainstream   libraries, so may require custom implementation.Sensitive to the choice of   principal components.                                                      | Large, high-dimensional datasets   like customer purchase behavior.Tasks requiring visualization of the   clustering process.              |
