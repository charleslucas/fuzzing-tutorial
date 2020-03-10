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
  Log in as root (don't use sudo), and then run the command exactly as given.

  AFL needs a file with *something* in it inside the -i input directory.  Just create one file with a word in it.


Compile:  afl-g++ exploitable2.cpp -g -o exploitable2
Execute:  afl-fuzz -i afl_in -o afl_out ./exploitable2