## Question 1

**Let P = |ψ⟩⟨ψ|. Compute (I − 2P )|ψ⟩ and (I − 2P )$|ψ^⊥⟩$**

$(I - 2p)|\psi\rangle:$

$(I - 2p)|\psi\rangle$

$= |\psi\rangle - 2(|ψ⟩⟨ψ|\psi\rangle)$

= $|\psi\rangle - 2|\psi\rangle$ 

= $-|\psi\rangle$

$(I - 2p)||\psi\rangle^{\dagger}:$

$(I - 2p)||\psi\rangle^{\dagger}$ 

$= |\psi\rangle^{\dagger} - 2(|ψ⟩⟨ψ|\psi\rangle^{\dagger})$

$= |\psi\rangle^{\dagger} - 0$

= $|\psi\rangle^{\dagger}$

**Show that (I − 2|ψ⟩⟨ψ|) is unitary whenever |ψ⟩ is a unit vector.**

Let $U = (I − 2|ψ⟩⟨ψ|)$. If $U$ is unitary, then it means
that $U^{\dagger} = U^{-1}$.

$|\psi\rangle =$

$$
\begin{bmatrix}
a + bi \\
c + di \\
\end{bmatrix} 
$$

$\langle\psi| =$

$$
\begin{bmatrix}
a - bi & c - di \\
\end{bmatrix}
$$

$U^{\dagger} = I^{\dagger} - 2|\psi\rangle^{\dagger}\langle\psi|^{\dagger}$
$U^{\dagger} = I - 2|\psi\rangle\langle\psi| = U$

Applying $U^{\dagger}$ onto $U$, we have $U^2$ 

$= (I - 2|\psi\rangle\langle\psi|)(I - 2|\psi\rangle\langle\psi|)$

= $I - 4|\psi\rangle\langle\psi| + 4(|\psi\rangle\langle\psi||\psi\rangle\langle\psi|)$

Since $|\psi\rangle$ is a unit vector, it means that $\langle\psi|\psi\rangle = 1$

$I - 4|\psi\rangle\langle\psi| + 4(|\psi\rangle\langle\psi||\psi\rangle\langle\psi|)$

= $I - 4|\psi\rangle\langle\psi| + 4|\psi\rangle\langle\psi|$ 

= $I$

Since  $U^{\dagger}U = I$, we have shown that U is unitary whenever $|\psi\rangle$ is a unit 
vector.

**What is the geometric interpretation of the transformation I − 2|0⟩⟨0| in $R^2$**

For any $|\psi\rangle$ we apply the transformation on, we will receive 
$|\psi\rangle - 2|0\rangle\langle0|\psi\rangle$

$\langle0|\psi\rangle$ tells us how much $\psi\rangle$ projects onto the x axis. Let $k$ be the 
factor denoting how much \psi\rangle$ projects onto the x-axis.

With $|\psi\rangle - 2|0\rangle\langle0|\psi\rangle$, this becomes
$|\psi\rangle - 2k|0\rangle$.

This tells us that we are taking the negation of the x coordinate of $|\psi\rangle$, which is 
equivalent to a relection over the y-axis. 

The geometric interpretation of the transformation is that it performs a reflection over the 
y-axis.

**Does the transformation I − 2|0⟩⟨0| have a similar geometric interpretation in the Bloch sphere? Why or why not**

Any point on the bloch sphere can be represented as $cos(\theta)|0\rangle + e^{i\phi}sin(\theta)$.

When applying an arbitrary point on the block sphere to the transformation, we obtain
$cos(\theta)|0\rangle + e^{i\phi}sin(\theta) - 2cos(\theta)|0\rangle = -cos(\theta)|0\rangle + e^{i\phi}sin(\theta) $.

$-cos(\theta)|0\rangle + e^{i\phi}sin(\theta) = e^{i\pi}(cos(\theta)|0\rangle + e^{i(\phi - \pi)}sin(\theta))$

Referring to the diagram of the bloch sphere, we know that rotating $\phi$ by $\pi$ is 
equivalent to rotating 180 degrees with respect to the z-axis.


## Question two

### How is a parity measurement of two qubits different from measuring both bits in the computational basis and then taking their parity?
A parity measurement of two qubits maps directly to the 0 parity or 1 parity subspace. 

A parity measurement of two qubits after measuring both bits in the computational basis 
changes the state of the qubits before projecting them onto the parity subspaces. This 
could differ since my state has changed, affecting my representation in the computational 
basis. 


The parity measurement of two qubits differs from measuring both bits in the computational basis and then taking their parity since
you may potentially change the state of the qubit by measuring in the computational basis. By
doing this and then measuring the parity, you can receive different values than if you had 
measured the parity using the given basis.


### Devise a circuit using CN OT gates and computational basis measurement which measures the parity of two qubits without measuring either qubit itself.
Measure the ancilla qubit after in the computational basis. If it is 0, then the parity of 
the two other qubits is 0.

If not, the parity of the two other qubits is 1.

## Question three

### Calculate the density matrix of {( 1√2 |0⟩ + 1√2 |+⟩, 1)}

The density matrix would be $(\frac{1}{\sqrt{2}}|0⟩ + \frac{1}{\sqrt{2}}|+⟩) (\frac{1}{\sqrt{2}}\langle 0| + \frac{1}{\sqrt{2}}\langle +|)$

= $\frac{1}{2}(|0\rangle \langle 0| + |0\rangle \langle +| + |+\rangle \langle 0| + |+\rangle \langle 0|)$

= $\frac{1}{2}(|0\rangle (\langle 0| + \langle +|) + |+rangle (\langle 0| + \langle +|))$


$$ \frac{1}{2}
\begin{bmatrix}
1 + \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\
0 & 0 \\
\end{bmatrix} +
\begin{bmatrix}
1 + \frac{1}{\sqrt{2}} & 1 \\
1 + \frac{1}{\sqrt{2}}  & 1 \\
\end{bmatrix} 
$$

=
$$\frac{1}{2}
\begin{bmatrix}
4 & 2 \\
2 & 1 \\
\end{bmatrix}
$$
