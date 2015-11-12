# Sinusoidal Sources

## Lecture 1

You can introduce a sinusoidal source into a circuit, with $V = V_0\sin\omega t$. The Fourier series says that you can decompose any signal into the sum of sine waves. The response to single sine waves is called AC theory. 

![An LC Circuit with a Sinusoidal Source.](Circuit-Diagram.png)

**KVL:** $V_0\sin(\omega t) - V_R - V_L = 0$  
**KCL:** One loop therefore one current $i$

A combination with the ideal relations gives

$$ \frac{di}{dt} + \frac{R}{L}i = \frac{V_0}{L}\sin(\omega t) $$

To which we can guess a solution

Guess

$$ i(t) = I_0 \sin (\omega t + \phi) $$

Differentiate

$$ \frac{di}{dt} = I_0\omega\cos(\omega t + \phi) $$

Substitute

$$ I_0\omega\cos(\omega t + \phi) + \frac{R}{L}I_0 \sin (\omega t + \phi) = \frac{V_0}{L}\sin(\omega t) $$

To verify that this is correct we need to find values of $(I_0, \phi)$ that work for $t\ge0$.

So, for $t = 0$

$$ 0 = I_0\omega\cos(\phi) + \frac{R}{L}\sin(\phi) $$

Factorising $I_0$

$$ \omega\cos(\phi) + \frac{R}{L}\sin(\phi) = 0 $$

Then, dividing though by $\cos(\phi)$

$$ \omega + \frac{R}{L}\tan(\phi) = 0 $$

So, for our guess to be correct

$$ \phi = \tan^{-1}\bigg(-\frac{\omega L}{R}\bigg) $$

Then, you can do the same for $t = \frac{\pi}{2\omega}$. You use this value because it shifts a sine function into the cosine function, and the cosine function to the negative of the sine function.

$$ I_0\omega\cos(\omega t + \phi) + \frac{R}{L}I_0 \sin (\omega t + \phi) = \frac{V_0}{L}\sin(\omega t) $$

$$ \frac{V_0}{L}\sin\big(\frac{\pi}{2}\big) = I_0\cos\big(\frac{\pi}{2} + \phi\big) + \frac{R}{L}I_0\sin\big(\frac{\pi}{2} + \phi\big) $$

$$ \frac{V_0}{L} = -I_0\sin(\phi) + \frac{R}{L}I_0\cos(\phi) $$

Now, using trigonometric identities you can find a nicer expression for substitution, using our know value for $\phi$.

![Diagram reprisenting $\tan\phi$ as a triangle.](triangle.png)

$$ \sin\phi = \frac{-\omega L}{\sqrt{R^2 + \omega^2 L ^2}} $$

$$ \cos\phi = \frac{R}{\sqrt{R^2 + \omega^2 L ^2}} $$

Then, by substitution

$$ \frac{V_0}{L} = -I_0\omega\bigg(\frac{-\omega L}{\sqrt{R^2 + \omega^2 L ^2}}\bigg) + I_0\frac{R}{L}\bigg(\frac{R}{\sqrt{R^2 + \omega^2 L ^2}}\bigg) $$

$$ \frac{V_0}{L} = \frac{I_0}{L}\frac{R^2 + \omega^2 L ^2}{\sqrt{R^2 + \omega^2 L ^2}}$$

$$ \frac{V_0}{L} = \frac{I_0}{L}\sqrt{R^2 + \omega^2 L ^2}$$

$$ I_0 = \frac{V_0}{\sqrt{R^2 + \omega^2 L ^2}} $$

If the guess is correct then our equations for $I_0$ and $\phi$ are correct. So finally we have to verify our solution by a final substitution back into $i(t)$

$$ i(t) = \frac{V_0}{\sqrt{R^2 + \omega^2L^2}}\sin\bigg(\omega t - \tan^{-1} \big(\frac{\omega L}{R}\big)\bigg) $$

Then, if we add a phase shift 

$$ i(t) = \frac{V_0}{\sqrt{R^2 + \omega^2L^2}}\sin\bigg(\omega t - \tan^{-1} \big(\frac{\omega L}{R} + \phi\big)\bigg) $$

## Lecture 2

