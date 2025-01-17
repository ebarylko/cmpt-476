Universality:   
* A gate set is universal (for classical computing) if $\forall n, m > 0$, any circuit can be constructed out of these gates

Correlated:
* A distribution is correlated if it cannot be written as the tensor product of two other states. it is Separable otherwise
* Similar to entanglement

Probability vector: 
* A vector where all the probabilities in the vector sum to 1
* Each probability is non-negative

Hermitian conjugate:
* Take the conjugate of the vector and then take the complex conjugate of each entry

Unitary:
* Hermitian conjugate is equal to its inverse
* Norm preserving

Projectors:
* An operator P with the property that $P^2$ = P pf

Partial measurement:
* Only measure and keep the states which have a qubit in the position you are looking at
* Normalize the resulting vector so it becomes a unit vector

Local operations:
* Measurements or operations done to a single qubit

Projective measurements: 
* Send a state $|\psi\rangle$ to $\frac{P_i|\psi\rangle}{\sqrt{p(i)}}$, where $p(i) = \langle\psi|P_i|\psi\rangle$

Hermitian:
* An operator p where $p^{\dagger} = p^{-1} = p$

Density matrix:
* Alternate representation of a mixed state
* All entries along the diagonal sum to 1
* Defined as $p = {\displaystyle\sum_{i}^{}} p_i|\theta_i\rangle\langle\theta_i|$
* Applying a unitary $U$ on the density matrix sends p to $UpU^{\dagger}$

Cyclicity of the trace:
* $Tr(ABC) = Tr(CAB) = Tr(BCA)$


Reduced density operations:
* Local unitaries do not change the reduced density matrix.
* $P^{AB} = {\displaystyle\sum_{i, j, e, k}^{}} p_{ijek} |e_i\rangle\langle e_j| \otimes |f_e\rangle \langle f_k|$
* $P^B = {\displaystyle\sum_{i, j, e, k}^{}} p_{ijek} \text{Tr}(|e_i\rangle\langle e_j|) \otimes |f_e\rangle \langle f_k|$
* We can choose any basis to write the denisty matrix in

![Partial trace of a matrix](midterm-study-guide.jpeg)

No Communication Theorem:
* If Alice and Bob share an entangled state, a local unitary applied on Alice's/Bob's qubit does not affect the reduced density matrix of the other person

Rotations:
* You can simulate any rotation through three rotations over two non-parallel axes.

* If you are rotating a point by $\pi$, in the bloch sphere you end up rotating by $2\pi$.
* You can obtain the antipodal point to any point by taking the same state, placing it at $\pi - \theta$, and then rotating by a degree of $\pi$ degrees around the z-axis. 
* That is why if you had $sin(\frac{\theta}{2})$, the antipodal point would be $sin(\frac{\pi - \theta}{2})$


Bell basis:
* a basis where all the basis vectors are entangled
* Each basis vector is a bell state

Superdense coding:
* The ability to send two bits of information by only sending one bit
* Put example of how this is done using measurements in the Bell basis.
* Note: local operations on one qubit do not change the reduced density matrix of the other, but they change the joint state

No cloning theorem:
* You cannot copy a qubit
* There exists no unitary $U$ such that $U|\psi 0\rangle = |\psi \psi\rangle$
* Put down proof

Holevo's theorem:
* You cannot obtain more than one bit of information from a qubit.

Entanglement swapping: 
* You can entangle two qubits without them physically interacting with each other
* You take two entangled states, entangle one part of the first state with another part of the second state, and then you can entangle a portion of the first state with another part of the second state that never interacted together

Complexity classes:
* P: problem can be solved in polynomial time
* NP: problems whose solution can be verified in polynomial time
* EXPTIME: problems with an exponential algorithm
* PSPACE: problems with polynomial space algorithm

Uniform circuit family: 
*  a collection of gates $\set{C_n | n \in \mathbb{N}}$, where the gates can be made in polynomial time

Measuring complexity in a circuit:
* Width: number of wires. Gives space complexity
* Depth: number of time slices. Gives time complexity

Spectral theorem: 
* A normal operator P has the following property: $AA^{\dagger} = A^{\dagger}A$
* For the following, $P$ is unitary and has the unit eigenvectors of A. $\land$ is diagonal as a matrix and encodes the eigenvalues of A.
* Every normal operator A can be written as $A = P\landP^{\dagger}

Euler angle decomposition:
* Any rotation in 3d space can be composed of three rotations in two planes

Approximate universality:
* Any circuit can be approximated to some error $\le \epsilon$, where $\epsilon > 0$.