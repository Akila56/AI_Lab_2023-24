# Ex.No: 10  Logic Programming –  Simple queries from facts and rules
### DATE: 26.9.2024                                                                      
### REGISTER NUMBER : 212222060012
### AIM: 
To write a prolog program to find the answer of query. 
###  Algorithm:
 Step 1: Start the program <br> 
 Step 2: Convert the sentence into First order Logic  <br> 
 Step 3:  Convert the sentence into Horn clause form  <br> 
 Step 4: Add rules and predicates in a program   <br> 
 Step 5:  Pass the query to program. <br> 
 Step 6: Prolog interpreter shows the output and return answer. <br> 
 Step 8:  Stop the program.

 ### Task 1:
Construct the FOL representation for the following sentences <br> 
1.	John likes all kinds of food.  <br> 
2.	Apples are food.  <br> 
3.	Chicken is a food.  <br> 
4.	Sue eats everything Bill eats. <br> 
5.	 Bill eats peanuts  <br> 
   Convert into clause form and Prove that John like Apple by using Prolog. <br>

### Program:
food(apples).<br>
food(chicken).<br>
food(peanuts).<br>
likes(john, X) :-<br>
  food(X).<br>
eats(bill, X) :-<br>
 food(X).<br>
eats(sue, X) :-<br>
  eats(bill, X).<br>

### Output:
![image](https://github.com/user-attachments/assets/e10c8ebe-562a-43d7-8a61-93b61333df16)

### Task 2:
Consider the following facts and represent them in predicate form: <br>              
1.	Steve likes easy courses. <br> 
2.	Science courses are hard. <br> 
3. All the courses in Have fun department are easy <br> 
4. BK301 is Have fun department course.<br> 
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”<br> 
### Program:
likes(steve, X) :-<br>
 easy_course(X).<br>
hard_course(science).<br>
easy_course(X) :-<br>
 in_department(X, have_fun).<br>
in_department(bk301, have_fun).<br>

### Output:
![image](https://github.com/user-attachments/assets/50993243-27f9-482b-bcd2-f16c1c5b9ed4)

### Task 3:
Consider the statement <br> 
“This is a crime for an American to sell weapons to hostile nations. The Nano , enemy of America has some missiles and its missiles were sold it by Colonal West who is an American” <br> 
Convert to Clause form and prove west is criminal by using Prolog.<br> 

### Program:
criminal(X):-<br>
    american(X),<br>
    weapon(Y),<br>
    hostile(Z),<br>
    sells(X,Y,Z).<br>

weapon(Y):-<br>
    missile(Y).<br>

hostile(Z):-<br>
    enemy(Z,america).<br>

sells(west,Y,nano):-<br>
    missile(Y),<br>
    owns(nano,Y).<br>
missile(m).<br>
owns(nano,m).<br>
enemy(nano,america).<br>
american(west).<br>
### Output:
![image](https://github.com/user-attachments/assets/2acca31f-4def-4dfa-9cd7-4da541cf3ec0)

### Result:
Thus the prolog programs were executed successfully and the answer of query was found.
