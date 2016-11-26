---
layout: page
title: "HW8: CMPT231"
subtitle: "Lecture 10, ch22"
ext-js: "https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_CHTML"
---

{% include policies.md %}

### HW8 (20pts) [(solutions)](solns/)
Consider the directed graph with the following **adjacency list**:

`{1:[2, 3], 2:[1, 7], 3:[2], 4:[7, 8], 5:[2, 4, 6], 6:[5, 8], 8:[3, 4]}`

In the following, any iterations over the vertex list or over the
neighbours of a vertex should be done in order of vertex index.

1. *(1 pt)* Show the corresponding **adjacency matrix**.
2. *(2 pts)* **Draw** the graph.
3. *(3 pts)* Demonstrate a **breadth-first search** starting at 8.
4. *(3 pts)* Demonstrate a **depth-first search** on the graph.
  Show as much work as you can, including discovery/finish times.
5. *(1 pt)* Draw the **DFS forest** and the remaining edges.
  **Classify** all edges in the graph.
6. *(1 pt)* Show a **topological sort** of the graph from your DFS.
7. *(3 pts)* Demonstrate finding the **strongly-connected components**
  of the graph, and draw a *component graph*.
8. One graph problem we touched on in class but didn't dive into
  is **bipartite checking**.  An undirected graph is *bipartite* if 
  it is colourable using two colours (e.g., red and blue) such that
  no edge connects vertices of the same colour. <br/>
  More precisely, \`V = V\_r uu V\_b\`, with \`V\_r nn V\_b = O/\` 
  and \`u, v in V\_r => (u,v) !in E\` and \`u,v in V\_b => (u,v) !in E\`.
  + (a) *(5 pts)* Design (i.e., **pseudocode**) an algorithm to test
  if a graph is bipartite (return a boolean).  Use a BFS strategy.
  + (b) *(1 pt)* What is the **complexity** of your algorithm, assuming
  adjacency list representation?
  + (c) *(2 pts extra credit)* Design a DFS bipartite checker.
