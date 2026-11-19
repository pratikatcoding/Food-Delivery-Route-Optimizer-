# Food Delivery Route Optimizer

A console-based Java project that models a city road network as a
weighted graph and finds the shortest delivery route from a restaurant
to a customer using **Dijkstra's algorithm**, a **Min-Heap
(PriorityQueue)**, and **HashMap**.

## Project Overview

Food delivery platforms need efficient routes to reduce delivery time
and distance. This project demonstrates how core Data Structures and
Algorithms can solve a simplified route-optimization problem.

The city is represented as a graph: - **Vertices** represent locations
such as restaurants, junctions, and customer areas. - **Edges**
represent roads connecting those locations. - **Edge weights** represent
distance (in kilometres) or travel time.

The program supports adding locations and bidirectional roads,
calculating shortest paths, and displaying the selected route with its
total weight.

## Key Features

-   Add locations to a simulated city road network.
-   Add bidirectional roads with non-negative weights.
-   Represent the road network using an adjacency list.
-   Find shortest routes using Dijkstra's algorithm.
-   Use a Min-Heap to efficiently select the next closest location.
-   Use HashMaps for location lookup, distance tracking, and parent
    tracking.
-   Reconstruct and display the complete route.
-   Handle invalid or unknown locations.

## Data Structures and Algorithms

  -----------------------------------------------------------------------
  Concept                             Purpose
  ----------------------------------- -----------------------------------
  Graph (Adjacency List)              Represents locations and the roads
                                      connecting them.

  Dijkstra's Algorithm                Computes shortest paths when all
                                      edge weights are non-negative.

  Min-Heap / `PriorityQueue`          Retrieves the location with the
                                      smallest known distance
                                      efficiently.

  `HashMap`                           Stores graph adjacency lists,
                                      distances, and parent
                                      relationships.
  -----------------------------------------------------------------------

## How It Works

1.  Build the city graph by adding locations and weighted roads.
2.  Select a source location (restaurant) and a destination (customer).
3.  Initialise all distances to infinity, except the source distance,
    which is zero.
4.  Insert the source into the Min-Heap.
5.  Repeatedly remove the location with the smallest distance and relax
    its neighbouring edges.
6.  Update a neighbour's distance and parent whenever a shorter route is
    found.
7.  Reconstruct the route by following the parent records backwards from
    the destination.
8.  Display the route and its total distance or travel-time weight.

## Example

The project report uses the following sample road network:

  Road                Weight
  ----------------- --------
  Restaurant -- A          4
  Restaurant -- B          2
  B -- A                   1
  A -- C                   5
  B -- C                   8
  C -- D                   3
  C -- Customer            4
  D -- Customer            1

**Sample shortest-route results:**

``` text
=== Food Delivery Route Optimizer ===

Finding Shortest Route: Restaurant -> Customer
Route: Restaurant -> B -> A -> C -> Customer
Total Distance: 12 km

Finding Shortest Route: Restaurant -> D
Route: Restaurant -> B -> A -> C -> D
Total Distance: 11 km

Invalid Location Test
Error: Location "Z" not found in the city map.
```

## Complexity Analysis

Let `V` be the number of vertices (locations) and `E` the number of
edges (roads).

  Operation                                               Time Complexity
  ------------------------------------------------------- --------------------
  Dijkstra's algorithm with a Min-Heap                    `O((V + E) log V)`
  Dijkstra's algorithm without a heap (as a comparison)   `O(V²)`
  HashMap lookup / insertion                              `O(1)` average
  Heap insertion / removal                                `O(log V)`
  Adjacency-list storage                                  `O(V + E)` space

## Technology and Requirements

-   **Language:** Java
-   **JDK:** Java 11 or later
-   **IDE:** VS Code, Eclipse, IntelliJ IDEA, or another Java-compatible
    editor
-   **Build:** `javac` from the JDK; Maven or Gradle may be used if
    configured

The project is designed to run on Windows, macOS, or Linux with a
compatible Java Development Kit installed.

## Run Locally

1.  Install Java JDK 11 or later.

2.  Clone this repository:

    ``` bash
    git clone <your-repository-url>
    ```

3.  Open the project directory.

4.  Compile the Java source files. For a simple project where the source
    files are in the current directory:

    ``` bash
    javac *.java
    ```

5.  Run the class that contains the `main` method. If that class is
    named `Main`, use:

    ``` bash
    java Main
    ```

> **Note:** The exact compile and run commands depend on the source
> filenames, package structure, and name of the class containing `main`.
> Update the commands above to match your repository.

## Project Structure

A possible organisation for the Java source files is:

``` text
Food-Delivery-Route-Optimizer/
├── src/
│   ├── Edge.java
│   ├── Node.java
│   ├── Graph.java
│   ├── RouteOptimizer.java
│   └── Main.java
└── README.md
```

This is a suggested layout based on the classes described in the project
report. Adapt it to the actual files in your repository.

## Limitations

-   The road network uses predefined sample data rather than live map
    data.
-   Edge weights are static; real-time traffic conditions are not
    included.
-   The current scope is a console-based, small-scale city simulation.
-   The route calculation assumes non-negative edge weights.

## Future Enhancements

-   Integrate live traffic data and dynamically update road weights.
-   Explore the A\* search algorithm to guide route exploration with a
    heuristic.
-   Support multiple deliveries and multi-stop route planning.
-   Integrate Google Maps or OpenStreetMap data.
-   Build a graphical interface using Java Swing or JavaFX.
-   Allocate orders to the nearest available delivery partner.

## Learning Outcomes

This project demonstrates practical use of graph modelling, adjacency
lists, greedy algorithm design, shortest-path computation, priority
queues, hash tables, route reconstruction, and time/space complexity
analysis.

## Author

**Pratik Karmakar**\
B.Tech -- Computer Science & Engineering (AI & ML)\
Rungta International Skills University\
Project: Food Delivery Route Optimizer\
Project No.: 93

## Academic Context

Developed as part of the **Data Structures and Algorithms** course,
Session **2026--27**.

**Project Guide:** Mr. Santanu Sasmal

------------------------------------------------------------------------

If you find this project useful for learning DSA, feel free to explore
the implementation and experiment with different city graphs and road
weights.
