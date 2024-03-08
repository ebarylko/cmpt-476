## Question 1
### Prove that approximation error is subadditive — that is, show that for any gates U1 , U2 , V1 , V2 , E(U2U1, V2V1) ≤ E(U2, V2) + E(U1, V1) You may use without proof two facts: the triangle inequality ||A + B|| ≤ ||A|| + ||B|| and ||UA|| = ||A|| = ||AU|| for any unitary U and complex valued matrix A.

Given my initial state $E(U_2U_1, V_2V_1) = ||U_2U_1 - V_2V_1||$, I can express the last expression 
as $||U_2U_1 + (-V_2V_1)||$.

I can modify the expression further to be $||(U_2U_1 - V_2U_1) + (V_2U_1 -V_2V_1)||$.
I can apply the triangle inequality and say that $||(U_2U_1 - V_2U_1) + (V_2U_1 -V_2V_1)|| \le$
$||(U_2U_1 - V_2U_1)|| + ||(V_2U_1 -V_2V_1)||$.

In order to prove that approximation error is subadditive, I must convert
$||(U_2U_1 - V_2U_1)|| + ||(V_2U_1 -V_2V_1)||$ to
$||U_2 - V_2|| + ||U_1 - V_1||$.

I can manipulate $||U_2U_1 - V_2U_1||$ by noting that it is equivalent to
$||(U_2 - V_2)U_1||$. If I let $(U_2 - V_2) = A$ and $U_1 = U$, then I can apply the fact
that ||UA|| = ||A|| = ||AU|| to obtain that $||(U_2 - V_2)U_1|| = ||U_2 - V_2|| = E(U_2, V_2)$

I can apply a similar procedure to manipulate $||(V_2U_1 -V_2V_1)||$. Noting that
$||V_2U_1 -V_2V_1|| = ||V_2(U_1 -V_1)||$, I can let $(U_1 -V_1) = A$ and $V_2 = U$ and 
apply the fact I used previously. Doing that results in  $||(V_2U_1 -V_2V_1)||$ being equal to
$||U_1 - V_1|| = E(U_1, V_1)$.

Using the work in the two sections above, we can say that 
$||(U_2U_1 - V_2U_1)|| + ||(V_2U_1 -V_2V_1)|| = E(U_2, V_2) + E(U_1, V_1)$.
Knowing this, we can substitute the new value of $||(U_2U_1 - V_2U_1)|| + ||(V_2U_1 -V_2V_1)||$
into the expression $||(U_2U_1 - V_2U_1) + (V_2U_1 -V_2V_1)|| \le$
$||(U_2U_1 - V_2U_1)|| + ||(V_2U_1 -V_2V_1)||$, obtaining
$||(U_2U_1 - V_2U_1) + (V_2U_1 -V_2V_1)|| \le  E(U_2, V_2) + E(U_1, V_1)$.

### Suppose you have a circuit U1 · · · Uk consisting of k gates and you wish to approximate over some particular gate set to an error of ε. What approximation factor should you choose for each gate?

Using what we just proved above, we know that the error of approximating the k gates is bounded 
by the expression $E(U_1, V_1) + E(U_2, V_2) + .... + E(U_k, V_k)$. For the preceding expression to
be less than or equal to $\epsilon$, we must have the error in each gate be $x$, where $x \le \frac{\epsilon}{k}$.
In the scenario where $x = \frac{\epsilon}{k}$, the sum of all the approximation errors is $\epsilon$. For 
other values of $x$, the sum of the approximation errors is smaller.

## Question two

### Part 1
|0⟩⟨0| ⊗ I + |1⟩⟨1| ⊗ U

Let $t, r$ be two arbitrary qubits where $t = a|0\rangle + b|1\rangle$, r = c|0\rangle + d|1\rangle$, $a, b, c, d \in \mathbb{c}$.

$|tr\rangle = ac|00\rangle + ad|01\rangle + bc|10\rangle + bd|11\rangle$.

Applying (|0⟩⟨0| ⊗ I + |1⟩⟨1| ⊗ U) to $|tr\rangle$, we obtain
(|0⟩⟨0| ⊗ I + |1⟩⟨1| ⊗ U)($ac|00\rangle + ad|01\rangle + bc|10\rangle + bd|11\rangle$). 
After applying |0⟩⟨0| ⊗ I + |1⟩⟨1| ⊗ U to each term, we obtain
$ac|00\rangle + ad|01\rangle + bc|1(U|0\rangle)\rangle + bd|1(U|1\rangle)\rangle$.

This proves that |0⟩⟨0| ⊗ I + |1⟩⟨1| ⊗ U functions as a controlled U gate for any arbitrary two 
qubits.

### Part 2

The circuit in matrix form would be $|0\rangle \langle 0| \otimes I \otimes I$
+ $|1\rangle \langle 1| \otimes I \otimes H$

## Question three


### Gate controlled on a measurement

Let $t, r$ be two arbitrary qubits where $t = a|0\rangle + b|1\rangle$, r = c|0\rangle + d|1\rangle$, $a, b, c, d \in \mathbb{c}$.

Let us have $t$ be the control bit and $r$ be the target bit.

We measure $|0\rangle$ in the control bit with a probability of $a^2$. Since we do not apply the 
$U$ gate, the joint state of $t$ and $r$ is $ac|00\rangle + ad|01\rangle$

We measure $|1\rangle$ in the control bit with a probability of $b^2$. Since we do apply the
$U$ gate, the joint state of $t$ and $r$ is $bc|1(U|1\rangle)\rangle + bd|1(U|0\rangle)\rangle$

### Quantum controlled gate 
Let $t, r$ be two arbitrary qubits where $t = a|0\rangle + b|1\rangle$, r = c|0\rangle + d|1\rangle$, $a, b, c, d \in \mathbb{c}$.

Let us have $t$ be the control bit and $r$ be the target bit.

The joint state of $r$ and $t$ is $ac|00\rangle + ad|01\rangle + bc|10\rangle + bd|11\rangle$.

After applying the $c-U$ gate, the joint state of $r$ and $t$ is
$ac|00\rangle + ad|01\rangle + bc|1(U|0\rangle)\rangle + bd|1(U|1\rangle)\rangle$ 
= $a|0\rangle(c|0\rangle) + d|1\rangle) + b|1\rangle(cU|0\rangle + dU|1\rangle)$

If we now measure $t$ in the classical basis, we obtain
$a|0\rangle(c|0\rangle) + d|1\rangle)$ with probability $|a|^2|(|c|^2 + |d|^2) = |a|^2$  
(since we are given that $|c|^2 + |d|^2 = 1$ from the fact that r is an arbitrary qubit) and
$b|1\rangle(cU|0\rangle + dU|1\rangle)$ with probability $|b|^2(|c|^2 + |d|^2) = |b|^2$.


If we compare the measurement results of the quantum controlled and classically controlled gate, 
we notice that they match. 

Therefore, every gate controlled on a measurement outcome is equivalent to a quantum 
controlled gate followed by a measurement.



