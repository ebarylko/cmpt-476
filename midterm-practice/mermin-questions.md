## Prove that the swap gate is composed of three CNOT gates

Let $S$ be the swap gate. 

The $S$ gate is defined to have the following behavior, $S|xy\rangle = |yx\rangle, x, y \in (0, 1)$.

To achieve this effect, we can start off by applying a $CNOT$ gate to $|xy\rangle$, 
obtaining $|x (x \oplus y)\rangle$.

We can then apply a $CNOT$ with the second bit being the control bit and obtain
$|(x \oplus (x \oplus y)) (x \oplus y)\rangle$, which is equivalent to
$|((x \oplus x) \oplus y) (x \oplus y)\rangle$ due to the XOR operator being associative, which 
is the same as $|(0 \oplus y) (x \oplus y)\rangle$, which simplifies to
$|y (x \oplus y)\rangle$

By applying a third $CNOT$ with the first bit being the control bit, we obtain
$|y ((x \oplus y) \oplus y)\rangle$ which simplifies to
$|y (x \oplus (y \oplus y))\rangle$ which is equal to
$|y x\rangle$.

Therefore, the swap gate can be implemented using three $CNOT$ gates.
