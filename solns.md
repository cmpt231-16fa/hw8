---
layout: page
title: "HW8 Solutions: CMPT231"
subtitle: "Lecture 10, ch22"
ext-js: "https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_CHTML"
---

### HW8 Solutions (20pts)

+ (1) *(1 pt)* Show the corresponding **adjacency matrix**.

  \`( (0, 1, 1, 0, 0, 0, 0, 0),
      (1, 0, 0, 0, 0, 0, 1, 0),
      (0, 1, 0, 0, 0, 0, 0, 0),
      (0, 0, 0, 0, 0, 0, 1, 1),
      (0, 1, 0, 1, 0, 1, 0, 0),
      (0, 0, 0, 0, 1, 0, 0, 1),
      (0, 0, 0, 0, 0, 0, 0, 0),
      (0, 0, 1, 1, 0, 0, 0, 0) )\`

+ (2) *(2 pts)* **Draw** the graph.

  ![hw8-2.svg](../img/hw8-2.svg)

+ (3) *(3 pts)* Demonstrate a **breadth-first search** starting at 8.

  ![hw8-3.svg](../img/hw8-3.svg)

+ (4) *(3 pts)* Demonstrate a **depth-first search** on the graph.
  Show as much work as you can, including discovery/finish times.

  | vertex | discover | finish |
  |--------|----------|--------|
  |    1   |      1   |    8   |
  |    2   |      2   |    5   |
  |    3   |      6   |    7   |
  |    4   |      9   |   12   |
  |    5   |     13   |   16   |
  |    6   |     14   |   15   |
  |    7   |      3   |    4   |
  |    8   |     10   |   11   |

+ (5) *(1 pt)* Draw the **DFS forest** and the remaining edges.
  **Classify** all edges in the graph.

  ![hw8-5.svg](../img/hw8-5.svg)
  + Green: **tree** edges
  + Blue: **cross** edges (different subtree or different tree in forest)
  + Purple: **back** edges (loops)
  + This graph has no **forward** edges.

+ (6) *(1 pt)* Show a **topological sort** of the graph from your DFS.

  In reverse order of finish time:
  5, 6, 4, 8, 1, 3, 2, 7

+ (7) *(3 pts)* Demonstrate finding the **strongly-connected components**
  of the graph, and draw a *component graph*.

  The components are: (56), (48), (123), (7).

+ (8a) *(4 pts)* BFS bipartite checking:

  Make sure you cover all connected components of the graph;
  the original BFS only covered vertices reachable from a given source.

```
def bipartiteBFS( V, E ):
  new FIFO: Q
  new array: colour
  for v in V:				# initialisation
    colour[v] = WHITE
  
  for src in V:				# cover all components
    if colour[src] == WHITE:

      colour[src] = RED			# set source colour
      Q.push(src)

      while Q.notempty():
        u = Q.pop()
	for v in E.adj[u]:

	  if colour[v] == colour[u]:	# not 2-colourable
	    return FALSE

	  if colour[v] == WHITE:	# unvisited:
	    if colour[u] == RED:	#   alternate colour
	      colour[v] = BLUE
	    else:
	      colour[v] = RED
	    Q.push(v)			#   add to FIFO

  return TRUE
```

+ (8b) *(1 pt)* Complexity:

  Same as BFS: O(V + E)

+ (8c) *(2 pts extra credit)* DFS bipartite checking:

