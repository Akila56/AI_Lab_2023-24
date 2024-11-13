# Ex.No: 6   Logic Programming – Factorial of number   
### DATE:5-09-2024                                                                            
### REGISTER NUMBER : 212222060012
### AIM: 
To  write  a logic program  to solve Towers of Hanoi problem  using SWI-PROLOG. 
### Algorithm:
1. Start the program
2.  Write a rules for finding solution of Towers of Hanoi in SWI-PROLOG.
3.  a )	If only one disk  => Move disk from X to Y.
4.  b)	If Number of disk greater than 0 then
5.        i)	Move  N-1 disks from X to Z.
6.        ii)	Move  Nth disk from X to Y
7.        iii)	Move  N-1 disks from Y to X.
8. Run the program  to find answer of  query.

### Program:

move(1,X,Y,_) :-  <br>
    write('Move top disk from '), <br>
    write(X), <br>
    write(' to '), <br>
    write(Y), <br>
    nl. <br>
move(N,X,Y,Z) :- <br>
    N>1, <br>
    M is N-1, <br>
    move(M,X,Z,Y), <br>
    move(1,X,Y,_), <br>
    move(M,Z,Y,X).<br>


### Output:
![image](https://github.com/user-attachments/assets/07266686-b27f-464e-bc7c-ac333ed4dc73)


### Result:
Thus the solution of Towers of Hanoi problem was found by logic programming.
