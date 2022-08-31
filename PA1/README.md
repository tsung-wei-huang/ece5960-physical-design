# F-M Circuit Partitioning

Due: 9/21/2022 23:59 PM

## Problem Description

Let $C = c_1, c_2, c_3, ..., c_n$ be a set of $n$ cells and $N = n_1, n_2, n_3, ..., n_m$ be a set of $m$ nets. Each net $n_i$ connects a subset of the cells in $C$. Your job in this programming assignment is to implement the 2-way [Fiduccia-Mattheyses algorithm](https://en.wikipedia.org/wiki/Fiduccia%E2%80%93Mattheyses_algorithm) that partitions the set $C$ of $n$ cells into two disjoing, balanced groups, $G_1$ and $G_2$, such that the overall cut size is minimized. No cell replication is allowed. The cust size $s$ is given by the number of nets among $G_1$ and $G_2$. For a given balance factor $r$, where $0 < r < 1$, the objective is to minimize the cut size $s$ while satisfying the following constraint:

$$
n\times(1-r)/2 \leq |G_1|, |G_2| \leq n\times(1+r)/2 
$$

## Input

Each input file starts with a balance factor $r$, followed by the description of $m$ nets. Each net description contains the keyword `NET`, followed by the net name and a list of the connected cells, and finally the symbol `;` denoting the end of the net description. 

| Input Format | Example |
| ------------ | ------- |
| $r$ <br> NET NET_NAME [CELL_NAME]+; | 0.5 <br> NET n1 c2 c3 c4 ; <br> NET n2 c3 c6 ; <br> NET n3 c3 c5 c6 ; <br> NET n4 c1 c3 c5 c6 ; <br> NET n5 c2 c4 ; <br> NET n6 c4 c6 ; <br> NET n7 c5 c6 ;|

In the example circuit, we have a balance factor of `0.5` and three nets `n1`, `n2`, and `n3`, where net `n1` has three cells `c1`, `c2`, `c3`, and `c4`, net `n2` has two cells `c3` and `c6`, net `n3` has three cells `c3`, `c5`, and `c6`, and so on.

## Output

In the program output, you are asked to give the cut size, the sizes of $G_1$ and $G_2$, and the contents of $G_1$ and $G_2$ (i.e., cells). The following table gives the output format and a sample output:

| Input Format | Example |
| ------------ | ------- |
| Cutsize = $s$<br> G1 size <br> [cells]+ <br> G2 size <br> [cells]+ | Cutsize = 5 <br> G1 3 <br> c1 c2 c3 ; <br> G2 3 <br> c4 c5 c6;|

Note that the example solution may not be the optimal one.

## Language

You can implement this assignment using any language you like. However, we recommend `C` or `C++` for performance reason.

## Platform

You need to evaluate your program on the Linux server at `twhuang-server-01.ece.utah.edu`.

Please email Dr. Huang (tsung-wei.huang at utah.edu) for creating an account to log in.


## Program Command 

Your program should support the following command-line parameters:


```bash
[executable file name] [input file name] [output file name]
```

For example:

```bash
~$ ./fm input_pa1/input_0.dat output_0.dat
```

## Checker 

We have also provide a checker program for you to verify your program:

```bash
~$ ./checker/checker_linux [input_file] [output_file]
```

A successful verification will give you the following message:

```bash
[Check] Cut size = 143285 matched!
[Check] Balance passed:: 189332(min) < 193156(G1), 189333(G2) < 193157(max) 
=================================
Congratulations! Legal Solution!!
=================================
```

Note the above output is just an example.


## Submission

You need to submit a report by responding directly to [Programming Assignment #1 Submission Page](https://github.com/tsung-wei-huang/ece5960-physical-design/issues/1). The report should contain the following section:

+ A section describing means to compile and run your code 
+ A section listing partition results in terms of cut size and runtime for each *PASSED* benchmark 
+ A section outlining the challenges you encountered and solved during the implementation

You *DO NOT* need to submit any source code but place it under the folder `/home/your_account/PA1` in the server `twhuang-server-01.ece.utah.edu`, where `your_account` is your log-in account. The instructor will go to your folder to grade your code based on the instruction in your report. If you wish to place your code somewhere else, please document it in your report.

To help you stay on schedule, we will have two checkpoints. At each checkpoint, you will need to update your current results in a Markdown Table by responding to [Programming Assignment #1 Checkpoint Report](https://github.com/tsung-wei-huang/ece5960-physical-design/issues/2).


## Grading Policy

This programming assignment will be graded based on the following metrics:

+ Correctness reported by the checker program
+ Solution quality of your partitioned results
+ Runtime performance of your program

## Academic Integrity

Please refer to the [University Academic Policies](https://regulations.utah.edu/academics/) for details about academic integrity.

## Questions

If you have any questions, please create an [issue page](https://github.com/tsung-wei-huang/ece5960-physical-design/issues). We highly encourage you discuss questions with others in the issue page.
