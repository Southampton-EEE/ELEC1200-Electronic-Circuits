# Circuits

## What *is* circuits?

- A branch of maths concerning the voltage and current of electronic and electrical systems.
- An Idealisation of real behaviours.
  - For example, $V = IR$ only works under certain circumstances, so the idealisation of $V = IR$ means it is useful but doesn't represent reality. The main problem is that as a component dissipates energy it heats up, increasing $R$.
- Useful for analysis and design.
  - Engineering is, after all, design. You need to understand models to design systems effectively.

## The Equations - Mathematical theory of circuits

### Ideal Components, and their relationship with $I$ and $V$.

| Component | Ideal Relationship     |
|-----------|------------------------|
| Resistor  | $V = I R$            |
| Capacitor | $I = C\frac{dV}{dt}$ |
| Inductor  | $V = L\frac{dI}{dt}$ |

There are also ideal relationships for diodes, opamps and transistors, which will be talked about later on.

### Describing how they are joined: The Kirchhoff Laws

#### The Voltage Law

The sum of the voltages in a loop always sum to zero. Often abbreviated to $KVL$.

$$\sum_i{v_i} = 0$$

#### The Current Law

The sum of all currents flowing into a point is zero. Often abbreviated to $KCL$.

$$ \sum_i{I_i} = 0 $$

And with these ideal equations and laws we can describe any circuit mathematically.

## Capacitors

As a first example, lets look at capacitors in series.

For two capacitors, $C_1$ and $C_2$ in series, what is their equivalent capacitance $C_3$, as if they were one component.

This turns out to be this relationship:

$$ \frac{1}{C_3} = \frac{1}{C_1} + \frac{1}{C_2} $$

But how is this derived?

First, find the ideal equations:

$$ I_1 = C_1\frac{dV_1}{dt} $$

$$ I_2 = C_2\frac{dV_2}{dt} $$

$$ I_3 = C_3\frac{dV_3}{dt} $$

Next, use $KCL$ to find relationships with current, in this example you might get:

$$ I_2 - I_3 = 0 \therefore I_1 = I_2 = I_3 $$

And finally use $KVL$ to find relationships with voltage, an example:

$$ V_1 + V_2 - V_2 - V_1 = V_1 + V_2 - V_3 \therefore V_3 = V_1 + V_2 $$

And from this information we can derive the formula:

$$ \frac{I}{C} = \frac{dV}{dt} $$

$$ \frac{I_3}{C_3} = \frac{I_1}{C_1} + \frac{I_2}{C_2} $$

$$ \frac{1}{C_3} = \frac{1}{C_1} + \frac{1}{C_2} $$

And this technique works though every circuit we will ever analyse.
