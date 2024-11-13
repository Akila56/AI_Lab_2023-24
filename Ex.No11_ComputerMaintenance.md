# Ex.No: 9  Logic Programming –  Computer Maintenance Expert System
### DATE: 19-09-2024                                                                           
### REGISTER NUMBER : 212222060012
### AIM: 
Write a Prolog program to build a computer maintenance expert system.
###  Algorithm:
1. Start the program.
2. Write the rules for each fault in computer.
3. If system have printing problem, missing dots and no uniform printing then system fault on printer head.
4. If system have not printing, missing dots and spread inks then system fault on ribbon
5. If system have not printing, paper jam and out of paper then system fault on paper stuck in printer
6. Similarly define rules for all faults.
7. Define facts for system problems.
8. Find the fault of computer by passing query to system.
     
### Program:

fault(printer_head) :-<br>
	problem(not_printing),<br>
	problem(missing_dots),<br>
	problem(nonuniform_printing).<br>
fault(ribbon) :-<br>
	problem(not_printing),<br>
	problem(missing_dots),<br>
	problem(spread_ink).<br>
fault(paper) :-<br>
	problem(not_printing),<br>
	problem(paper_jam),<br>
	problem(out_of_paper).<br>
fault(motherboard) :-<br>
	problem(long_beep),<br>
	problem(short_beep).<br>
fault(hard_disc) :-<br>
	problem(two_short_beeps),<br>
	problem(blank_display).<br>
problem(not_printing).<br>
problem(missing_dots).<br>
problem(spread_ink).<br>
problem(two_short_beeps).<br>
problem(blank_display).<br>


### Output:
![image](https://github.com/user-attachments/assets/98280dae-ff84-481c-89a5-d238710a09b0)



### Result:
Thus the simple computer maintenance expert system was built sucessfully.
