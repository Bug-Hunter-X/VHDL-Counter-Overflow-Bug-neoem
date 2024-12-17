# VHDL Counter Overflow Bug
This repository demonstrates a common bug in VHDL code: an integer overflow in a counter. The `buggy_counter.vhdl` file contains the buggy code, while `fixed_counter.vhdl` provides a corrected version.  The bug arises from the way the counter handles the maximum value.  The solution uses a more robust approach to prevent unexpected behavior.

## Bug Description
The original counter design increments a signal correctly until it reaches its maximum value (15). However, instead of halting, it wraps around to 0, and may continue to increment, depending on the simulation setup.  This behavior can be problematic in real-world applications leading to unintended results or even system crashes if the counter is used as an index into an array or other data structures.

## Solution
The solution provided in `fixed_counter.vhdl` addresses this bug by explicitly checking if the counter is at its maximum value. If it is, the counter stops incrementing and remains at 15 instead of resetting to 0, thus avoiding the overflow condition.  This ensures the counter behaves correctly and prevents undefined behavior. 
