# challenge3_illegal
**Three bugs** were detected 
Bugs detected at line 6, 16 and 26 , Below is the attached screenshot of the same.
#
1) (BUG at line 6)-  As it is said we are work with rv32i , and in code *"RVTEST_RV64M"*  makes the line incorrect
2) (BUG at line 16)- As "TEST_PASSFAIL" presence in that line interrupts the process and it never reaches further lines , it causes loop preventing generation of spike dump file
3) (BUG at line 26)- "mret" makes the process return, causing a loop which prevents generation of spike dump file
   #
<img width="957" alt="challenge1illegalBUG61626" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/d21e87b0-b8b3-4b64-b5be-9fa0f230b512">

#
The **SOLUTION** to the bugs is the following piece of code
#
1) (BUG at line 6)-  As it is said we are work with rv32i , we write *"RVTEST_RV32M"* in code making the line correct
2) (BUG at line 16)- We simple remove "TEST_PASSFAIL" as its absence in that line makes sure all required lines execute sequentially
3) (BUG at line 26)-  We add "TEST_PASSFAIL" at line 25 and remove "mret" from line 26 making the process go as expected, causing generation of spike dump file
   #
<img width="958" alt="challenge1illegalBUG61626soln1" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/85a35b74-75aa-42f0-939b-a2218a6efff0">

<img width="958" alt="challenge1illegalBUG61626soln" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/8f5a38c5-b073-4541-a791-6febb3bb5ab6">