This is not a very good method as it takes a very long time. A better solution involves complex numbers.

It is not difficult to reason that the following is also a solution.

$$ i(t) = \frac{V_0}{\sqrt{R^2 + \omega^2L^2}}\cos\bigg(\omega t - \tan^{-1} \big(\frac{\omega L}{R}\big)\bigg) $$

And also that you can add a coefficient $\alpha$ to the source for the sine wave.

$$ i(t) = \alpha\frac{V_0}{\sqrt{R^2 + \omega^2L^2}}\sin\bigg(\omega t - \tan^{-1} \big(\frac{\omega L}{R}\big)\bigg) $$

And when you add them you can get 

$$ i(t) = \alpha\frac{V_0}{\sqrt{R^2 + \omega^2L^2}}\sin\bigg(\omega t - \tan^{-1} \big(\frac{\omega L}{R}\big)\bigg) + \frac{V_0}{\sqrt{R^2 + \omega^2L^2}}\cos\bigg(\omega t - \tan^{-1} \big(\frac{\omega L}{R}\big)\bigg) $$

Which is the equation for a circuit with a source

$$ V_0\sin(\omega t) + V_0\cos(\omega t) $$

This is the case because the differential equation is linear, so if you add two solutions together you will get another solution.

Now, we make the decision to make $\alpha = j = \sqrt{-1}$.

$$ i(t) = j\frac{V_0}{\sqrt{R^2 + \omega^2L^2}}\sin\bigg(\omega t - \tan^{-1} \big(\frac{\omega L}{R}\big)\bigg) + \frac{V_0}{\sqrt{R^2 + \omega^2L^2}}\cos\bigg(\omega t - \tan^{-1} \big(\frac{\omega L}{R}\big)\bigg) $$

This is not a circuit nor a model of one, as it is impossible to generate a complex voltage. This is just a mathematical object. But, this mathematical circuit is useful because it contains two copies of physical circuits. 

If you take the real part of the voltage source of the mathematical circuit you get the voltage source of the cosine circuit. If you take the real part of the solution $i(t)$ for the mathematical circuit you get the solution $i(t)$ of the cosine circuit.

$$ v_{cosine}(t) = \Re(v_{math}(t)) $$
$$ i_{cosine}(t) = \Re(i_{math}(t)) $$


If you take the imaginary part of the voltage source of the mathematical circuit you get the voltage source of the sine circuit. If you take the imaginary part of the solution $i(t) $ of the mathematical circuit you get the solution $i(t)$ for the sine circuit.

$$ v_{sine}(t) = \Im(v_{math}(t)) $$
$$ i_{sine}(t) = \Im(i_{math}(t)) $$

Why have we done this though? It is now possible to write the voltage in the mathematical circuit as

$$ V_0\cos(\omega t) + j V_0 \sin(\omega t) = V_0e^{j\omega t} $$

Which is much easier to write, and much simpler to manipulate, due to the use of exponentials instead of trigonometric functions, which are much simpler to differentiate.

So, doing it quickly

The differential equation for the mathematical circuit

$$ \frac{di}{dt} + \frac{R}{L}i = \frac{1}{L}V_0 e^{j\omega t} $$

Then we guess a solution

$$ i(t) = I_0 e^{j(\omega t + \phi)} $$

The we substitute this guess into the equation, for which we need to find $\frac{di}{dt}$

$$ \frac{di}{dt} = I_0 j \omega e^{j(\omega t + \phi)} $$

Then we substitute

$$ I_0 j \omega e^{j(\omega t + \phi)} + \frac{R}{L} I_0 e^{j(\omega t + \phi)} = \frac{1}{L}V_0 e^{j\omega t} $$

Then divide though by $e^{j\omega t}$

$$ I_0 j \omega e^{j\phi} + \frac{R}{L} I_0 e^{j\phi} = \frac{1}{L}V_0 $$

because $e^{j(\omega t + \phi)} = e^{j\omega t}e^{j\phi}$

Then you can find

$$I_0 e^{j\phi} = \frac{V_0}{j\omega L + R} $$

Which tells you what $I_0$ and $\phi$ are. Then all that is left to do is solve this equation. Which you can find very easily. As you can see this was a very quick way of finding the solution compared to the previous method.
