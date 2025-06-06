# Problem 1
# Theoretical Foundations of Equivalent Resistance Using Graph Theory

## 1. Ohm’s Law and Basic Circuit Principles

Ohm’s Law defines the linear relationship between voltage ($V$), current ($I$), and resistance ($R$):

$$
V = IR
$$

This foundational equation governs all passive resistive components in a circuit. It implies that for a constant resistance, the voltage is directly proportional to the current. 

**Key Relationships:**
- Voltage Drop: $V = IR$
- Current Flow: $I = \frac{V}{R}$
- Resistance Calculation: $R = \frac{V}{I}$

## 2. Series and Parallel Resistor Combinations

### Series Combination

Resistors are in series if they are connected end-to-end, with the same current passing through each:

$$
R_{\text{eq}} = R_1 + R_2 + \dots + R_n
$$

### Parallel Combination

Resistors are in parallel if they are connected to the same two nodes, sharing the same voltage:

$$
\frac{1}{R_{\text{eq}}} = \frac{1}{R_1} + \frac{1}{R_2} + \dots + \frac{1}{R_n}
$$

Equivalently, for two resistors:

$$
R_{\text{eq}} = \frac{R_1 R_2}{R_1 + R_2}
$$

## 3. Kirchhoff’s Circuit Laws

### Kirchhoff’s Current Law (KCL)

At any junction (node), the total current entering equals the total current leaving:

$$
\sum I_{\text{in}} = \sum I_{\text{out}}
$$

This law is a consequence of conservation of electric charge.

### Kirchhoff’s Voltage Law (KVL)

The sum of all voltage drops in a closed loop is zero:

$$
\sum V = 0
$$

This is derived from the conservation of energy principle in electrical circuits.

## 4. Graph Theory Concepts in Circuits

Circuits can be modeled as **graphs**, where:

- **Nodes (vertices)** represent junctions.
- **Edges** represent resistors or other components.
- **Weights** on edges represent resistance values.

### Key Definitions

- **Graph $G = (V, E)$**: A set of vertices $V$ and edges $E$.
- **Weighted Graph**: Each edge $e \in E$ has an associated weight $w(e)$, e.g., resistance $R$.
- **Connected Component**: A subgraph in which any two nodes are connected by a path.
- **Tree**: An acyclic connected graph.
- **Cycle**: A closed path where the start and end vertices are the same, and all other vertices are distinct.

### Circuit Graph Properties

- A **tree** in a circuit graph represents a minimal configuration connecting all nodes without forming loops.
- A **cycle** corresponds to a loop in the circuit, important in analyzing KVL.
- **Cutsets** and **loops** play a vital role in solving via node and mesh analysis.

---

> These theoretical foundations form the basis for advanced analysis techniques in graph-based circuit analysis, enabling algorithmic solutions for complex resistor networks.
# 2. Graph Representation of Circuits

To apply graph theory to electrical circuits, we must model the circuit as a mathematical graph. This abstraction allows algorithmic approaches to analyze and simplify circuits for computing equivalent resistance.

## ✅ Circuit as a Graph: Nodes and Edges

A **graph** $G = (V, E)$ consists of:

- **Vertices (Nodes) $V$**: Represent the junction points in a circuit, where two or more components are connected.
- **Edges $E$**: Represent circuit elements (primarily resistors in this context) connecting two nodes.

Each edge has an associated **resistance value**, modeled as a **weight** on the edge.

### Example:
A resistor $R$ connecting nodes $A$ and $B$ is an edge:

$$
e = (A, B), \quad w(e) = R
$$

### Important Considerations:
- Nodes correspond to points of electrical potential.
- Edges are undirected if current can flow in either direction.
- In directed graphs (for active components or signal flow), edge direction may indicate polarity or control flow.

## ✅ Storing Resistance Values: Edge Weights

Each resistor is stored as a **weighted edge** in the graph. The weight corresponds to the **resistance** $R$ in ohms $(\Omega)$.

- Edge between nodes $u$ and $v$: $e_{uv}$
- Resistance of edge $e_{uv}$: $w(e_{uv}) = R_{uv}$

