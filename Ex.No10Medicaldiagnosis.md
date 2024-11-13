# Ex.No: 8  Logic Programming –  Medical Diagnosis Expert System
### DATE:   19-9-2024                                                                        
### REGISTER NUMBER : 212222060012
### AIM: 
Write a Prolog program to build a medical Diagnosis Expert System.
###  Algorithm:
1. Start the program.
2. Write the rules for each diseases.
3. If patient have mumps then symptoms are fever and swollen glands.
4. If patient have cough, sneeze and running nose then disease is measles.
5. if patient have symptoms headache ,sneezing ,sore_throat, runny_nose and  chills then disease is common cold.
6. Define rules for all disease.
7. Call the predicates and Collect the symptoms of Patient and give the hypothesis of disease.
        

### Program:

hypothesis(Patient,german_measles) :-<br>
	symptom(Patient,fever),<br>
	symptom(Patient,headache),<br>
	symptom(Patient,runny_nose),<br>
	symptom(Patient,rash).<br>
hypothesis(Patient,flu) :-<br>
        symptom(Patient,fever),<br>
       symptom(Patient,headache),<br>
	symptom(Patient,body_ache),<br>
	symptom(Patient,conjunctivitis),<br>
	symptom(Patient,chills),<br>
	symptom(Patient,sore_throat),<br>
	symptom(Patient,runny_nose),<br>
	symptom(Patient,cough).<br>
hypothesis(Patient,common_cold) :-<br>
	symptom(Patient,headache),<br>
	symptom(Patient,sneezing),<br>
	symptom(Patient,sore_throat).<br>
hypothesis(Patient,chicken_pox) :-<br>
	symptom(Patient,fever),<br>
	symptom(Patient,chills),<br>
	symptom(Patient,body_ache),<br>
	symptom(Patient,rash).<br>
hypothesis(Patient,measles) :-<br>
	symptom(Patient,cough),<br>
	symptom(Patient,sneezing),<br>
	symptom(Patient,runny_nose).<br>
symptom(raju,headache).<br>
symptom(raju,sneezing).<br>
symptom(raju,sore_throat).<br>
### Output:

![316235602-51224685-6269-4428-b8f8-cf4dcb8446bd](https://github.com/user-attachments/assets/a7add01d-5dc9-411b-b2f8-f4e548e5dd4b)


### Result:
Thus the simple medical diagnosis system was built sucessfully.
