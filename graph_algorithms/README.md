# Graph searching algorithms

## Depth First Search (DFS)

DFS takes one node at a time and follows the entire depth of that node
before moving on to the next node. It's a recursive algorithm
that can be very costly if land on a particularly long path and your
destination node is not on it.

You'll want to keep track of the nodes you've visited
in the scenario that you have nodes with paths leading
back into themselves.

``` c#
class Node
{
    int Id;
    List<Nodes> AdjacentNodes;
}

public bool DFS(Node source, Node destination, HashSet<int> visited)
{
    if (visited.Contains(source.Id)) return false;
    
    visited.Add(source.Id);
    
    if (source == destination) return true;
    
    foreach (var child in source.AdjacentNodes)
    {
        if (DFS(child, destination, visited)) return true;
    }
    
    return false;
}
```

### Time Complexity

The time complexity is expressed as **O(V+E)** which is the **Nodes + Edges**.
This means the time complixity is **O(N) = linear**.

## Breadth First Search (BFS)

BFS works by only scanning the first level of all adjacent nodes
before moving on to the next level. You will need to use some
queue to store the Nodes you want to visit next.

``` c#
class Node
{
    int Id;
    List<int> AdjacentNodes;
}

public bool BFS(Node source, Node destination)
{
    var nextToVisit = new Queue<Node>();
    var visited = new HashSet<int>();
    nextToVisit.Enqueue(source);
    
    while (!nextToVisit.Empty())
    {
        var node = nextToVisit.Dequeue();
        
        if (node == destination) return true;
        
        if (visited.Contains(node.Id)) continue;
        
        visited.Add(node.Id);
        
        foreach (var child in node.AdjacentNodes)
        {
            nextToVisit.Enqueue(child);
        }
    }
    
    return false;
}
```

### Time Complexity

The time complexity is expressed as **O(V+E)** which is the **Nodes + Edges**.
This means the time complixity is **O(N) = linear**.

## Dijkstra's Algorithm

Dijkstra's algorithm is only allowed on weighted graphs
with non-negative edge weights. This constraint is imposed
to ensure that once a node has been visited its optimal distance cannot be improved.
You'll want to create a priority queue where the nodes with
the shortest distances are placed on top, including your
staring node, which will be on top.

You'll also want to keep track of where you've come from to a certain node.
You work through the nodes in a BFS type of fashion.

Everytime you finish processing a node's adjacent nodes, you remove that
node from the queue. You then move onto the next priority node and recalculate
the distances to all the nodes from the new node and then reprioritize the queue.

### Quick Algorithm Overview

- Maintain a 'dist' array where the distance to
every node is positive infinity. Mark the distance to the start node 's' to be 0.
- Maintain a priority queue (PQ) of key-value pairs of **(node index, distance)** pairs
which tell you which node to visit next based on sorted min value.
- Insert (s, 0) into PQ and loop while PQ is not empty pulling out next most promising
**(node index, distance)** pair.
- Iterate over all the edges outwards from the current node and relax each edge
appending a new **(node index, distance)** key-value pair to the PQ for
every relaxation.

### Pseudo Code

```
# Runs Dijkstra's algorithm and returns an array that
# contains the shortest distance to every node from
# the start node s.
# g - adjacency list
# n - the number of nodes in the graph
# s - the index of the starting node (0 <= s <= n)
function dijkstra(g, n, s):
    visited = [false, false, ..., false] # size n
    distances = [inf, inf, ..., inf] # size n
    distances[s] = 0
    ipq = empty indexed priority queue
    ipq.insert(s, 0)
    
    while ipq.size() != 0:
        index, minValue = ipq.poll()
        visited[index] = true
        if distances[index] < minValue: continue
        for (edge : g[index]):
            if visited[edge.to]: continue
            newDist = distances[index] + edge.cost
            if newDist < distances[edge.to]:
                distances[edge.to] = newDist
                if !ipq.contains(edge.to):
                    ipq.insert(edge.to, newDist)
                else:
                    ipq.decreaseKey(edge.to, newDist)
    return distances
```

### Time Complexity

There are different ways of implementing Dijkstra's algorithm and
different data structures that you can use, but the time complexity
is typically **O(E*log(V)**.

## A* Search

asd.

