# RL with a Source

Having found the current characteristics of the circuit it is easy to use that information to find $V_L$.

$$ i(t) = \frac{E}{R}(1 - e^{-\frac{R}{L}t}), t > 0 $$

And we know from the ideal relations that

$$ V_L = L \frac{di}{dt}  = L\frac{di(t)}{dt}$$

Which we can then use to find that

$$ L\frac{d}{dt}\frac{E}{R}(1 - e^{-\frac{R}{L}t}), t > 0 $$

Which simplifies after differentiating to 

$$ V_L = Ee^{-\frac{R}{L}t} $$

Then, by KVL you can find $V_R$ by either

$$ V_R= Eu(t) - V_L $$

or 

$$ V_R = iR $$
