# fuzzing-tutorial

// Copyright 2020
// Charles Lucas
// ZeroSquared.io

Basic fuzzing tutorial showing how you can use AFL to find potential vulnerabilities in poorly constructed C++ programs.


My environment setup:
- Create Ubuntu VM under Oracle VM Virtualbox
- Install Guest Additions
- Log in, install gcc, afl-fuzz
- Install "code" editor with C++

Notes:
  First time I ran, AFL gave me an unclear message about /proc/sys/kernel/core_pattern.
  To take care of it su as root (don't use sudo), and then run the command exactly as given.

The initial testcase for exploitable2 consists of a textfile with a few names in it:  testcases/users.txt

Compile:  afl-g++ exploitable2.cpp -g -o exploitable2
Execute:  afl-fuzz -i testcases -o afl_out ./exploitable2 @@