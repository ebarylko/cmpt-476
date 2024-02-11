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
A parity measurement of two qubits is a partial measurement that projects
to the 0 parity or 1 parity subspace. It changes the state, but the superposition 
is still maintained and we have uncertainty.

A parity measurement of two qubits after measuring both bits in the computational basis 
projects both onto the computational basiS, removing any uncertainty we had before.
When we then take the parity measurement of this, there no uncertainty when we project 
onto one of the parity subspaces.


The parity measurement of two qubits differs from measuring both bits in the computational basis and then taking their parity since
you may potentially change the state of the qubit by measuring in the computational basis. By
doing this and then measuring the parity, you can receive different values than if you had 
measured the parity using the given basis.


### Devise a circuit using CN OT gates and computational basis measurement which measures the parity of two qubits without measuring either qubit itself.
Measure the ancilla qubit after in the computational basis. If it is 0, then the parity of 
the two other qubits is 0.

If not, the parity of the two other qubits is 1.

There are three cases to consider for the circuit:
* Both of the first two qubits are 0 
* Only one of the first two qubits are 1
* Both of the first two qubits are 0

**Case 1: both qubits are 0**

If both qubits are zero, then the ancilla bit will not be turned on and will return us 
0 for the parity of the other two qubits. This matches the actual parity.

**Case 2: Only one of the qubits are 1**

The ancilla bit will be turned on by the bit that is in the one state, and will have nothing
done to it by the other bit. 

Measuring the ancilla bit, we will obtain 1, which is the parity of the first two qubits.

**Case 3: both of the qubits are 1**

The ancilla bit will be turned on by one bit and will be turned off by the other bit.

Measuring the ancilla bit, we will obtain 0, which is the parity of the first two qubits.

## Question three

### Calculate the density matrix of {( 1√2 |0⟩ + 1√2 |+⟩, 1)}

The density matrix would be $(\frac{1}{\sqrt{2}}|0⟩ + \frac{1}{\sqrt{2}}|+⟩) (\frac{1}{\sqrt{2}}\langle 0| + \frac{1}{\sqrt{2}}\langle +|)$

= $\frac{1}{2}(|0\rangle \langle 0| + |0\rangle \langle +| + |+\rangle \langle 0| + |+\rangle \langle 0|)$

= $\frac{1}{2}(|0\rangle (\langle 0| + \langle +|) + |+\rangle (\langle 0| + \langle +|))$ =


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

-1 + i/sqrt(2)
i/sqrt(2) + 1/2 
1/2


### {(|0⟩, 1/2 ), (|+⟩, 1/2 )}

The density matrix would be $\frac{1}{2}|0\rangle\langle0| + \frac{1}{2}|+\rangle\langle+|$

$\frac{1}{2}|0\rangle\langle0| + \frac{1}{2}|+\rangle\langle+|$ =

$$\frac{1}{2}
\begin{bmatrix} 
\frac{3}{2} & \frac{1}{2} \\
\frac{1}{2} & \frac{1}{2} \\
\end{bmatrix}
$$

=

$$
\begin{bmatrix}
\frac{3}{4} & \frac{1}{4} \\
\frac{1}{4} & \frac{1}{4} \\
\end{bmatrix}
$$

### (|00⟩, 1/2 ), (|01⟩, 1/4 ), (|10⟩, 1/4 )}

The density matrix would be $\frac{1}{4}(2|00\rangle\langle00| + |01\rangle\langle01| + |10\rangle\langle10|)$

$\frac{1}{4}(2|00\rangle\langle00| + |01\rangle\langle01| + |10\rangle\langle10|)$  

= 

$$ \frac{1}{4} 
2\begin{bmatrix}
1 & 0 & 0 & 0\\
0 & 0 & 0 & 0  \\
0 & 0 & 0 & 0  \\
0 & 0 & 0 & 0  \\
\end{bmatrix} 
\begin{bmatrix}
0 & 0 & 0 & 0\\
0 & 1 & 0 & 0  \\
0 & 0 & 0 & 0  \\
0 & 0 & 0 & 0  \\
\end{bmatrix} 
\begin{bmatrix}
0 & 0 & 0 & 0\\
0 & 0 & 0 & 0  \\
0 & 0 & 1 & 0  \\
0 & 0 & 0 & 0  \\
\end{bmatrix} 
$$
= 

$$\frac{1}{4}
\begin{bmatrix}
2 & 0 & 0 & 0\\
0 & 1 & 0 & 0  \\
0 & 0 & 1 & 0  \\
0 & 0 & 0 & 0  \\
\end{bmatrix} 
$$

### Question four

We can represent the density matrix 