This makes it possible to apply algorithms that consider weights, such as resistance summation rules or minimum spanning trees.

## ✅ Data Structures for Graph Representation

Several data structures can be used to represent circuit graphs. The choice depends on the desired efficiency and algorithm:

### 1. Adjacency List (Preferred for Sparse Graphs)

Stores a list of neighbors for each node, along with edge weights:

```python
graph = {
    'A': [('B', 100), ('C', 50)],
    'B': [('A', 100)],
    'C': [('A', 50)]
}
# 3. Graph Simplification Techniques

To compute the **equivalent resistance** between two nodes in a circuit graph, we apply a sequence of **graph simplification rules**. These involve identifying standard topological patterns (series, parallel, nested structures) and reducing them recursively or iteratively until a single equivalent edge remains.

---

## ✅ Rules for Detecting and Collapsing Resistor Combinations

### 1. Series Combinations

Resistors are in **series** if:

- They form a **single path** with no branches.
- The same current flows through all of them.
- Intermediate nodes have **degree 2** (i.e., connected to exactly two edges).

#### Collapse Rule:
If $R_1, R_2, \dots, R_n$ are in series:

$$
R_{\text{eq}} = R_1 + R_2 + \dots + R_n
$$

#### Graphically:
Collapse a **path** $A \rightarrow B \rightarrow C$ into $A \rightarrow C$:

$$
R_{AC} = R_{AB} + R_{BC}
$$

---

### 2. Parallel Combinations

Resistors are in **parallel** if:

- They connect the **same two nodes**.
- The voltage across each resistor is the same.
- Multiple edges exist between the same pair of nodes.

#### Collapse Rule:
For resistors $R_1, R_2, \dots, R_n$ in parallel between nodes $u$ and $v$:

$$
\frac{1}{R_{\text{eq}}} = \frac{1}{R_1} + \frac{1}{R_2} + \dots + \frac{1}{R_n}
$$

#### Two-edge example:
If edges $(u, v)$ have resistances $R_1$ and $R_2$:

$$
R_{\text{eq}} = \frac{R_1 R_2}{R_1 + R_2}
$$

#### Graphically:
Multiple edges $e_1, e_2$ between nodes $A$ and $B$ → replace with one edge:

$$
R_{AB} = \left( \frac{1}{R_{e_1}} + \frac{1}{R_{e_2}} \right)^{-1}
$$

---

## ✅ Handling Nested Combinations

Real circuits often contain **combinations of series and parallel resistors**, sometimes nested arbitrarily deep.

### Approach:
1. Identify **innermost reducible subgraphs** (lowest-depth combinations).
2. Simplify them into single resistances.
3. Repeat simplification until only a single edge remains between source and target.

### Example:
If you have:

- $R_1$ in series with the parallel combination of $R_2$ and $R_3$:

$$
R_{\text{eq}} = R_1 + \left( \frac{1}{R_2} + \frac{1}{R_3} \right)^{-1}
$$

Use **recursion** to handle nested groups:
- Simplify inner combinations first.
- Return reduced value to outer layer.

---

## ✅ Multiple Current Paths (Cycles and Meshes)

Circuits with **loops or cycles** require deeper analysis:

- Such graphs cannot be reduced purely by local simplifications.
- Must apply **graph traversal** or **matrix methods** (e.g., Laplacian, nodal/mesh analysis).

### Cycle Detection:
- Use **DFS** or **BFS** to detect cycles.
- Convert cycles into simpler structures using:
  - **Delta-to-Wye (Δ-Y) transformations**
  - **Mesh current analysis**

---

## ✅ Strategy for Recursive or Iterative Simplification

### Recursive Strategy

1. Traverse the graph recursively.
2. Identify base cases: pure series or parallel connections.
3. Apply simplification formulas.
4. Collapse subgraphs and propagate results up the recursion tree.

```python
def simplify(graph):
    if is_simple(graph):
        return compute_equivalent(graph)
    subgraph = find_reducible_subgraph(graph)
    reduced = simplify(subgraph)
    update_graph(graph, reduced)
    return simplify(graph)

