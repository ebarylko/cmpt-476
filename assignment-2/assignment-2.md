## Question 1

Let $\beta$ = $\{|A\rangle, |B\rangle\}$


### Show that rotating the basis twice by θ is the same as rotating once by an angle of 2θ

The rotation matrix $R_{\theta}$ = 

$$ \begin{bmatrix}
cos(\theta) & -sin(\theta) \\
sin(\theta) & cos(\theta) \\
\end{bmatrix} $$

Rotating $\beta$ once by $\theta$ = 

$\{cos(θ)|A⟩ + sin(θ)|B⟩, − sin(θ)|A⟩ + cos(θ)|B⟩\}$

Rotating $\beta$ once more by theta results in the new basis

$\beta^{\prime\prime}$ = $\{cos^2(θ)|A⟩ + 2sin(θ)cos(θ)|B⟩ - sin^{2}(θ)|A\rangle, −sin^2(θ)|B⟩ - 2cos(θ)sin(θ)|A⟩ + cos^2(θ)|B⟩\}$

The rotation matrix $R_{2\theta}$ = 

$$ \begin{bmatrix}
cos(2\theta) & -sin(2\theta) \\
sin(2\theta) & cos(2\theta) \\
\end{bmatrix} $$ 

=

$$ \begin{bmatrix}
cos^2(\theta) - sin^2(\theta) & -2sin(\theta)cos(\theta) \\
2sin(\theta)cos(\theta) & cos^2(\theta) - sin^2(\theta) \\
\end{bmatrix} $$ 


Applying $R_{2\theta}$ on $\beta$:

$R_{2\theta}\beta$ =

$\{|A\rangle(cos^2(\theta) - sin^2(\theta)) + |B\rangle(2sin(\theta)cos(\theta)), |A\rangle(-2sin(\theta)cos(\theta)) + |B\rangle(cos^2(\theta) - sin^2(\theta))\}$ 

= $\beta^{\prime\prime}$.

Therefore, rotating the basis twice by $\theta$ is equivalent to rotating it once by $2\theta$.

### Calculate the angle θ and number of measurements needed to reach the |1⟩ state with success probability p for some positive real number p close to 1.

Let $A\rangle = |0\rangle$ and $B\rangle = |1\rangle$.

After rotating $\beta$ once by $\theta$, we obtain that $\beta^{\prime} = (cos(θ)|A⟩ + sin(θ)|B⟩, − sin(θ)|A⟩ + cos(θ)|B⟩), with |A^{\prime}\rangle = cos(θ)|A⟩ + sin(θ)|B⟩,  |B^{\prime}\rangle = − sin(θ)|A⟩ + cos(θ)|B⟩$

Measuring $|0\rangle$ in $\beta^{\prime}$ gets us $|A^{\prime}\rangle$ 
with probability $cos^2(\theta)$, and $|B^{\prime}\rangle$ with a 
probability $sin^2(\theta)$.

As $\theta \rightarrow 0$, the probability of measuring 
the initial state in $|A^{\prime}\rangle$ grows close to 1 and
the probability of measuring the initial state in 
$|B^{\prime}\rangle$ grows close to 0.

If $\theta$ is very close to zero, then the probability of mapping the 
initial state to $|A^{\prime}\rangle$ is very high.

If we rebind the initial state to what the initial state mapped to 
and rebind $\beta$ to $\beta^{\prime}$ and repeat the measurement of 
the initial state in the rotated basis, then the probability of
mapping the initial state to $A^{\prime\prime}$ is $cos^2(\theta)$. 
Repeatedly rotating the basis, mapping the initial state, and 
rebinding the basis and initial state results in the $|0\rangle$ state
being moved closer to the $|1\rangle$ state. 

For the value of $p$, we can create a lower bound for it 
as the probability of always mapping to the rotated $|A\rangle$ 
basis vector.

The probability of always mapping to the $|A\rangle$ basis vector
is $(pr(a_1) + pr(a_2) + ... pr(a_n))$, where $a_i$ represents
the event in which the initial state maps to $|1\rangle$ after
$i$ rotations. The value of the expression can be bounded by the 
union-bound rule. 

This means that $(pr(a_1) + pr(a_2) + ... pr(a_n)) < pr(a_1) + pr(a_2) + ... pr(a_n)$

Since we always rotate $\beta$ by an angle of $\theta$, the probability of
mapping the initial state to $A^{\prime\prime}$ is $cos^2(\theta)$. 
This means that $pr(a_i) = pr(a_2) = p(a_n)$

Let $n$ be the number of rotations. $n = \frac{\pi}{2\theta}$.

$p = n * pr(a_1)$ 

$p = \frac{\pi}{2\theta} * cos^2(\theta)$ 

$\frac{2p}{\pi} = \frac{cos^2(\theta)}{\theta}$


$\sqrt{\frac{p}{n}} = cos(\theta)$

$arccos(\sqrt{\frac{p}{n}}) = theta$



## Question 2

$I$ = 

