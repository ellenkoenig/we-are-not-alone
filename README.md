# we-are-not-alone
Explore your social network with music

Dependencies
 * `jupyter` for running the notebooks
 * `python-twitter` for accessing the Twitter API
 * `networkx` for Social network and graph analysis
 * `matplotlib` for basic graph visualization
 * `audiolazy` for sound "visualization"


Rough idea  to convert graph into music

1) For all nodes (using `nodes_iter`), compute different centrality metrics using [NetworkX](https://networkx.github.io/documentation/networkx-1.10/reference/algorithms.centrality.html)
 * in_degree_centrality
 * out_degree_centrality
 * closeness_centrality
 * betweenness_centrality

2) Use the list of node metrics to create a series that can be converted into a music sequence