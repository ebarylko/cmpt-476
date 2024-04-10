## Question 1

### Part 1
I must show that $(X \otimes Z) * (Z \otimes X) = (Z \otimes X) * (X \otimes Z)$.

Using the fact that $XZ = -ZX$, I can modify the above expression to equivalently 
be $(-Z \otimes X) * (Z \otimes X) = (Z \otimes X) * (-Z \otimes X)$. I can pull out the 
constant of $-1$ from both sides of the equation to obtain
$-1((Z \otimes X) * (Z \otimes X)) = -1((Z \otimes X) * (Z \otimes X))$.

I have therefore showed that $(X \otimes Z)$ and $(Z \otimes X)$ are commutative.

### Part 2

Given $U(t) = e^{-i\hat{H}t} = e^{-it[{\theta}_1 (Z \otimes X) + {\theta}_2 (X \otimes Z)]}$, we can break it further
down into $e^{-it[{\theta}_1 (Z \otimes X)]} *  e^{-it[{\theta}_2 (X \otimes Z)]}$ since $(X \otimes Z)$ and $(Z \otimes X)$ commute.

Given $U(t) = $e^{-it[{\theta}_1 (Z \otimes X)]} *  e^{-it[{\theta}_2 (X \otimes Z)]}$, we can simulate the 
Hamiltonian by first applying $e^{-it[{\theta}_2 (X \otimes Z)]}$  and then $e^{-it[{\theta}_1 (Z \otimes X)]}$.

With $e^{-it[{\theta}_2 (X \otimes Z)]}$, we know that it is equivalent to
$e^{-it[{\theta}_2 ((H \otimes I) * (Z \otimes I) * (H \otimes Z))]}$. Simulating this hamiltonian on 
a circuit, we obtain 
![Second Hamiltonian](second_hamiltonian.jpeg), where 
the third line was obtained using the fact that ![Z gate simplification](z_gate.jpeg).

Simulating $e^{-it[{\theta}_1 (Z \otimes X)]}$ in a circuit, we know it 
is equivalent to $e^{-it[{\theta}_1 ((Z \otimes H) * (I \otimes Z) * (I \otimes H))]}$. In circuit form, it 
would be ![First Hamiltonian](first_hamiltonian.jpeg), where
the third line was obtained using the fact that ![Z gate simplification](z_gate.jpeg).

Combining these Hamiltonians, the full circuit simulating
$U(t) = $e^{-it[{\theta}_1 (Z \otimes X)]} *  e^{-it[{\theta}_2 (X \otimes Z)]}$
is ![Full circuit](full_circuit.jpeg)


### Part 3
Using $c = 1.5, \epsilon = 10^{-17}$ in the formula depth = $log_{2}^{1.5} (\frac{1}{\epsilon})$, I obtain 
depth = $log^{1.5}_{2} (\frac{1}{10^{-17}}) \approx 425$ for a single qubit unitary. Considering we 
have two usages of the rotation gate, we have in total a depth of 850 gates for the circuit.


### Part 4
For a general vector eigenvector $q$ of $(X \otimes Z)$ and $(Z \otimes X)$, we know q is of the form 

$$
\begin{bmatrix}
a \\
b \\
c \\
d \\
\end{bmatrix}
$$


Applying $(X \otimes Z)q$, we find that $q$ is the eigenvector corresponding to the eigenvalue of 1 if 

$$
(X \otimes Z) \begin{bmatrix}
a \\
b \\
c \\
d \\
\end{bmatrix} =
\begin{bmatrix} c \\
-d \\
a \\
-b
\end{bmatrix}$$

The conditions for $q$ being the eigenvector with the eigenvalue of 1 are $a = c, b = -d$.

If $q$ is the eigenvector corresponding to the eigenvalue of -1, it means that  

$$
(X \otimes Z) \begin{bmatrix}
a \\
b \\
c \\
d \\
\end{bmatrix} =
\begin{bmatrix} -c \\
d \\
-a \\
b
\end{bmatrix}$$

The conditions for $q$ being the eigenvector with the eigenvalue of -1 are $a = -c, b = d$.

Similarly, for $(Z \otimes X)$ the eigenvector corresponding to the eigenvalue of 1 is

$$
(Z \otimes X) \begin{bmatrix}
a \\
b \\
c \\
d \\
\end{bmatrix} =
\begin{bmatrix} b \\
a \\
-d \\
-c
\end{bmatrix}$$

The conditions for $q$ being the eigenvector with the eigenvalue of 1 are $a = b, c = -d$.

The eigenvector corresponding to the eigenvalue of -1 is

$$
(Z \otimes X) \begin{bmatrix}
a \\
b \\
c \\
d \\
\end{bmatrix} =
\begin{bmatrix} -b \\
-a \\
d \\
c
\end{bmatrix}$$

The conditions for $q$ being the eigenvector with the eigenvalue of -1 are $a = -b, c = d$.

If we combine the conditions on the entries of the eigenvectors for $(X \otimes Z)$ and $(Z \otimes X)$, we can 
find the shared eigenvectors.

### Combining the conditions for the +1 eigenspaces of (X ⊗ Z) and (Z ⊗ X)

Combining the conditions for the $+1$ eigenspaces of $(X \otimes Z)$ and $(Z \otimes X)$, 
we have that $a = c, b = -d, a = b, c = -d$. With this rule, we have that $a = b = c = -d$.

