# Objective-C KVO Crash: Unremoved Observer

This repository demonstrates a common error in Objective-C related to Key-Value Observing (KVO).  Failure to remove observers before the observed object is deallocated can result in crashes due to accessing freed memory.

The `bug.m` file contains the flawed code that omits the crucial step of removing the observer. The `bugSolution.m` file provides the corrected version with the observer properly removed.

## Steps to Reproduce

1. Compile and run `bug.m`.
2. Observe the crash (EXC_BAD_ACCESS). 
3. Compile and run `bugSolution.m`. 
4. Observe the successful execution without a crash. 

## Solution

Always ensure that you remove observers using `removeObserver:` when they're no longer needed.  This is essential to prevent crashes and ensure the stability of your application.