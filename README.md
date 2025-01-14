# VHDL Counter with Metastability Risk

This repository demonstrates a potential metastability issue in a simple VHDL counter.  The `buggy_counter.vhd` file contains code for a counter that might exhibit unpredictable behavior due to a lack of explicit wait statements in its process.

The `fixed_counter.vhd` provides a corrected version. The key change is the addition of a wait statement to address the issue and ensure proper synchronization.

## Bug Description

The original VHDL code lacks a wait statement in the process that updates the counter.  This can result in metastability if the clock signal changes during the critical timing window for the state update.  This means that the counter may not accurately reflect its intended value, and its behavior will become unreliable and unpredictable, especially at higher clock frequencies.

## Solution

The solution demonstrates a proper VHDL coding practice. It explicitly waits for the next clock edge to update the counter's state. This eliminates the timing window which allows the risk of metastability to occur.