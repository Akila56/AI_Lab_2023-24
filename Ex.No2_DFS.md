# Ex.No: 2  Implementation of Depth First Search
### DATE:   8/8/2024                                                                         
### REGISTER NUMBER : 212222060012

### AIM:

To write a python program to implement Depth first Search. 

### Algorithm:

1. Start the program
2. Create the graph by using adjacency list representation
3. Define a function dfs and take the set “visited” is empty 
4. Search start with initial node. Check the node is not visited then print the node.
5. For each neighbor node, recursively invoke the dfs search.
6. Call the dfs function by passing arguments visited, graph and starting node.
7. Stop the program.

### Program:

graph = {<br>
  '5' : ['3','7'],<br>
  '3' : ['2', '4'],<br>
  '7' : ['8'],<br>
  '2' : [],<br>
  '4' : ['8'],<br>
  '8' : []<br>
}<br>
visited = set() # Set to keep track of visited nodes of graph.<br>
def dfs(visited, graph, node):  #function for dfs <br>
    if node not in visited:<br>
        print (node)<br>
        visited.add(node)<br>
        for neighbour in graph[node]:<br>
            dfs(visited, graph, neighbour)<br>
            
# Driver Code:

print("Following is the Depth-First Search")<br>
dfs(visited,graph,'5')<br>

### Output:

![314004393-c8ee9d9c-caa8-417b-bb4b-c215f8ebab51](https://github.com/user-attachments/assets/e59dfb5e-c49a-4688-8644-2bd1702b9ee7)

### Result:
Thus the depth first search order was found sucessfully.
