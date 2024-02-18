Ex.No: 1 Implementation of Breadth First Search

# REGISTER NUMBER : 212221060206
# AIM:
To write a python program to implement Breadth first Search.

# Algorithm:
# Step-1
Start the program
# Step-2
Create the graph by using adjacency list representation
# Step-3
Define a function bfs and take the set “visited” is empty and “queue” is empty
# Step-4
Search start with initial node and add the node to visited and queue.
# Step-5
For each neighbor node, check node is not in visited then add node to visited and queue list.
# Step-6
Creating loop to print the visited node.
# Step-7
Call the bfs function by passing arguments visited, graph and starting node.
# Step-8
Stop the program.

# Program:
# Breadth first Search in python 
```
graph = {
 '5' : ['3','7'],
 '3' : ['2', '4'],
 '7' : ['8'],
 '2' : [],
 '4' : ['8'],
 '8' : []
 }
visited = [] # List for visited nodes.
queue = []     #Initialize a queue
def bfs(visited, graph, node): #function for BFS
  visited.append(node)
  queue.append(node)
  while queue:          # Creating loop to visit each node
    m = queue.pop(0) 
    print (m) 
    for neighbour in graph[m]:
      if neighbour not in visited:
        visited.append(neighbour)
       	queue.append(neighbour)

```
# Driver Code
print("Following is the Breadth-First Search")
bfs(visited, graph, '5')    # function calling

# Output:
![image](https://github.com/PoornimaKumar29/AI_Lab_2023-24/assets/106436734/62db4939-d0ac-4020-b477-ade6270f6ab7)


Result:
Thus the breadth first search order was found sucessfully.
