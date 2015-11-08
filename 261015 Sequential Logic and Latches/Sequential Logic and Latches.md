# Sequential Logic and Latches

A sequential system is defined by the concept that it moves though a sequence of states.
The system requires a way to remember it's current state - it needs a form of memory.

## 1-bit Memory

A simple 1-bit memory example would be a buffer's output connected to it's input. This works because there is a delay between it getting it's input and giving and output. 

<!--Fig 1-->

This circuit would be the same as two inverters connected in place of the buffer, bar possibly the delay. 

<!--Fig 2-->

Which is equivalent to

<!--Fig 3-->

The `SET` state is when $Q = 1$ and $\bar{Q} = 0$ and the `RESET` state is when $Q = 0$ and $\bar{Q} = 1$. Because there are two stable states it is called a "bi-stable".

The problem with this is that there are **no inputs**.

So we need a way to change the state, for this we use a $\bar{R}\bar{S}$ Latch.

<!--Fig 4-->

These inputs are active low. This means that to activate the input you have to make the input low (`0`). 

| $\bar{S}$ | $\bar{R}$ | $Q_n$ | $\bar{Q}_n$ | State     |
|-----------|-----------|-------|-------------|-----------|
| 0         | 0         | 1     | 1           | Invalid   |
| 0         | 1         | 1     | 0           | Set       |
| 1         | 0         | 0     | 1           | Reset     |
| 1         | 1         | $Q$   | $\bar{Q}$   | Latch     |
  
As you can see from the table this does not behave as a combinational logic system. The output is dependant on it's current state. This is called a **characteristic table**.

The problem with the RS Latch is that when in it's invalid state it's output becomes unpredictable.

You can use an RS Latch to debounce an input.

<!--Fig 5-->

<!--Fig 6-->

A way to prevent this bounce is to add an RS Latch to the outputs:

<!--Fig 7-->

So now at time $\tau$ the latch gets put either into the set or reset position, but it means that when the input bounces and both inputs are `1` it goes into the latch state, and therefore the input doesn't change, and therefore the input is debounced. 

This is an example of a good use of and RS Latch because it is impossible to go into the invalid state, therefore the latch will perform normally.

It is also possible to build on the RS Latch to prevent this undesirable behaviour.

## D-type Latch

First we can place an inverter between the S and R of an RS Latch to make $  = \bar{R}$.

<!--Fig 8-->

Which gives the following characteristic table:

| $D$ | $Q_n$ | $\bar{Q}_n$ |
|-------|---------|---------------|
| 0     | 1       | 0             |
| 1     | 0       | 1             |

But this removes that latch functionality. To regain this we can add two NAND gates.

<!--Fig 9-->

Which gives us a D-type Latch. 

| $D$ | $\bar{LATCH}$ | $Q_n$ | $\bar{Q}_n$ |
|-------|-----------------|---------|---------------|
| 0     | 1       | 0             | 1 |
| 1     | 1       | 1             | 0 |
| X | 0 | $Q$ | $\bar{Q}$ |
