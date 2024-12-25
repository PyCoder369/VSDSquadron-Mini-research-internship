Task 1: A C program which calculates the sum of all numbers upto 'n' and compare outputs of risv64 gcc O1 and riscv64 gcc Ofast

Open Terminal and type leafpad <filename>.c                        Note: If leafpad not available install it by typing sudo apt install leafpad

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/8c76f6f986f9866db7c4f5782494a3380d0c4bef/1.png)

Type the c program code for sum of n numbers and save
![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/770fd2ee4dbbd44d92e469d0c0ec3b1167c332ed/2.png)



compile by typing gcc <filename>.c
![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/1cddbd747263e652568b70fce9b8e7f19613ef5e/3.png)


check output by typing ./a.out

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/1cddbd747263e652568b70fce9b8e7f19613ef5e/4.png)

first check for riscv64 gcc O1

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/1cddbd747263e652568b70fce9b8e7f19613ef5e/5.png)

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/1cddbd747263e652568b70fce9b8e7f19613ef5e/6.png).

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/1cddbd747263e652568b70fce9b8e7f19613ef5e/7.png).

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/1cddbd747263e652568b70fce9b8e7f19613ef5e/8.png).

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/1cddbd747263e652568b70fce9b8e7f19613ef5e/9.png).


Calculate no of instructions
![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/3808825cbbbd8876680d418a00c7ed21ea6d829a/10.png).
![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/d37c217a416066d2b64f82072d8bb08831ca43da/11.png).

Divide by 4 beacuse each instruction is incremented by 4
![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/496463c8037ec478d5d03bf5b26d0724b4d64c84/12.png).

we get 15 so 15 instructions


similarly repeat steps for riscv64 gcc Ofast we will be seeing lesser instructions compared to riscv64 gcc O1
![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/1cddbd747263e652568b70fce9b8e7f19613ef5e/13.png).

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/61e5e76745ad4137074e6fe75679758f63c0796c/14.png).

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/61e5e76745ad4137074e6fe75679758f63c0796c/15.png).

![image alt](https://github.com/PyCoder369/VSDSquadron-Mini-research-internship/blob/61e5e76745ad4137074e6fe75679758f63c0796c/16.png).

Here we get 12 instructions which is less compared to O1.

