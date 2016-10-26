# GDB OLD

## This is how I like to compile with g++.

    $g++ -W -Wall -pedantic -o programName -p sourceFile.cpp
    
    -W: Print extra warning messages for some problems.
    -Wall: Enable all the warnings about questionable code
    -pedantic: Show all the warnings demanded by strict ISO compliance
    -o programName: place the executable output in programName sourceFile.cpp: the 
    name of our source code file

## 1

    ulimit -c 1024
    
    hexedit core
    
    bt
    
    frame 6
    
    l
    
## 2
 
    b 6
    
    run 
    
    p m

## 3

    gcc -g double_free.c -o double_free_gdb
    gcc -g double_free.c -o double_free_lite
    
    -g informacje debugowe
    
    strip -g double_free_gdb_lite
    
    rm core
    
    ./double_free_lite
    
    gdb double_free_gdb core
    
    bt
    