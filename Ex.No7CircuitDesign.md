# Ex.No: 7  Logic Programming –  Logic Circuit Design
### DATE: 12/9/2024                                                                     
### REGISTER NUMBER : 212222060012
### AIM: 
To write a logic program to design a circuit like half adder and half subtractor.
###  Algorithm:
1. Start the Program
2. Design a AND gate logic if both inputs are 1 then output is 1.
3. Design a OR gate logic if any one of input is 1 then output is 1.
4. Design a XOR gate logic if both inputs are different then output is 1.
5. Design a NOT gate logic if input is 0 then output is 1.
6. Design a half adder and half subtractor using the rules.
7. Test the logic.
8. Stop the program.

### Program:


and(0,0,0).<br>
and(0,1,0).<br>
and(1,1,1).<br>
and(1,0,0).<br>
xor(1,0,1).<br>
xor(1,1,0).<br>
xor(0,1,1).<br>
xor(0,0,0).<br>
not(0,1).<br>
not(1,0).<br>
or(0,0,0).<br>
or(0,1,1).<br>
or(1,1,1).<br>
or(1,0,1).<br>
halfadder(A,B,Sum,Carry):-<br>
    xor(A,B,Sum),<br>
    and(A,B,Carry).<br>
halfsubtractor(A, B, Difference, Borrow):-<br>
    xor(A, B, Difference),<br>
    not(A, NA),<br>
    and(NA, B, Borrow).<br>

### Output:
![316234393-dc3ecb8f-ed99-40de-841d-5ef40006a223](https://github.com/user-attachments/assets/53664144-e189-4975-aa69-91fa1db6158e)



### Result:
Thus the truth table of circuit verified sucessfully.
