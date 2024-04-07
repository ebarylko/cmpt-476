## Question 1

### Part 1
I must show that $(X \otimes Z) * (Z \otimes X) = (Z \otimes X) * (X \otimes Z)$.

Using the fact that $XZ = -ZX$, I can modify the above expression to equivalently 
be $(-Z \otimes X) * (Z \otimes X) = (Z \otimes X) * (-Z \otimes X)$. I can pull out the 
constant of $-1$ from both sides of the equation to obtain
$-1((Z \otimes X) * (Z \otimes X)) = -1((Z \otimes X) * (Z \otimes X))$.

I have therefore showed that $(X \otimes Z)$ and $(Z \otimes X)$ are commutative.

### Part 2

### Part 3
Using $c = 1.5, \epsilon = 10^{-17}$ in the formula depth = $log^{1.5}_{2} [ \frac{1}{\epsilon ]$, I obtain 
depth = $log^{1.5}_{2} [\frac{1}{10^{-17}}] \approx 425$.

### Part 4

## Question two

### Part 1

Given that $H$ and $M$ are given, my search function $f(x): \set{0, 1}^{32} \rightarrow \set{0, 1}$ would 
be $f(x) = h(x) = H \land x \neq M$.

### Part 2
Using that we need $\frac{\pi \sqrt{2^n}}{4} - \frac{1}{2}$ iterations for n bits, we can 
substitute n for 32 in the aforementioned expression. We obtain $\frac{\pi \sqrt{2^{32}}}{4} - \frac{1}{2} = \frac{\pi 2^{16}}{4} - \frac{1}{2}$. 
This simplifies to $\pi 2^{14}- \frac{1}{2}$, which tells us we need $\pi 2^{14}- \frac{1}{2} \approx \pi 2^{14} - 1$ many iterations.


### Part 3

The approximate probability of success would be $\frac{1}{\sqrt{2^n}} + \frac{2}{\sqrt{2^n}}(\frac{\pi \sqrt{2^n}}{4} - \frac{1}{2})$. 
Substituting $n = 32$ in the expression above, I obtain $\frac{1}{\sqrt{2^{32}}} + \frac{2}{\sqrt{2^{32}}}(\frac{\pi \sqrt{2^{32}}}{4} - \frac{1}{2})$
= $\frac{1}{2^{16}} + \frac{2}{2^{16}}(\pi 2^{14} - 1)$.

The expression above simplifies to $\frac{1}{2^{16}} + \frac{1}{2^{15}}(\pi 2^{14} - 1) = \frac{1}{2^{16}}  + \frac{\pi}{2} - \frac{1}{2^{15}}$, 
which can further be reduced to $\frac{\pi}{2} - \frac{1}{2^{16}}$.
