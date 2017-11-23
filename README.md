# graphcolouring
Graph Colouring Problem Code 

The steps followed for solving a graph coloring problem using SAT are as follows:

1. Input :

    a. Number of nodes
    
    b. Edges in the form of adjacency matrix
    
    c. Number of Colors

2. Identification of variables
  
    Example :: If a graph contains 4 nodes, say, a,b,c,d, then we these as 4 variables and also acolx,bcolx,ccolx,dcolx which are the logical variables and indicates if the vertices can have same or different colours with respect to the other vertex x.

3. Construction of Clauses

    Example :: (~a v ~b) is 1 means there exists an Edge between Vertex a and Vertex b. [a and b are the values for a and b in the adjacency matrix in the row for a or b]

4. 
    a. Assigning two colors(1 or 2) to vertices to specify if they can take same or different color values, on the basis of truth values assigned to literals, with respect to each vertex. [1 and 2 are not actual colors]
  
    1 means possibility of same color. 
    2 means must have different color.
    
    Example :: When (a v b) is 1 then Vertex b will be assigned 2 when checking Vertex a, else 1 will be assigned.

5. 
    
    a. Checking for each vertex, if the other vertices have different color possibility with respect to it.
    
    b. Then assign different color value if value assigned in last step is 2. 
    
    c. If the vertices have same color possibility, check if they are not adjacent to any other vertex having the possibility of same color.
        Example :: When checking with respect to vertex a, (~b v ~c) checks if edge exists between b and c.
        Then (~ccola v ~bcola) checks if b and c can have same colour with respect to a.
        Then (~b v ~c) v (~ccola v ~bcola) decides if b can hav same colour as a or not.
    
    d. If yes, then assign different color.
