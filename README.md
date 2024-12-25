# topsort
Topological Sorting for Golang

## Explaination

Topological sorting algorithms are especially useful for dependency calculation, and so this particular implementation is mainly intended for this purpose. As a result, the direction of edges and the order of the results may seem reversed compared to other implementations of topological sorting.

For example, if:

* A depends on B
* B depends on C

The graph is represented as:

```
A -> B -> C
```

Where `->` represents a directed edge from one node to another.

The topological ordering of dependencies results in:

```
[C, B, A]
```

The code for this example would look something like:

```go
// Initialize the graph.
graph := topsort.NewGraph[string]()

// Add edges.
graph.AddEdge("A", "B")
graph.AddEdge("B", "C")

// Topologically sort node A.
graph.TopSort("A")  // => [C, B, A]
```

## Notes
Personally I think this codebase is really horrible on the side of usability, too much internals, not enough methods
My endgoal is making it so it's easier to use and manipulate and that's what I'll do in the upcoming releases
