---
layout: page
title: "HW8: CMPT231"
subtitle: "Lecture 10, ch22"
ext-js: "https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_CHTML"
---

{% include policies.md %}

### HW8 (20pts)
Consider the directed graph with the following **adjacency list**:

`{1:[2, 3], 2:[1, 7], 3:[2], 4:[7, 8], 5:[2, 4, 6], 6:[5, 8], 8:[3, 4]}`

In the following, any iterations over the vertex list or over the
neighbours of a vertex should be done in order of vertex index.

1. *(1 pts)* Show the corresponding **adjacency matrix**.
2. *(2 pts)* **Draw** the graph.
3. *(3 pts)* Demonstrate a **breadth-first search** starting at 8.
4. *(3 pts)* Demonstrate a **depth-first search** on the graph.
  Show as much work as you can, including discovery/finish times.
5. *(1 pts)* Draw the **DFS forest** and the remaining edges.
  **Classify** all edges in the graph.
6. *(1 pts)* Show a **topological sort** of the graph from your DFS.
7. *(3 pts)* Demonstrate finding the **strongly-connected components**
  of the graph, and draw a *component graph*.
8. *(6 pts)*
