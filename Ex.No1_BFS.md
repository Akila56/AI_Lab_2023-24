# Ex.No: 1  Implementation of Breadth First Search 
### DATE: 8.8.2024                                                                          
### REGISTER NUMBER : 212222060012
### AIM: 
To write a python program to implement Breadth first Search. 
### Algorithm:
1. Start the program
2. Create the graph by using adjacency list representation
3. Define a function bfs and take the set “visited” is empty and “queue” is empty
4. Search start with initial node and add the node to visited and queue.
5. For each neighbor node, check node is not in visited then add node to visited and queue list.
6.  Creating loop to print the visited node.
7.   Call the bfs function by passing arguments visited, graph and starting node.
8.   Stop the program.
### Program:
graph={<br>
    '2':['3','4'],<br>
    '3':['5'],<br>
    '4':['6','7'],<br>
    '6':[ ],<br>
    '5':['6'],<br>
    '7':['8'],<br>
    '8':[ ]<br>
}<br>
visited=[]<br>
queue<br>
def bfs(visted,node,graph):<br>
    visited.append(node)<br>
    queue.append(node)<br>
    while queue:***<br>
        m=queue.pop(0)<br>
        print(m)<br>
        for neighbour in graph[m]:<br>
            if neighbour not in visited:<br>
                visited.append(neighbour)<br>
                queue.append(neighbour)<br>
print("BFS order is")<br>
bfs(visited,'2',graph)<br>

### Output:
![image](https://github.com/user-attachments/assets/8ddf5d05-d5a1-40ba-a74a-2554b9a4c733)

### Result:
Thus the breadth first search order was found sucessfully.
