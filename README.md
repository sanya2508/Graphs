# Graphs

## Introduction: 

* Graph is a data structure which has two components:
   1. Node/Vertex
   2. Edge (which connects two nodes)
* Types of graph:
   1. Directed Graph
   2. Undirected Graph
* Degree in a graph:
   * The number of edges that are incoming or outgoing in a graph.
   * In an undirected graph there are degerees.
       * Total degree of all the nodes = 2*edges. 
   * In a directed graph there are:
       1. Indegree (Incoming edge)
       2. Outdegree (Outgoing edge)
 * Path:
   * Path is a sequence of nodes or vertex such that none of the nodes are repeating or visited more than once.
 * Cyclic graph:
    * If there is a cycle in an undirected graph we can call that as an undirected cyclic graph.
      * Undirected acylic graph: Tree/no cycle.  
    * If there is a cycle in a directed graph we can call that as a directed cyclic graph.
      * Directed acyclic graph: No cycle.
 * Weighted graph:
    * Weighted directed graph.
    * Weighted undirected graph. 

<hr/>

## Graph representation in C++:
 1. <a href="https://github.com/sanya2508/Graphs/blob/main/a.%20Adjacency%20matrix%20representation.cpp">Adjacency matrix: </a>
    1. Find out the number of nodes.
    2. Check if it is one based indexing or zero based indexing.
       * If it is one based indexing we create 6*6 2D array.
    3. Fill the 2D array with zeroes.
    4. Iterate over all the edges and mark 1 whenever there is an edge present for that node. (adj[u][v] =1)
       * If the graph is undirected, mark the reverse edge 1 as well. (adj[u][v] =1) and (adj[v][u] =1) 
    * Disadvantages of using this method:
      1. We can only use adjacency matrix for smaller values of n.
    * Space complexity: O(n*n)
  
  2. <a href="https://github.com/sanya2508/Graphs/blob/main/b.%20Adjacency%20List%20Representation.cpp">Adjacency List: </a>
      1. If it's an undirected or directed graph, we are going to have vector<int> of an adjaceny array of size (n+1).
        * For directed:
           ```
           adj[u].push_back(v);
           ```
          
        * For undirected: 
          ```
          adj[u].push_back(v);
          adj[v].push_back(u);
          ```
          
   2. Then we can store adjacent nodes at each index for all the index in their respective vector. 
   * Space complexity: 
      * Undirected: O(N+2E)
      * Directed: O(N+E)
   * If there is an edge weight as well, then we can convert the vector into pair <int, int> instead of int.


<hr/>

## Connected components in a graph:
 * A graph can either be a connected graph, or disconnected graph.
 * In general, whatever code we write, we have to write for multiple components.

<hr/>

## Traversal Techniques:
  1. <a href="https://github.com/sanya2508/Graphs/blob/main/c.%20Breadth-First%20Traversal.cpp">Breadth-First Search (BFS): </a>
      * BFS is traversing the adjacent nodes at first, and after that moving on  to next nodes.
      * For each component:
        1. At first we have to take a visited array, and every thing will be marked as zero which means none of the nodes has been visited yet.
        2. Now, we take a queue, insert the first node into it, and mark it as visited in the visited array.
        3. Now, iterate till the queue is not empty.
        4. Take the topmost element of the queue, and remove that element from the queue.
        5. Take the adjacent nodes of the node that we popped from the queue, and insert those nodes into the queue (only if not visited). Mark visited for those nodes as well.
        6. Continue this till we get all the adjacent nodes, for all nodes. (The queue is empty).
      * Complexity:
        * Time complexity: O(N+E) -> N is time taken for visiting N nodes, and E is for travelling through adjacent nodes overall.
        * Space complexity: O(N+E) + O(N) + O(N) -> Space for adjacency list, visited array, and queue.
        
    
   2. <a href="">Depth-First Search:</a>
       * DFS is traversing the graph in depthward motion. It is a recursive function.
       * For each component:
         1. Create a visited array of size V+1. Mark all the indexes as zero.
         2. 
