
# Graphs


### Terms

- Vertex 
  * A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.
- Edge 
  * An edge is a connection between two nodes.
- Neighbor 
  * The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.
- Degree 
  * The degree of a vertex is the number of edges connected to that vertex.
- Undirected Graph 
  * is a graph where each edge is undirected or bi-directional. This means that the undirected graph does not move in any direction.
- Directed Graph also called a Digraph 
  * is a graph where every edge is directed. Unlike an undirected graph, a Digraph has direction. Each node is directed at another node with a specific requirement of what node should be referenced next.
- Complete graph 
  * all nodes are connected to all other nodes.
- Connected graph 
  * a graph that has all of vertices/nodes have at least one edge.
- Disconnected graph 
  * a graph where some vertices may not have edges.
- Acyclic Graph 
  *  a directed graph without cycles.  A cycle is when a node can be traversed through and potentially end up back at itself.
- Cyclic Graphs 
  *  a graph that has cycles.  A cycle is defined as a path of a positive length that starts and ends at the same vertex.
- Graph Representation 
  * We represent graphs through:
    * Adjacency Matrix
    * Adjacency List
- Adjacency Matrix 
  *  represented through a 2-dimensional array. If there are n vertices, then we are looking at an n x n Boolean matrix
- Adjacency List 
  *  the most common way to represent graphs. An adjacency list is a collection of linked lists or array that lists all of the other vertices that are connected.  Adjacency lists make it easy to view if one vertices connects to another.
- Weighted Graphs 
  *  a graph with numbers assigned to its edges. These numbers are called weights
- Traversals 
  * You will be required to traverse through a graph. The traversals itself are like those of trees. Below is a breakdown of how you would traverse a graph.