The eigenvector that complies with this condition is 

$$
\begin{bmatrix} 1 \\
1 \\
1 \\
-1
\end{bmatrix}$$

Applying $(X \otimes Z)$ and $(Z \otimes X)$ on this eigenvector, we obtain 

$$
(X \otimes Z) \begin{bmatrix}
1 \\
1 \\
1 \\
-1 \\
\end{bmatrix} =
\begin{bmatrix} 1 \\
1 \\
1 \\
-1
\end{bmatrix}$$

and 

$$
(Z \otimes Y) \begin{bmatrix}
1 \\
1 \\
1 \\
-1 \\
\end{bmatrix} =
\begin{bmatrix} 1 \\
1 \\
1 \\
-1
\end{bmatrix}$$

We see that 

$$
\begin{bmatrix} 1 \\
1 \\
1 \\
-1
\end{bmatrix}$$

is the eigenvector corresponding to the eigenvalue 1 for $(X \otimes Z)$ and $(Z \otimes X)$.


### Combining the conditions for the +1 eigenspace of (X ⊗ Z) and the -1 eigenspace of (Z ⊗ X)
The combined conditions are $a = c, b = -d, a = -b, c = d$, simplifying to $a = c = d = - b$.

The eigenvector satisfying this condition 

$$
\begin{bmatrix} 1 \\
-1 \\
1 \\
1
\end{bmatrix}$$


Applying $(X \otimes Z)$ and $(Z \otimes X)$ on this eigenvector, we obtain

$$
(X \otimes Z) \begin{bmatrix}
1 \\
-1 \\
1 \\
1 \\
\end{bmatrix} =
\begin{bmatrix} 1 \\
-1 \\
1 \\
1
\end{bmatrix}$$

and

$$
(Z \otimes X) \begin{bmatrix}
1 \\
-1 \\
1 \\
1 \\
\end{bmatrix} =
\begin{bmatrix} -1 \\
1 \\
-1 \\
-1
\end{bmatrix}$$

We see that the eigenvector


$$
\begin{bmatrix} 1 \\
-1 \\
1 \\
1
\end{bmatrix}$$

is the eigenvector corresponding to the eigenvalue 1 and -1 for $(X \otimes Z)$ and $(Z \otimes X)$, respectively.

### Combining the conditions for the -1 eigenspace of (X ⊗ Z) and (Z ⊗ X)

## Question two


### Part 1

Given that $H$ and $M$ are given, my search function $f(x): \set{0, 1}^{32} \rightarrow \set{0, 1}$ would 
be $f(x) = h(x) = H \land x \neq M$.

To implement the oracle, I would first create my uniform superposition $H^{\otimes 32} |0\rangle^{\otimes 32}$. I would
then apply my $U_{\bar{f}}: |x\rangle \rightarrow (-1)^{f(x)}$, using $f(x)$ defined earlier, and $U_{diff}$ enough 
times to rotate our initial to the wanted state. We then measure 


### Part 2
Using that we need $\frac{\pi \sqrt{2^n}}{4} - \frac{1}{2}$ iterations for n bits, we can 
substitute n for 32 in the aforementioned expression. We obtain $\frac{\pi \sqrt{2^{32}}}{4} - \frac{1}{2} = \frac{\pi 2^{16}}{4} - \frac{1}{2}$. 
This simplifies to $\pi 2^{14}- \frac{1}{2}$, which tells us we need $\pi 2^{14}- \frac{1}{2} \approx \pi 2^{14} - 1$ many iterations.


### Part 3

After k rotations, our current state is $sin((2k + 1)\theta) |\phi_{good}\rangle + cos((2k + 1)\theta) |\phi_{bad}\rangle$.
The probability I am in the good state is $sin^2((2k + 1)\theta)$. Using $k = 2^14 \pi - \frac{1}{2}$ discovered in the 
last question and $\theta = sin^{-1} \frac{1}{2^{16}}$, I obtain that $sin^2((2k + 1)\theta) = sin^2((2^15 - 2)sin^{-1} \frac{1}{2^{16}}) = 1$.

The approximate probability of success is 1.

Make a note about how this probability was obtained using the limited precision of the calculator.




## Question three

Let us define $|0\rangle _L = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle), |1\rangle _L = \frac{1}{\sqrt{2}}(|01\rangle + |10\rangle)$.

Applying $(X \otimes X)$ on $|0\rangle _L$, we obtain $(X \otimes X)\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle) = \frac{1}{\sqrt{2}}(|11\rangle + |00\rangle) = |0\rangle _L$.

Applying $(X \otimes X)$ on $|1\rangle _L$, we obtain $(X \otimes X)\frac{1}{\sqrt{2}}(|01\rangle + |10\rangle) = \frac{1}{\sqrt{2}}(|10\rangle + |01\rangle) = |1\rangle _L$.

If the bit flips are independent, then we transform $|0\rangle _L$ to $|1\rangle _L$ and $|1\rangle _L$ to $|0\rangle _L$. This 
occurs since our subspace protected against the errors caused by $(X \otimes X)$ by mapping one state in the superposition to
the other state in the superposition. With independent bit flips, the error maps a state in $|0\rangle _L$ to 
a state in $|1\rangle _L$, and vice versa. 