$$
\frac{1}{2}
\begin{bmatrix}
0 & 0 & 0 & 0\\
0 & 1 & -1 & 0  \\
0 & -1 & 1 & 0  \\
0 & 0 & 0 & 0  \\
\end{bmatrix}
$$


as $\frac{1}{2}(|01\rangle\langle01| - |01\rangle\langle10| - |10\rangle\langle01| + |10\rangle\langle10|)$


$\frac{1}{2}(|01\rangle\langle01| - |01\rangle\langle10| - |10\rangle\langle01| + |10\rangle\langle10|)$

= 

$$
\frac{1}{2}(|0\rangle\langle0| \otimes |1\rangle\langle1| - 
|0\rangle\langle1| \otimes |1\rangle\langle0| -
|1\rangle\langle0| \otimes |0\rangle\langle1| +
|0\rangle\langle0| \otimes |1\rangle\langle1|)
$$


Tracing out the first qubit, we have 

$$
\frac{1}{2}(\langle0|0\rangle \otimes |1\rangle\langle1| -
\langle1|0\rangle \otimes |1\rangle\langle0| -
\langle0|1\rangle \otimes |0\rangle\langle1| +
\langle0|0\rangle \otimes |1\rangle\langle1|)
$$

= $\frac{1}{2}(2|1\rangle\langle1|) = |1\rangle\langle1|$

The reduced density matrix of the second qubit is $|1\rangle\langle1|$.

## Question five 

Show that $p = {\displaystyle\sum_{i=1}^{n}} p_i|\theta_i\rangle\langle\theta_i|$ is positive-semidefinite.

To show that ${\displaystyle\sum_{i=1}^{n}} p_i|\theta_i\rangle\langle\theta_i|$ is positive-semidefinite, than
\forall $|V\rangle$ of appropriate dimension, $\langle V p V\rangle$ must be non-negative.

$\langle V p V\rangle$  =

{\displaystyle\sum_{i=1}^{n}} p_i|\langle V |\theta_i\rangle \langle \theta_i | V\rangle$ 

Let $\langle V| \theta_i \rangle =  \langle\theta_i|V\rangle = k_i$


${\displaystyle\sum_{i=1}^{n}} p_i|\theta_i\langle V| \theta_i \rangle\langle\theta_i|V\rangle$  =

${\displaystyle\sum_{i=1}^{n}} p_i|{k_{i}}^2$. 

$\forall k_i \in \mathbb{R}, {k_i}^2 \geq 0$

Considering that all the probabilities are non-zero and that every ${k_i}^2 \geq 0$, 
this implies that ${\displaystyle\sum_{i=1}^{n}} p_i|{k_i}^2$ will sum to a non-negative value.

Since this occurs for any $|V\rangle$, $p$ is positive-semidefinite.

## Question six

Let $G = {\displaystyle\sum_{i=1}^{n}} |e_i\rangle\langle e_i| \otimes I$.

$P^{AB} = {\displaystyle\sum_{i, j, e, k}^{}} p_{ijek} |e_i\rangle\langle e_j| \otimes |f_e\rangle \langle f_k|$

$P^B = {\displaystyle\sum_{i, j, e, k}^{}} p_{ijek} \text{Tr}(|e_i\rangle\langle e_j|) \otimes |f_e\rangle \langle f_k|$


$P^B = {\displaystyle\sum_{i, j, e, k}^{}} p_{ijek} \text{Tr}(\langle e_j|e_i\rangle) \otimes |f_e\rangle \langle f_k|$

Even if I apply $G$ solely on to Alice's qubit, Bob's reduced density matrix should not 
change.

Let $(G \otimes I)$ be the gate applied onto Alice's and Bob's shared state.

Applying $(G \otimes I)$ onto Alice's and Bob's shared state and then calculating the 
reduced density matrix, we have that it is 
$P^{B^{\prime}} = {\displaystyle\sum_{i, j, e, k}^{}} p_{ijek} \text{Tr}(|Ge_i\rangle\langle e_jG^{\dagger}|) \otimes |f_e\rangle \langle f_k|$

$P^{B^{\prime}} = {\displaystyle\sum_{i, j, e, k}^{}} p_{ijek} \text{Tr}(\langle e_jG^{\dagger}||Ge_i\rangle) \otimes |f_e\rangle \langle f_k|$ (from the cyclicity of the trace)

$P^{B^{\prime}} = {\displaystyle\sum_{i, j, e, k}^{}} p_{ijek} \text{Tr}(\langle e_j |e_i\rangle) \otimes |f_e\rangle \langle f_k|$ (from the fact that $GG^{\dagger} = I$)

$P^{B^{\prime}} = P^B$





