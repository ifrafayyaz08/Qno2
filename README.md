import java.util.LinkedList;

class Graph {
    private int vertices;
    private LinkedList<Integer> adjListArray[];

    // Constructor
    Graph(int vertices) {
        this.vertices = vertices;

        // Initialize the adjacency list array
        adjListArray = new LinkedList[vertices];

        // Create a new list for each vertex
        for (int i = 0; i < vertices; i++) {
            adjListArray[i] = new LinkedList<>();
        }
    }

    // Method to add an edge into the graph
    void addEdge(int src, int dest) {
        // Add an edge from src to dest
        adjListArray[src].add(dest);

        // Since the graph is undirected, add an edge from dest to src also
        adjListArray[dest].add(src);
    }

    // Method to print the adjacency list representation of the graph
    void printGraph() {
        for (int v = 0; v < vertices; v++) {
            System.out.print("Vertex " + v + ":");
            for (Integer node : adjListArray[v]) {
                System.out.print(" -> " + node);
            }
            System.out.println();
        }
    }

    public static void main(String args[]) {
        // Create a graph with 4 vertices
        int vertices = 4;
        Graph graph = new Graph(vertices);

        // Adding edges such that each vertex is connected to every other vertex
        graph.addEdge(0, 1);
        graph.addEdge(0, 2);
        graph.addEdge(0, 3);
        graph.addEdge(1, 2);
        graph.addEdge(1, 3);
        graph.addEdge(2, 3);

        // Print the adjacency list representation of the graph
        graph.printGraph();
    }
}
