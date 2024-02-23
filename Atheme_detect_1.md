Affected Version:
Atheme 7.2.12 7e3a2fead55e1976a7bec324e6acd92d3b9256fb

Vulnerability Description:
The vulnerability is a memory leak bug located at line 203 of the file /atheme/src/crypto-benchmark/main.c. This vulnerability could potentially be exploited maliciously to cause resource exhaustion and denial of service attacks.

Atheme download address:
https://github.com/atheme/atheme.git

Defect details:

1.In the file main.c located at line 179 in /atheme/src/crypto-benchmark, a pointer named opt is defined. The program allocates a dynamic memory area for this pointer using the strdup function at line 182, and checks whether the dynamic memory area is allocated successfully. When the dynamic memory area is successfully allocated, the program enters the loop at line 187. If the if statement at line 200 evaluates to true, the program returns at line 203 without executing the free statement at line 209, resulting in a memory leak defect in the pointer opt, as shown in the following figure:

![image](https://github.com/LuMingYinDetect/Atheme_defects/blob/main/Atheme_1.png)
