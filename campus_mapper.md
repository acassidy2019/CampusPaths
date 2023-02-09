# Campus Map Director (CMD) 
By: Adam Cassidy, Atticus Templeton, Jonathan Hamstra, and Owen Foster

## Purpose and Goals
The primary goal of Campus Map Director is to present to a user the shortest and most efficient route between two buildings on Whitworth Campus. In order to accomplish this, Campus Map Director uses an A* search algorithm to traverse a graph of vertices in edge-list format to find the shortest path between two vertices. 

## How to run Campus Map Director

### What is A*?
A* is a search algorithm derived from Dijkstra's algorithm. The main mechanism is the same as Dijkstra's, but What sets A* apart is that it factors in a hueristic when traversing graph and calculating shortest distances. When this hueristic is 0, A* is functionally equivalent to Dijkstra's, however in the A* algorithm used by CMD, the heuristic is the Euclidean distance between each vertex. 

## Assumptions Made:
Campus Map Director is very easy to use. CMD outputs a key with which numbers correspond to which buildings, then asks for the user the number of where they want to start and end. This should be very accessible to anyone. 

## A* Algorithm Psuedocode

Psuedocode for astar_v2

Pass in the string name of start node and end node

Visited <--- starting node data (name, parent)

candidates <--- first candidate, namely the starting node (node_cost, name, parent)

start infinite loop
    initialize next node as weight infinity
    
    find candidate node that is the cheapest node_cost
    remove the newly found candidate node from the list

    create a list with every child of the new node to be checked
    if it is the goal jump to FINISH code
    
    loop through every child node, checking for if it is the goal first,
    then calculate the G cost (path length plus added distance between previous node and this new node)
    then add the H cost
    (H cost is euclidian distance from node to goal)

    take this G + H value and append all the new info to the candidates list
		(the node weight, name of node, name of parent)

finally append the (node, parent) pair to the visited list now that it has been calculated

FINISH
    once we find the goal node, add the final connection to the visited list
    now create a moves list that holds the sequential order of each step in the path
    add the goal to it
    now take the parent node of this junction, and find the pair in visited where it
    is the main node

    then add that node to the moves list, and take it's parent as the new parent variable

    repeat until you have found the starting node

    reverse the order of the list and return it



