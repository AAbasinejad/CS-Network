# CS-Network
Repository for Homework __4__ of Algorithmic Methods for Data Mining - *__Group 1__*.

__Introduction__: Carry out some information from Computer Scientists network by applying the [Graph methods](https://networkx.github.io/).

__Data__: In this project we've used the [DBLP](http://dblp.uni-trier.de/) dataset. during the project we worked on two json file, *__full_dblp__* json file, which needs to be parsed and contains the entire network, and  *__reduced_dblp__* json file for testing and debugging, which needs to be parsed and contains a portion of the network.

__Modules__:

[Graph](https://github.com/AAbasinejad/CS-Network/blob/master/Graph.py): By processing JSON file create a graph, G, whose nodes are the authors. Two nodes are connected if they have at least one publication in common. Each edge is weighted in the following way:
<d1>
<p align="center">
  <img src="https://latex.codecogs.com/gif.latex?w(a_1,a_2)&space;=&space;1&space;-&space;J(p_1,&space;p_2)" title="Weight Formula" width="200"/>
</p>
</d1>

> where a1, a2 are authors, p1 and p2 are the set of publication of the two authors and, J(p1 , p2) represents the jaccard similarity between these two sets of publications.

In __Graph__ module we have two function, `def create_graph(inf_data):` which is to create a graph's nodes without edges, (this function must be called with a loaded json dataset file as a argument), and `def add_edges(inf_data,graph):` which is used to create weighted graph's edges, (this must be called with a loaded json dataset and the results nodes of previous function, in following way:

``` python
with open('reduced_dblp.json') as json_data:
    data = json.load(json_data)
G = Graph.create_graph(data)
Graph.add_edges(data,G)
```







