# challenge2_loop
**Three bugs** were detected 
Bugs detected at line 11 , 22 and 23 , Below is the attached screenshot of the same.
#
 1) (BUG at line 11)-  As it is said we are to test 3 cases , and in code *"li TESTNUM 2"*  makes the line incorrect
 2) (BUG at line 22)- As at line 14 we initialise "t5" and while comparing our added out result we are comparing it with "t4" which makes it incorrect
 3) (BUG at line 23)- "j fail" makes the process fail while it tries to reach *"test_end:"*, causing a loop which prevents generation of spike dump file
    #
<img width="957" alt="challenge1loopBUGln11_22_23bug" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/3fe8f4b6-2879-44f1-9707-6e4964d9afde">

#
The **SOLUTION** to the bugs is the following piece of code
#
1) (Soln to BUG at line 11)-  As it is said we are to test 3 cases , we make the line code *"li TESTNUM 3"*  making the line correct
2) (Soln to BUG at line 22)- As at line 14 we initialise "t5" and while comparing our added out result we are comparing it with "t5" which makes correct
3) (Soln to BUG at line 23)- We just remove "j fail" making the process reach *"test_end:"*,making it correct and causing generation of spike dump file
   #
<img width="957" alt="challenge1loopBUGln11_22_23soln" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/b779f38d-b1d6-4fe5-8c78-7d79b39ad0ca">
