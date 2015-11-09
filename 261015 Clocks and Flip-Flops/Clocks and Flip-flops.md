# Clocks and Flip-flops

## Synchronous vs Asynchronous

In an asynchronous system, signals propagate as soon as something changes which can cause problems due to (differences in) propagation delays and can be faster, but very hard to design reliably.

In a synchronous system, activity is ‘synchronised’ by a single ‘clock’.

A clock signal is normally a square wave between logic 1 and 0 with a constant frequency and a 50% duty cycle.

**Level Triggering**

With latches, when the latch signal is disabled the inputs and outputs are the same, and when it is enabled they are latched at their previous state: this is called level triggering. 

**Edge Triggering**

A better way of triggering is where the sequential circuits only change on the edge of the wave. This prevents the problem where the latch is disabled and you get the asynchronous problems. 

## Circuit Diagrams

There are circuit symbols for these latches so you don't have to draw the whole thing each time.

<!--Fig 10-->

## The Master-Slave D-type Flip Flop

    
