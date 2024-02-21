## Question one
### The Bloch Sphere is a generalization of the representation of a complex number z with |z|^2 = 1 as a point on the unit circle in the complex plane. From this starting point, derive the equation of the Bloch sphere

I know that my point on the bloch sphere is a linear combination of 
$|0\rangle$ and $|1\rangle$. Therefore, $z = a|0\rangle + b|1\rangle, a, b \in \mathbb{C}$.

I can represent a complex number z (a point on the bloch sphere) as a + bi, $a, b \in \mathbb{R}$.

Using Euler's theorem, I can also represent z as $re^{i\theta}$.

Using this fact, I can represent $a|0\rangle + b|1\rangle$ as $r_ae^{i{\theta}_a}|0\rangle +  r_be^{i{\theta}_b}|1\rangle$

Knowing that a difference of global phase does not affect the measurement results, I can factor out 
$e^{i{\theta}_a} in z$, obtaining $r_a|0\rangle +  r_be^{i({\theta}_b - {\theta}_a)}|1\rangle$

Let $\phi = {\theta}_b - {\theta}_a$. We can represent the above expression as
$r_a|0\rangle +  r_be^{i\phi}|1\rangle$.

I do not understand how to factor out the coefficients and be left with the formula I need to 
obtain.

### Show that the global phase factor, eiγ, has no observable effect on the probabilities, |α|2 and |β|2
.