$$ \begin{bmatrix}
1 & 0 \\
0 &  1 \\
\end{bmatrix} $$

$Z$ =

$$ \begin{bmatrix}
1 & 0 \\
0 &  -1 \\
\end{bmatrix} $$

$X$ =

$$ \begin{bmatrix}
0 & 1 \\
1 &  0 \\
\end{bmatrix} $$

$Y$ =

$$ \begin{bmatrix}
0 & -i \\
i &  0 \\
\end{bmatrix} $$ 

### Compute the matrices X⊗Z and Z⊗X

#### X⊗Z

$X \otimes Z$ =

$$ \begin{bmatrix}
0Z & Z \\
Z &  0Z \\
\end{bmatrix} $$  

=


$$ \begin{bmatrix}
\begin{bmatrix} 0 & 0 \\ 0 & 0\end{bmatrix} & \begin{bmatrix} 1 & 0 \\ 0 & -1\end{bmatrix} \\
\begin{bmatrix} 1 & 0 \\ 0 & -1\end{bmatrix} & \begin{bmatrix} 0 & 0 \\ 0 & 0\end{bmatrix}\\
\end{bmatrix} 
$$  


#### Z⊗X

$Z \otimes X$ =

$$ \begin{bmatrix}
1X & 0X \\
0X &  -X \\
\end{bmatrix} $$  

==


$$ \begin{bmatrix}
\begin{bmatrix} 0 & 1 \\ 1 & 0\end{bmatrix} & \begin{bmatrix} 1 & 0 \\ 0 & -1\end{bmatrix} \\
\begin{bmatrix} 0 & 0 \\ 0 & 0\end{bmatrix} & \begin{bmatrix} 0 & -1 \\ -1 & 0\end{bmatrix}\\
\end{bmatrix}
$$  

### Show that the non-identity Pauli matrices anti-commute: that is, U V = −V U for every pair of X, Y , and Z matrices where U 6 = V

#### XY = -YX

$XY$ 

=

$$ \begin{bmatrix}
0 & 1 \\
1 &  0 \\
\end{bmatrix} 
\begin{bmatrix}
0 & -i \\
i &  0 \\
\end{bmatrix} $$ 

= 

$$
\begin{bmatrix}
i & 0 \\
0 &  -i \\
\end{bmatrix} $$ 

$YX$ 

=


$$\begin{bmatrix}
0 & -i \\
i &  0 \\
\end{bmatrix}
\begin{bmatrix}
0 & 1 \\
1 &  0 \\
\end{bmatrix} 
$$ 

= 

$$\begin{bmatrix}
-i & 0 \\
0 &  i \\
\end{bmatrix} $$ 

$XY = - YX$

#### XZ = -ZX
$XZ$ 

= 


$$
\begin{bmatrix}
0 & 1 \\
1 &  0 \\
\end{bmatrix}
\begin{bmatrix}
1 & 0 \\
0 &  -1 \\
\end{bmatrix} 
$$

=


$$\begin{bmatrix}
0 & -1 \\
1 &  0 \\
\end{bmatrix} $$ 

$ZX$  

$$
\begin{bmatrix}
1 & 0 \\
0 &  -1 \\
\end{bmatrix}
\begin{bmatrix}
0 & 1 \\
1 &  0 \\
\end{bmatrix}
$$

=

$$\begin{bmatrix}
0 & 1 \\
-1 &  0 \\
\end{bmatrix} $$ 

$XZ = -ZX$  

#### YZ = -ZY

$YZ$:

$$ 
\begin{bmatrix}
0 & -i \\
i &  0 \\
\end{bmatrix}
\begin{bmatrix}
1 & 0 \\
0 &  -1 \\
\end{bmatrix}
$$ 

=

$$\begin{bmatrix}
0 & i \\
i &  0 \\
\end{bmatrix} $$ 

$ZY$:

$$
\begin{bmatrix}
1 & 0 \\
0 &  -1 \\
\end{bmatrix}
\begin{bmatrix}
0 & -i \\
i &  0 \\
\end{bmatrix}
$$ 

= 

$$\begin{bmatrix}
0 & -i \\
-i &  0 \\
\end{bmatrix} $$ 

$YZ = -ZY$.

### Show that the Pauli matrices I, X, Z, Y are linearly independent

To show that the Pauli matrices are linearly independent, I must show
that the only solution to the equation $c_1I + c_2X + c_3Z + c_4Y = 0$ is
$c_1 = c_2 = c_3 = c_4 = 0$.

Using the following matrix to represent the equation above, 

$$\begin{bmatrix}
1 & 1 & 0 & 0 \\
0 &  0 & 1 & -i \\
0 &  0 & 1 & i \\
1 &  -1 & 0 & 0 \\
\end{bmatrix} $$

Row reducing it will show if there exists a non-trivial solution to the 
equation.

Row reducing the matrix above results in  

$$\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 &  1 & 0 & 0 \\
0 &  0 & 1 & 0 \\
0 &  0 & 0 & 1 \\
\end{bmatrix} $$

