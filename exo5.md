PS5 – Fundamental Algorithm Techniques

Problem 1 – Tree Definitions

The goal was to show that all the common definitions of a tree actually describe the same thing.
I went through them one by one and connected them logically.

1. Connected + acyclic ⇒ one component of a forest

A forest is just an acyclic graph.
If our graph is acyclic and connected, then it’s exactly one connected component of a forest.

2. One forest component ⇒ connected with at most V−1 edges

A known fact:
A forest with k components has exactly E=V−k.
If there is only one component, then E=V−1. That’s the upper limit for an acyclic graph.

3. Connected with ≤ V−1 edges ⇒ minimally connected

A connected graph cannot have fewer than V−1 edges.
So “at most” becomes “exactly”.
If you remove any edge, the graph disconnects → minimal connectivity.

5. Minimally connected ⇒ acyclic + ≥ V−1 edges

If removing any edge breaks the graph, then it can't contain a cycle (a cycle always has a removable edge).
Also it must have at least V−1 edges to stay connected.

5. Acyclic + ≥ V−1 edges ⇒ maximally acyclic

An acyclic graph can have at most V−1 edges.
Having ≥ V−1 means it has exactly V−1.
Adding any edge creates a cycle → maximal acyclicity.

6. Maximally acyclic ⇒ unique path between any two vertices

If adding any edge forms a cycle, then the graph must already be connected.
In an acyclic graph, between any two vertices there can be only one path (two paths automatically form a cycle).

7. Unique path ⇒ connected + acyclic

If there is exactly one path between every pair of vertices:

it’s connected, and there are no cycles (a cycle would create two different paths).

That’s the original definition, so the loop closes.

Conclusion: all seven definitions describe the same structure: a tree.

Problem 2 – Sparse Graphs (CSC Format)

Vertices:
A=0, B=1, C=2, D=3, E=4

Graph 1 (Undirected)
Given CSC
col_pointers = [0, 2, 5, 8, 11, 12]
row_indices  = [1,2, 0,2,3, 0,1,3, 1,2,4, 3]

(a) Adjacency Matrix

Column interpretation:
| Vertex | Neighbors |
| ------ | --------- |
| A      | B, C      |
| B      | A, C, D   |
| C      | A, B, D   |
| D      | B, C, E   |
| E      | D         |

Matrix:

    A B C D E
A [ 0 1 1 0 0 ]
B [ 1 0 1 1 0 ]
C [ 1 1 0 1 0 ]
D [ 0 1 1 0 1 ]
E [ 0 0 0 1 0 ]

(b) Diagram (simple)
      B ---- D ---- E
     / \     /
    A---C----

Graph 2 (Directed)
Given CSC
col_pointers = [0,0,2,4,5,7]
row_indices  = [0,3, 0,1, 2, 1,3]

(a) Adjacency Matrix

Outgoing edges:

| Vertex | Edges |
| ------ | ----- |
| A      | —     |
| B      | A, D  |
| C      | A, B  |
| D      | C     |
| E      | B, D  |

Matrix:

    A B C D E
A [ 0 0 0 0 0 ]
B [ 1 0 0 1 0 ]
C [ 1 1 0 0 0 ]
D [ 0 0 1 0 0 ]
E [ 0 1 0 1 0 ]

(b) Diagram
C -> A
C -> B -> A
B -> D -> C
E -> B
E -> D

(c) Unique directed cycle

Following the arrows:

C → B → D → C

This is the only cycle in the graph.
