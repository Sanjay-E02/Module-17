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

```
from collections import defaultdict

# This class represents a directed graph
# using adjacency list representation
class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	# function to add an edge to graph
	def addEdge(self,u,v):
		self.graph[u].append(v)

	# Function to print a BFS of graph
	def BFS(self, s):

		# Mark all the vertices as not visited
		visited = [False] * (max(self.graph) + 1)

		# Create a queue for BFS
		queue = []

		# Mark the source node as
		# visited and enqueue it
		queue.append(s)
		visited[s] = True

		while queue:
		    s=queue.pop(0)
		    print(s,end=" ")
		    
		    for i in self.graph[s]:
		        if visited[i]==False:
		            queue.append(i)
		            visited[i]=True
		
		
		
		

# Create a graph given in
# the above diagram
n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print ("Following is Breadth First Traversal"
				" (starting from vertex {})".format(n))
g.BFS(n)

```

## OUTPUT
![image](https://github.com/user-attachments/assets/0823e1a5-fa2c-47e9-81b9-46a73289f1c7)


## RESULT
Thus the python program was initialised and executed successfully.
