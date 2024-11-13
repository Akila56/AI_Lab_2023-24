# Ex.No: 12  Planning –  Monkey Banana Problem
### DATE:   10-10-2024                                                                         
### REGISTER NUMBER : 212222060012
### AIM: 
To find the sequence of plan for Monkey Banana problem using PDDL Editor.
###  Algorithm:
Step 1:  Start the program <br> 
Step 2 : Create a domain for Monkey Banana Problem. <br> 
Step 3:  Create a domain by specifying predicates. <br> 
Step 4: Specify the actions GOTO, CLIMB, PUSH-BOX, GET-KNIFE, GRAB-BANANAS in Monkey Banana problem.<br>  
Step 5:   Define a problem for Monkey Banana problem.<br> 
Step 6:  Obtain the plan for given problem.<br> 
Step 7: Stop the program.<br> 


(define (domain monkey)	    <br>   
  (:requirements :strips)<br>
   (:constants monkey box knife bananas glass waterfountain)<br>
   (:predicates (location ?x)<br>
	       (on-floor)<br>
	       (at ?m ?x)<br>
	       (hasknife)<br>
	       (onbox ?x)<br>
	       (hasbananas)<br>
	       (hasglass)<br>
	       (haswater))<br>
   ;; movement and climbing<br>
  (:action GO-TO<br>
	     :parameters (?x ?y)<br>
	     :precondition (and (location ?x) (location ?y) (on-floor) (at monkey ?y))<br>
	     :effect (and (at monkey ?x) (not (at monkey ?y))))<br>
   (:action CLIMB<br>
	     :parameters (?x)<br>
	     :precondition (and (location ?x) (at box ?x) (at monkey ?x))<br>
	     :effect (and (onbox ?x) (not (on-floor))))<br>
   (:action PUSH-BOX<br>
	     :parameters (?x ?y)<br>
	     :precondition (and (location ?x) (location ?y) (at box ?y) (at monkey ?y) <br>
				 (on-floor))<br>
	     :effect (and (at monkey ?x) (not (at monkey ?y))<br>
			   (at box ?x)    (not (at box ?y))))<br>
  ;; getting bananas<br>
  (:action GET-KNIFE<br>
	     :parameters (?y)<br>
         :precondition (and (location ?y) (at knife ?y) (at monkey ?y))<br>
	     :effect (and (hasknife) (not (at knife ?y))))<br>
  (:action GRAB-BANANAS<br>
	     :parameters (?y)<br>
	     :precondition (and (location ?y) (hasknife) <br>
                                 (at bananas ?y) (onbox ?y))<br>
	     :effect (hasbananas))<br>
  ;; getting water<br>
  (:action PICKGLASS<br>
	     :parameters (?y)<br>
	     :precondition (and (location ?y) (at glass ?y) (at monkey ?y))<br>
	     :effect (and (hasglass) (not (at glass ?y))))<br>
  (:action GETWATER<br>
	     :parameters (?y)<br>
	     :precondition (and (location ?y) (hasglass)<br>
				 (at waterfountain ?y)<br>
				 (at monkey ?y)<br>
				 (onbox ?y))<br>
	     :effect (haswater)))<br>
```

### Input :
```
(define (problem pb1)<br>
    	(:domain monkey)<br>
  	(:objects p1 p2 p3 p4 bananas monkey box knife)<br>
  	(:init (location p1)<br>
		(location p2)<br>
		(location p3)<br>
		(location p4)<br>
	 	(at monkey p1)<br>
		(on-floor)<br>
		(at box p2)<br>
		(at bananas p3)<br>
	 	(at knife p4)<br>
	)<br>
  	(:goal (and (hasbananas)))<br>
)<br>


### Output/Plan:
![image](https://github.com/user-attachments/assets/d7d0e6db-122d-40d8-8f2d-4374e40b8cb9)
![image](https://github.com/user-attachments/assets/28a9eba2-70eb-443d-bfbb-5fd878e21770)
![image](https://github.com/user-attachments/assets/a3f254ca-d26c-4c1c-80e2-bbd15f263588)
![image](https://github.com/user-attachments/assets/8dbe3d81-284c-4134-aa69-09e2047a6a9a)
![image](https://github.com/user-attachments/assets/ba536dff-5a75-4078-878d-5d11b224b519)




### Result:
Thus the plan was found for the initial and goal state of given problem.
