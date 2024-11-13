# Ex.No: 4   Implementation of Alpha Beta Pruning 
### DATE: 22/8/2024                                                                          
### REGISTER NUMBER : 212222060012
### AIM: 

Write a Alpha beta pruning algorithm to find the optimal value of MAX Player from the given graph.

### Steps:

1. Start the program
2. Initially  assign MAX and MIN value as 1000 and -1000.
3.  Define the minimax function  using alpha beta pruning
4.  If maximum depth is reached then return the score value of leaf node. [depth taken as 3]
5.  In Max player turn, assign the alpha value by finding the maximum value by calling the minmax function recursively.
6.  In Min player turn, assign beta value by finding the minimum value by calling the minmax function recursively.
7.  Specify the score value of leaf nodes and Call the minimax function.
8.  Print the best value of Max player.
9.  Stop the program. 

### Program:

# Initial values of Alpha and Beta<br>
MAX, MIN = 1000, -1000<br>
# Returns optimal value for current player<br>
#(Initially called for root and maximizer)<br>
def minimax(depth, nodeIndex, maximizingPlayer,<br>
            values, alpha, beta):<br>
    # Terminating condition. i.e<br>
    # leaf node is reached<br>
    if depth == 3:<br>
        return values[nodeIndex]<br>
    if maximizingPlayer:<br>
        best = MIN<br>
        # Recur for left and right children<br>
        for i in range(0, 2): <br>
            val = minimax(depth + 1, nodeIndex * 2 + i,<br>
                          False, values, alpha, beta)<br>
            best = max(best, val)<br>
            alpha = max(alpha, best)<br>
            # Alpha Beta Pruning<br>
            if beta <= alpha:<br>
                break<br>
        return best<br>
    else:<br>
        best = MAX<br>
        # Recur for left and<br>
        # right children<br>
        for i in range(0, 2):<br>
            val = minimax(depth + 1, nodeIndex * 2 + i,<br>
                            True, values, alpha, beta)<br>
            best = min(best, val)<br>
            beta = min(beta, best)<br>
            # Alpha Beta Pruning<br>
            if beta <= alpha:<br>
                break<br>
        return best<br>
values = [3, 5, 6, 9, 1, 2, 0, -1] <br>
print("The optimal value is :", minimax(0, 0, True, values, MIN, MAX))<br>

### Output:

**![314007562-64b8a03b-17a7-474c-a291-d718a5b90a54](https://github.com/user-attachments/assets/2a724459-68cf-4989-baa7-42a0053048b9)


### Result:
Thus the best score of max player was found using Alpha Beta Pruning.
