## Question one
### The Bloch Sphere is a generalization of the representation of a complex number z with |z|^2 = 1 as a point on the unit circle in the complex plane. From this starting point, derive the equation of the Bloch sphere

I know that my point on the bloch sphere is a linear combination of 
$|0\rangle$ and $|1\rangle$. Therefore, $z = a|0\rangle + b|1\rangle, a, b \in \mathbb{C}$.

I can represent a complex number z (a point on the bloch sphere) as a + bi, $a, b \in \mathbb{R}$.

Using Euler's theorem, I can also represent z as $re^{i\theta}$.

Using this fact, I can represent $a|0\rangle + b|1\rangle$ as $r_ae^{i{\theta}_a}|0\rangle +  r_be^{i{\theta}_b}|1\rangle$

Knowing that a difference of global phase does not affect the measurement results, I can factor out 
$e^{i{\theta}_a}$ in z, obtaining $r_a|0\rangle +  r_be^{i({\theta}_b - {\theta}_a)}|1\rangle$

Let $\phi = {\theta}_b - {\theta}_a$. We can represent the above expression as
$r_a|0\rangle +  r_be^{i\phi}|1\rangle$.

If we measure the probabilities of measuring the $|0\rangle$ and $|1\rangle$ states, it will 
be $|r_a|^2$ and $|r_b|^2$ respectively.

If we choose to represent $r_b$ as $x + iy, x, y \in \mathbb{R}$, then we obtain

$|r_a|^2$ and $(x + iy)(x - iy)$, which is equivalent to 

$|r_a|^2$ and $x^2 + y^2$

Knowing that $|r_a|^2$ and $|r_b|^2$ sum to one, we know that
$|r_a|^2$ and $x^2 + y^2$ also sums to 1.

Since we have that $|r_a|^2 + x^2 + y^2 = 1$, we know that it is the equation of a sphere 
with radius one.

Knowing this, we can say that $|r_a|^2 + x^2 + y^2 = z^2 + x^2 + y^2$,

Knowing that we are working with a sphere, we can use the equations $x = sin(\theta)cos(\phi), y = sin(\theta)cos(\phi), z = cos(\theta)$ 
to simplify our expression. 

$r_a|0\rangle +  r_be^{i\phi}|1\rangle = r_a|0\rangle +  (x + iy)|1\rangle$ becomes 
$cos(\theta)|0\rangle  + sin(\theta)(cos(\phi) + isin(\phi))|1\rangle$.

Using Euler's formula, our expression above becomes 

$cos(\theta)|0\rangle  + sin(\theta)e^{i\phi}|1\rangle$.

We can further simplify our expression noticing that we only need to have $\theta$ be within $[0, \frac{\pi}{2}]$
since we can obtain all the larger values of $\theta$ by applying a global phase.

Our expression above becomes $cos(\frac{\theta}{2})|0\rangle  + sin(\frac{\theta}{2})e^{i\phi}|1\rangle$, which
is the equation of the bloch sphere.

### Show that the global phase factor, eiγ, has no observable effect on the probabilities, |α|^2 and |β|^2

We know that a quantum state can be represented as $a|0\rangle + b|0\rangle, a, b \in \mathbb{C}$

The probabilities of measuring the $|0\rangle$ and $|1\rangle$ states are ${|a|}^2$ and ${|b|}^2$
respectively.

If we apply a global phase factor $e^{i\phi}$ onto the quantum state, we obtain $ae^{i\phi}|0\rangle + be^{i\phi}|0\rangle$

Calculating the probabilities of measuring the $|0\rangle$ and $|1\rangle$, we obtain
${|ae^{i\phi}|0\rangle|}^2$ and  ${|be^{i\phi}|1\rangle|}^2$.

Calculating ${|ae^{i\phi}|0\rangle|}^2$, it is
$a^*e^{-i\phi}\langle 0| * ae^{i\phi}|0\rangle$ =
$a^*e^{-i\phi} * ae^{i\phi}$ =
$a^2$ =
$|a|^2$ 

For the probability of measuring $|1\rangle$, it is 

$b^*e^{-i\phi}\langle 0| * be^{i\phi}|0\rangle$ =
$b^*e^{-i\phi} * be^{i\phi}$ =
$b^2$ =
$|b|^2$ 

From this, we can see that a global phase factor has no observable effect on the probabilities 
of measuring the $|0\rangle$ and $|1\rangle$ states.

### Show that opposite states on the Bloch sphere are orthogonal.

Let $A$ be an arbitrary quantum state of the form $cos(\theta)|0\rangle + e^{i\phi}sin(\theta)|1\rangle, \phi \in \mathbb{R}$.

For the opposite state of $A$, we only need to multiply it by -1. 

We know that $-1 = e^{i\pi}$. Using that fact, $-A$ becomes

$e^{i\pi}cos(\pi - \theta)|0\rangle + e^{i\pi}e^{i\phi}sin(\pi - \theta)|0\rangle = e^{i\pi}cos(\pi - \theta)|0\rangle + e^{i(\phi + \pi)}sin(\pi - \theta)|1\rangle$

Taking the dot product of $-A$ and $A$, we obtain
(e^{-i\pi}cos(\pi - \theta)|0\rangle + e^{-i(\phi + \pi)}sin(\pi - \theta)|1\rangle)(e^{i\pi}cos(\pi - \theta)|0\rangle + e^{i(\phi + \pi)}sin(\pi - \theta)|1\rangle)
,which becomes







