# Experiment 11(c): DFS Traversal

## Aim
To write a Python program to print DFS (Depth-First Search) traversal from a given source vertex in a graph.

---

## Algorithm

1. **Start the program**:
   - Create a graph using an adjacency list representation.
   - Add edges between vertices using the `addEdge()` function.

2. **Implement the DFSUtil function**:
   - This function will recursively visit and print each unvisited vertex.
   - Mark the current vertex as visited.
   - Recursively call `DFSUtil()` for each unvisited adjacent vertex.

3. **DFS function**:
   - Initialize an empty set to keep track of visited vertices.
   - Call the `DFSUtil()` function starting from the given vertex.

4. **Input**:
   - The user provides the starting vertex for the DFS traversal.

5. **Perform DFS traversal**:
   - Start from the given source vertex and traverse all reachable vertices using DFS.
   - Print the vertices in the DFS order.

6. **End the program**:
   - The program outputs the order of vertices visited during the DFS traversal.

---

## Program

```python
# Python3 program to print DFS traversal
# from a given graph
from collections import defaultdict

# This class represents a directed graph using
# adjacency list representation


class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	# function to add an edge to graph
	def addEdge(self, u, v):
		self.graph[u].append(v)

	# A function used by DFS
	def DFSUtil(self, v, visited):

		# Mark the current node as visited
		# and print it
		visited.add(v)
		print(v, end=' ')

		# Recur for all the vertices
		# adjacent to this vertex
		for neighbour in self.graph[v]:
			if neighbour not in visited:
				self.DFSUtil(neighbour, visited)

	# The function to do DFS traversal. It uses
	# recursive DFSUtil()
	def DFS(self, v):

		# Create a set to store visited vertices
		visited = set()

		# Call the recursive helper function
		# to print DFS traversal
		self.DFSUtil(v, visited)

# Driver code


# Create a graph given
# in the above diagram
n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print("Following is DFS from (starting from vertex {})".format(n))
g.DFS(n)


```

## OUTPUT

![434657337-c6ce2e1b-dba4-431b-bd9a-0cbc9c586f26](https://github.com/user-attachments/assets/cc19ec92-45c1-459a-a947-84ced5f78a06)

## RESULT
The function performs a recursive DFS traversal and prints the nodes in the order they are visited starting from the given source vertex.
