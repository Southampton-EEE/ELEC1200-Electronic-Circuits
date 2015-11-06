# RC Circuits

$$  \frac{dv}{dt} + \frac{1}{RC}v = 0 $$

$$ v(0) = v_0 e^{-\frac{1}{RC}} \to v_0 = v(o)$$

Therefore we can model the system using the differential equations and the initial conditions.

### Finding a Solution via Substitution

First we can guess the solution, because the decay looks exponetial we can guess

$$ v(t) = Ae^{\lambda t} $$

Therefore

$$ \frac{dv}{dt} = \lambda A e^{\lambda t} $$

So

$$ \frac{dv}{dt} + \frac{1}{RC}v = \lambda A e^{\lambda t} + \frac{1}{RC}v = Ae^{\lambda t}(\lambda + \frac{1}{RC}) $$

Therefore, if this is correct it must equal 0.

$$ Ae^{\lambda t}(\lambda + \frac{1}{RC}) = 0 $$

Which means that either $A = 0$ or $(\lambda + \frac{1}{RC}) = 0$ which itself implies that $\lambda = \frac{-1}{RC}$. 

For $A$ to be zero, the initial value of $v$ must be zero, which is not a global solution, as $v_0$ is not always zero.

Therefore, we can replace $\lambda$ with $\frac{-1}{RC}$:

$$ v(t) = Ae^{\frac{-1}{RC}t} $$

Where $A$ is the initial value of the voltage, $v_0$.

$$ v(t) = v_0e^{\frac{-1}{RC}t} $$

# RL Circuits

A resistor and an inductor connected in a loop. 

$$ \frac{di}{dt} + \frac{R}{L}i = 0 $$

Both RC and RL circuits have the same form, so we can use the solution found for RC circuits, replacing constants:

$$ i(t) = i_0e^{-\frac{R}{L}t} $$

# LC Circuits

A capacitor and an inductor connected in a loop.

KCL:

$$ i_C - i_L = 0 $$
$$ i_C = i_L = i$$

KVL:

$$ v_C + v_L = 0 $$
$$ v_C = -v_L $$

Ideal:

$$ i_C = C\frac{dv_i}{dt} $$
$$ v_L = L\frac{di_L}{dt} $$

**Forming A Differential Equation:**

$$ v_C = -L\frac{di}{dt} $$
$$ v_c = -L\frac{d}{dt}(i_c) $$
$$ v_C = -L\frac{d}{dt}(C{\frac{dv_C}{dt}}) $$
$$ v_C = -LC\frac{d^2v_c}{dt^2} $$
$$ \frac{d^2v_C}{dt^2} + \frac{1}{LC}v_C = 0 $$

Which looks like SHM ($\frac{d^2x}{dt^2} + \omega^2x = 0$) because this is a oscillating system.

This also works for current:

$$ \frac{d^2I}{dt^2} + \frac{1}{LC}I = 0 $$

**Finding a solution** by substitution

Guess: 

$$ V(t) = A\sin(\omega t) $$

Substitute:

$$ \frac{d^2v}{dt^2} + \omega^2v = 0 \ \ \textrm{and} \ \ \omega = \sqrt{\frac{1}{LC}} $$

$$ v = A\sin(\omega t) $$

$$ \frac{dv}{dt} = A\omega\cos(\omega t) $$

$$ \frac{dv^2}{dt^2} = -A\omega^2\sin(\omega t) $$

$$ -A\omega^2\sin(\omega t) + \omega^2A\sin(\omega t) = 0 $$

Which is true, therefore this is a correct solution.

$$ V = A\sin\bigg(\sqrt{\frac{1}{LC}}I\bigg) $$

If the solution is this, then that means that $V(0) = 0$ because $V(0) = A\sin(0)$. But this is not he only solution as $V$ can be anything at $t = 0$. To combat this we add a variable $\phi$, the phase shift.

$$ V = A\sin\bigg(\sqrt{\frac{1}{LC}}I + \phi\bigg) $$

This can be proved by adding $v$ in terms of $\cos()$ and $\sin()$, then using double angle.

From this, we can see that adding two solutions you can get another solution.

$$ f(x) = \sum_if_i(x) $$

Also note that the order of the differential equation is also the number of degrees of freedom, for example in the second order equation for an RL circuit you have two degrees of freedom $V_{max}$ and $\phi$.

**But why can you add them?**

Say you have two solutions to $V$, $V_1$ and $V_2$. This means that:

$$ \textrm{if} \ \ f(V) = a \ \ \textrm{then} \ \ f(V_i) = a $$


