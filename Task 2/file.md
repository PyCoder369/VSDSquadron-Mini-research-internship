# Task 2: Spike Simulation

Run the sum1ton.o in the Spike simulator in order to debug the code.
Check the output from risc compiler by typing: spike pk <filename>.c

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/87aa57a84a542b5dc136475e120246636a0d6700/t21.png)

Now open new tab in terminal to open risc assembly code

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/9220a7c47dbc32f998a0c129d112456e4b63cef6/t22.png)

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/57dddf37fda502a549cad012ae32cc53a892b5ee/t23.png)

Now in first tab open spike debugger by typing: spike -d pk <filename>.o

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/59db123f5a982165cdabe2cb0e83694b1717f425/t24.png)

Now type:
- until pc 0 100b0     (Run program counter from 0 to 100b0)

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/335c8cbdb4dd9792ea3422d4b77900d1d6b31e73/t25.png)

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/335c8cbdb4dd9792ea3422d4b77900d1d6b31e73/a.png)

Now to know what a0 contains type:
- reg 0 a0

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/e3a6e6ac8898925b992e55f387749c86c5028f44/t26.png)

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/af04b11af9b9214894390c9ad844fab5e6d394c5/b.png)

Now check sp value before and after getting updated

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/08a8dc187ed7a0d472905a062ed016b3f366b56c/t27.png)

