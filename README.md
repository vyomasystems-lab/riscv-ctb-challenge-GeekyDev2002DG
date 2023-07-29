
# RISCV CTB VERIFICATION HACKATHON FINAL REPORT
 SUBMITTED BY   **DEVPARNO GHOSAL**

**OBJECTIVE:** This is the final report describing different bugs captured through different challenges provided as a part of this hackathon

# CHALLENGE LEVEL-1 (challenge_level1)

# challenge1_logical 
**Two bugs** were detected 
#
**1)** Bug detected at line 15855 , Below is the attached screenshot of the same.
For both statements at line no. 15855 and 15856 the statements refer to "s7" yet last parameter (*one being "z4" and other "ra"*)
is different which is logically incorrect
#
<img width="957" alt="challenge1logicalBUG1" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/73fcd66c-8e08-4e33-9702-ebc4f9c4a7fe">

#
The **SOLUTION** to the bug is the following piece of code
To make logically correct we make the last parameter of both statements at line no. 15855 and 15856 same -- "ra", rendering line 15855 and 15856 as same, hence correcting the code
#
<img width="959" alt="challenge1logicalBUG1soln" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/d3bd00da-ccde-4503-9eae-857c7ef63f0f">

#
**2)** Bug detected at line 25584 , Below is the attached screenshot of the same.
 All statements start with "and" yet statement at line no. 25584 starts with *"andi"*, which makes it logically incorrect
 #
<img width="957" alt="challenge1logicalBUG2" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/2dd1579c-a86c-4ff4-8598-7b64fe736d2d">

#
The **SOLUTION** to the bug is the following piece of code
 To make it logically correct, we replace *"andi"* with *"and"* , as it should be, making the code correct
 #
<img width="959" alt="challenge1logicalBUG2soln" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/4ac96f13-c0df-42c5-996c-7446e741b746">

#
# challenge2_loop
**Three bugs** were detected 
Bugs detected at line 11 , 22 and 23 , Below is the attached screenshot of the same.
 1) (BUG at line 11)-  As it is said we are to test 3 cases , and in code *"li TESTNUM 2"*  makes the line incorrect
 2) (BUG at line 22)- As at line 14 we initialise "t5" and while comparing our added out result we are comparing it with "t4" which makes it incorrect
 3) (BUG at line 23)- "j fail" makes the process fail while it tries to reach *"test_end:"*, causing a loop which prevents generation of spike dump file
    #
<img width="957" alt="challenge1loopBUGln11_22_23bug" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/3fe8f4b6-2879-44f1-9707-6e4964d9afde">

#
The **SOLUTION** to the bugs is the following piece of code
1) (Soln to BUG at line 11)-  As it is said we are to test 3 cases , we make the line code *"li TESTNUM 3"*  making the line correct
2) (Soln to BUG at line 22)- As at line 14 we initialise "t5" and while comparing our added out result we are comparing it with "t5" which makes correct
3) (Soln to BUG at line 23)- We just remove "j fail" making the process reach *"test_end:"*,making it correct and causing generation of spike dump file
   #
<img width="957" alt="challenge1loopBUGln11_22_23soln" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/b779f38d-b1d6-4fe5-8c78-7d79b39ad0ca">

#
# challenge3_illegal
**Three bugs** were detected 
Bugs detected at line 6, 16 and 26 , Below is the attached screenshot of the same.
1) (BUG at line 6)-  As it is said we are work with rv32i , and in code *"RVTEST_RV64M"*  makes the line incorrect
2) (BUG at line 16)- As "TEST_PASSFAIL" presence in that line interrupts the process and it never reaches further lines , it causes loop preventing generation of spike dump file
3) (BUG at line 26)- "mret" makes the process return, causing a loop which prevents generation of spike dump file
   #
<img width="957" alt="challenge1illegalBUG61626" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/d21e87b0-b8b3-4b64-b5be-9fa0f230b512">

#
The **SOLUTION** to the bugs is the following piece of code
1) (BUG at line 6)-  As it is said we are work with rv32i , we write *"RVTEST_RV32M"* in code making the line correct
2) (BUG at line 16)- We simple remove "TEST_PASSFAIL" as its absence in that line makes sure all required lines execute sequentially
3) (BUG at line 26)-  We add "TEST_PASSFAIL" at line 25 and remove "mret" from line 26 making the process go as expected, causing generation of spike dump file
   #
<img width="958" alt="challenge1illegalBUG61626soln1" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/85a35b74-75aa-42f0-939b-a2218a6efff0">

<img width="958" alt="challenge1illegalBUG61626soln" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/8f5a38c5-b073-4541-a791-6febb3bb5ab6">

#

# CHALLENGE LEVEL-2 (challenge_level2)

# challenge1_instructions
**Bug** detected , Below is the attached screenshots of the same
#
<img width="956" alt="challenge2instructionsBUG1" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/5f01a33d-2f67-47e9-a527-9baca2c3f114">

<img width="955" alt="challenge2instructionsBUG2" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/832d3238-1bba-43f0-a603-4246d9ba96dd">

#
# challenge2_exceptions
Exception generated , Below is the attached screenshot of the same
Editing "ecause" statements makes it work correctly
#
<img width="959" alt="challenge2exceptions" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/2807ad0c-f87c-4fb1-bc0c-cea28ae6c422">


**END**
# THANK YOU :)