This indicates that only the trivial solution is an answer to the equation
$c_1I + c_2X + c_3Z + c_4Y = 0$. Based on this, we can conclude that
the pauli matrices are linearly independent

### Show that the Pauli matrices form a basis for the space of 2 × 2 complex-valued matrices.
If the Pauli matrices form a basis for the space of 2 × 2 complex-valued matrices, 
then for any complex-valued matrix 

$$
\begin{bmatrix}
a & b \\
c &  d \\
\end{bmatrix}
$$

It can be composed out of a linear combination of the Pauli matrices.

Since the Pauli matrices are linearly independent and there are four 
matrices, this means they span the space of 2 x 2 complex-valued matrices.
Therefore, the Pauli matrices from a basis for the space 
of 2 × 2 complex-valued matrices.


## Question four
Let $CZ$ =

$$\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 &  1 & 0 & 0 \\
0 &  0 & 1 & 0 \\
0 &  0 & 0 & 01 \\
\end{bmatrix} $$

Let $|\phi\rangle = |\psi\rangle = |0\rangle + |1\rangle$

$|\phi\rangle \otimes \psi\rangle$  

= 

$$\begin{bmatrix}
1 \\
1 \\
1 \\ 
1 \\
\end{bmatrix} $$

$CZ(|\phi\rangle = |\psi\rangle = |0\rangle)$ 

= 


$$\begin{bmatrix}
1 \\
1 \\
1 \\
-1 \\
\end{bmatrix} $$

If $CZ$ is not entangling, than we can write $CZ(|\phi\rangle = |\psi\rangle = |0\rangle)$ 
as a tensor product of two kets.


We can say that $CZ(|\phi\rangle = |\psi\rangle = |0\rangle)$  

=

$$\begin{bmatrix}
a \\
b \\
\end{bmatrix} \otimes
\begin{bmatrix}
c \\
d \\
\end{bmatrix}
$$

=

$$\begin{bmatrix}
ac \\
ad \\
bc \\
bd \\
\end{bmatrix} $$

To have this equality, we need the following conditions to hold:
* $ac$ = 1
* ad = 1
* bc = 1
* bd = -1

For $ac = 1$ to be true, both a and c must be positive or negative. 

For $ad = 1$ to be true, both a and d must be positive or negative. As
the value of a was decided in the equation above, d must have the
same sign as a.


For $bc = 1$ to be true, both b and c must be positive or negative.
Since we decided on the sign of c in the first equation, c must
have the same sign as b.

For $bd = 1$ to be true, one of b and d must be positive and the
other negative.

However, d has the same sign as a and b has the same sign
as c. Furthermore, the product of a and c is a positive value. This
implies the product of b and d is also a positive value. Since we 
cannot create this matrix out of a tensor product of two vectors,  
we know we have an entangled system. 

Since $|\phi\rangle \otimes |\psi\rangle$ is an untangled system, this 
means that $CZ$ is entangling

## Question five

$\phi\rangle = \frac{i\sqrt{2}}{\sqrt{3}}|00\rangle + \frac{1}{\sqrt{2}\sqrt{3}}|01\rangle + \frac{1}{\sqrt{2}\sqrt{3}}|10\rangle$

### Calculate the probabilities of measuring 0 or 1 in the first qubit and the resulting normalized state vector

#### probability of measuring 0 and resulting unit vector

pr(measure 0 in first qubit) =  $|\frac{i\sqrt{2}}{\sqrt{3}}|^2 +  |\frac{1}{\sqrt{2}\sqrt{3}}|^2$

pr(measure 0 in first qubit) =  $\frac{2}{3} + \frac{1}{6} = \frac{5}{6}$

The resulting state after measuring 0 in the first qubit is $\frac{i\sqrt{2}}{\sqrt{3}}|00\rangle + \frac{1}{\sqrt{2}\sqrt{3}}|01\rangle$, 
which is not a unit vector.

To make the resulting state a unit vector, I must divide by $\sqrt{\frac{5}{6}}$

Let $r^{\prime}$ be the resulting state after measuring 0 in the first 
qubit which is a unit vector.

$r^{\prime} = \frac{1}{\sqrt{\frac{5}{6}}}(\frac{i\sqrt{2}}{\sqrt{3}}|00\rangle + \frac{1}{\sqrt{2}\sqrt{3}}|01\rangle)$ 

#### probability of measuring 1 in the first qubit and resulting unit vector

pr(measure 1 in first qubit) =  $|\frac{1}{\sqrt{2}\sqrt{3}}|^2 = \frac{1}{6}$

The resulting state after measuring 1 in the first qubit is $\frac{1}{\sqrt{2}\sqrt{3}}|10\rangle$,
which is not a unit vector.

To make the resulting state a unit vector, I must divide by $\sqrt{\frac{1}{6}}$

Let $t^{\prime}$ be the resulting state after measuring 1 in the first
qubit which is a unit vector.

$t^{\prime} = \frac{1}{\sqrt{\frac{1}{6}}}\frac{1}{\sqrt{2}\sqrt{3}}|10\rangle$

