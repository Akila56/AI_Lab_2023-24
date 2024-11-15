# Ex.No: 11  Planning –  Block World Problem 
### DATE:       3-10-2024                                                                     
### REGISTER NUMBER : 212222060012
### AIM: 
To find the sequence of plan for Block word problem using PDDL  
###  Algorithm:
Step 1 :  Start the program <br>
Step 2 : Create a domain for Block world Problem <br>
Step 3 :  Create a domain by specifying predicates clear, on table, on, arm-empty, holding. <br>
Step 4 : Specify the actions pickup, putdown, stack and un-stack in Block world problem <br>
Step 5 :  In pickup action, Robot arm pick the block on table. Precondition is Block is on table and no other block on specified block and arm-hand empty.<br>
Step 6:  In putdown action, Robot arm place the block on table. Precondition is robot-arm holding the block.<br>
Step 7 : In un-stack action, Robot arm pick the block on some block. Precondition is Block is on another block and no other block on specified block and arm-hand empty.<br>
Step 8 : In stack action, Robot arm place the block on under block. Precondition is Block holded by robot arm and no other block on under block.<br>
Step 9 : Define a problem for block world problem.<br> 
Step 10 : Obtain the plan for given problem.<br> 
     
### Program:
(define (domain blocksworld)<br>
(:requirements :strips :equality)<br>
(:predicates (clear ?x)<br>
             (on-table ?x)<br>
             (arm-empty)<br>
             (holding ?x)<br>
             (on ?x ?y))<br>
(:action pickup<br>
  :parameters (?ob)<br>
  :precondition (and (clear ?ob) (on-table ?ob) (arm-empty))<br>
  :effect (and (holding ?ob) (not (clear ?ob)) (not (on-table ?ob)) <br>
               (not (arm-empty))))<br>
(:action putdown<br>
  :parameters  (?ob)<br>
  :precondition (and (holding ?ob))<br>
  :effect (and (clear ?ob) (arm-empty) (on-table ?ob) <br>
               (not (holding ?ob))))<br>
(:action stack<br>
  :parameters  (?ob ?underob)<br>
  :precondition (and  (clear ?underob) (holding ?ob))<br>
  :effect (and (arm-empty) (clear ?ob) (on ?ob ?underob)<br>
               (not (clear ?underob)) (not (holding ?ob))))<br>
(:action unstack<br>
  :parameters (?ob ?underob)<br>
  :precondition (and (on ?ob ?underob) (clear ?ob) (arm-empty))<br>
  :effect (and (holding ?ob) (clear ?underob)<br>
               (not (on ?ob ?underob)) (not (clear ?ob)) (not (arm-empty)))))<br>

### Input 
(define (problem pb1)<br>
   (:domain blocksworld)<br>
   (:objects a b)<br>
   (:init (on-table a) (on-table b)  (clear a)  (clear b) (arm-empty))<br>
   (:goal (and (on a b))))<br>
### Output/Plan:
![326324956-d4f22e91-acf9-4a1d-bd18-6a42f29cfeb0](https://github.com/user-attachments/assets/83424a8b-3b94-4427-82f2-7a0af06fc92f)
![326325029-4e1e15ca-0d75-4e77-8ba1-2be2364352cd](https://github.com/user-attachments/assets/1e0bb952-6bc1-47b1-9f35-135cdb4f43f1)



### Result:
Thus the plan was found for the initial and goal state of block world problem.
