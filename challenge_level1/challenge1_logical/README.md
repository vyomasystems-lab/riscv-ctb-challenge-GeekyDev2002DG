# challenge1_logical 
**Two bugs** were detected 
#
**1)** Bug detected at line 15855 , Below is the attached screenshot of the same.
#
For both statements at line no. 15855 and 15856 the statements refer to "s7" yet last parameter (*one being "z4" and other "ra"*)
is different which is logically incorrect
#
<img width="957" alt="challenge1logicalBUG1" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/73fcd66c-8e08-4e33-9702-ebc4f9c4a7fe">

#
The **SOLUTION** to the bug is the following piece of code.
#
To make logically correct we make the last parameter of both statements at line no. 15855 and 15856 same -- "ra", rendering line 15855 and 15856 as same, hence correcting the code
#
<img width="959" alt="challenge1logicalBUG1soln" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/d3bd00da-ccde-4503-9eae-857c7ef63f0f">

#
**2)** Bug detected at line 25584 , Below is the attached screenshot of the same.
#
 All statements start with "and" yet statement at line no. 25584 starts with *"andi"*, which makes it logically incorrect
  #
<img width="957" alt="challenge1logicalBUG2" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/2dd1579c-a86c-4ff4-8598-7b64fe736d2d">

#
The **SOLUTION** to the bug is the following piece of code
#
 To make it logically correct, we replace *"andi"* with *"and"* , as it should be, making the code correct
 #
<img width="959" alt="challenge1logicalBUG2soln" src="https://github.com/vyomasystems-lab/riscv-ctb-challenge-GeekyDev2002DG/assets/72439194/4ac96f13-c0df-42c5-996c-7446e741b746">
