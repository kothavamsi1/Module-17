# Experiment 11(a): Representation of Graph

## Aim
To write a Python program to generate a graph for a given fixed degree sequence.

---

## Algorithm

1. **Start the program**:
   - Read the degree sequence from the user input.
   - The degree sequence represents the number of edges connected to each vertex in the graph.
   
2. **Define the graph representation**:
   - Create an adjacency matrix to represent the graph. The matrix will be a square matrix where each element `mat[i][j]` is `1` if there's an edge between vertex `i` and vertex `j`, and `0` otherwise.

3. **Construct the graph**:
   - Loop through all pairs of vertices (`i`, `j`).
   - If both vertices `i` and `j` have remaining degrees greater than `0`, decrement their degree and add an edge between them in the matrix.

4. **Display the adjacency matrix**:
   - Print the adjacency matrix in a human-readable format.
   
5. **End the program**:
   - The graph is now represented by the adjacency matrix, and the program prints the matrix.

---

## Program

```python
# Python3 program to generate a graph
# for a given fixed degrees

# A function to print the adjacency matrix.
def printMat(degseq, n):
	
	# n is number of vertices
	mat = [[0]*n for i in range(n)]
	
	for i in range(n):
	    for j in range(i+1,n):
	        if(degseq[i]>0 and degseq[j]>0):
	            degseq[i]-=1
	            degseq[j]-=1
	            mat[i][j]=1
	            mat[j][i]=1
	
	# Print the result in specified form
	print("      ", end ="")
	for i in range(n):
		print(" ", "(", i, ")", end ="")
	print()
	print()
	for i in range(n):
		print("  ", "(", i, ")", end = " ")
		for j in range(n):
			print("  ", mat[i][j], end = " ")
		print()

# Driver Code
degseq=[]
for i in range(0, 5):
    ele = int(input())
  
    degseq.append(ele)
#degseq =[v0,v1,v2,v3,v4]

n = len(degseq)
printMat(degseq, n)


```

## OUTPUT

![image](https://github.com/user-attachments/assets/e9ba6ff4-6484-4be9-aaed-ce6aa0b0492d)


## RESULT
The result of graph representation is a structured way to store and organize vertices and edges, either using an adjacency matrix for dense graphs or an adjacency list for sparse graphs, enabling efficient traversal and manipulation of the graph.
