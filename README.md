# AssemblyX86-crashcourse-
A Quick intro to assembly X86 , with important notes and resources
ASM
--------------------------------------
assembly we can consider its a mid level language between human and machine languages , if you reverse engineer or a malware analyst you should learn assembly to able to read and understand the code .

"note each cpu archticture has its own assembly instruction here is the basics of Intel 32 arch assembly 86"

in this article just a quick intro to it and some important notes .

# the flow of assembly language to excute is : 
sourcecode ➡ assembler make objectcode("machine language") ➡ linker make it exe ➡ os loader get it in output when we run it

## registers
registers is small unit in cpu , they are used to store data and instructions that the CPU needs to access quickly

general purpose:
4bytes | 2bytes
eax    | ax                 //store value
ecx    | cx                 //counte "looping"
edx    | dx                 //i/o pointer
ebx    | bx                 

esp    | sp                 //STACK pointer 
ebp    | bp                 //STACK base pointer for local variables

esi    | si                 //SOURCE
edi    | di                 //DESTINATION

flags:
EIP                         //NEXT INSTRUCTION POINTER     

## Stack 
stack memory is a type of memory that stores data in a Last In First Out (LIFO) format. It is a special type of memory that is used to store local variables and function parameters when a program is running. It is also used to store return addresses when functions are called. Stack memory is allocated and released very efficiently, making it the most efficient type of memory for storing temporary data.

stack (LIFO)last in first out
stack used 2 options 
push its put data
pop  get data out
![image-1](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20221219100314/stack.drawio2.png)
stack grow down

## asm instructions
----------------
there is two syntax to write asm86 instruction (opcode) we will foucus on the intel syntax
### instruction destination, source
it takes the source from the right side put in the left side , like = operaton in high lvl programming language
also its not always can be like this it can be instructionOnly  and instruction destination

### instructionOnly
like nop "no operation"

### instruction dedestination   
like inc,dec,push,pop,etc...      

### destination could be
1-register eax ,edx,...
2-place in memory DWORD [1254554566]...

#### memory in assembly has diffrent sizes from :
byte "8 bit"
word "16 bit"
dword "32 bit"
qword "64 bit"
and more  "
3-Acess STACK

### source could be
same like dest
or immediate value "just a number or value"

#### note some times [] means get the get the value of the address
----------------------------------------------------------------
### we can divid asm in 3 cataegories

data manipulation

ADD,SUB,MUL,DIV,NEG,INC,DEC

OR,XOR,AND,NOT

SHL,SHR,ROL,ROR

data transfer

MOV,MOVZX,MOVSX "mov data form src to dst"

XCHG "Replace data"

PUSH,POP,PUSHAD,POPAD 

MOVSB,LODSB,STOSB

program control is two cases :

1-unconditional 
JMP, ""
CALL,RET "call and return function"

2-conditional
JNZ,JZ,JCC...,LOOP "like if , if else , else , and loop"

repeat
REP
----------------------------------------------------------------
Resources to learn assembly x86

[watch it first](https://www.youtube.com/watch?v=75gBFiFtAb8)

[Arabic dr ahmed sallam](https://www.youtube.com/playlist?list=PLMm8EjqH1EFVodghdDWaAuHkHqj-nJ0bN)
[Arabic shell code with assembly](https://www.youtube.com/playlist?list=PLiF9Gb9oy4n4v8cidEJ1izE2L9wrgnkKU)

English articles one of best resources
[1](https://revers.engineering/applied-re-basic-architecture/)
[2](https://revers.engineering/applied-re-the-stack/)
[3](https://revers.engineering/applied-re-exceptions/)
[4](https://revers.engineering/applied-re-accelerated-assembly-p1/)
[5](https://revers.engineering/applied-re-accelerated-assembly-p2/)
----------------------------------------------------------------
