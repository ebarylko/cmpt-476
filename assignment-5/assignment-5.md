## Question 1

### Part 1
$H^{\otimes n}\frac{1}{\sqrt{|S|}} {\displaystyle\sum_{s \in S}{} |x + s\rangle} = $
$\frac{1}{\sqrt{|S|}}{\displaystyle\sum_{s \in S}{} \frac{1}{\sqrt{2^n}} {\displaystyle\sum_{z \in \set{0, 1}^n}{} (-1)^{(x + s)z}|z\rangle}}$.

Taking the expression above, I can modify the order of the summations to obtain
$\frac{1}{\sqrt{2^n|S|}}{\displaystyle\sum_{z \in \set{0, 1}^n}{} } {\displaystyle\sum_{s \in S}{} (-1)^{(x + s)z}|z\rangle}$.
This expression can be further split into the $|z\rangle$ which are orthogonal to $|s\rangle$ and which are not 
orthogonal to $|s\rangle$.

Splitting the expression, we obtain
$\frac{1}{\sqrt{2^n|S|}}({\displaystyle\sum_{z \in s^{\perp}}{} } {\displaystyle\sum_{s \in S}{} (-1)^{(x + s)z}|z\rangle} + {\displaystyle\sum_{z \notin s^{\perp}}{} } {\displaystyle\sum_{s \in S}{} (-1)^{(x + s)z}|z\rangle})$.

In order to proceed further with this expression, I will need to prove that $\forall z \notin s^{\perp}$, $z·s = 0$ for half of the elements in $S$.

**Start of proof**:

We know that for every $s \in S$, it can be written as a linear combination of the basis vectors in $S$.

We can therefore express $z * s$ as $z a_1 t_1 + z a_2 t_2 + z a_3 t_3 + ... z a_n t_n$ for the n basis vectors of $S$, where 
the nth basis vector is denoted by $t_n$ and the coefficient for the nth basis vector is denoted by $a_n$.

If $z \notin s^{\perp}$, this means that $\exists t_x \in \set{t_i}, z * t_x = 1$.

Let us know define $S^{\prime}$ as $span \set{t_1, t_2 ... t_{x - 1}, t_{x + 1}, ... t_{n}}$. Knowing that no 
vector in $S^{\prime}$ contains $t_x$, we know that the sets $S^{\prime}$ and $S^{\prime} +t_x$ are disjoint.

Let us consider taking a vector $q \in S^{\prime}$, and compute the value of $q * z$. We will obtain that $z * q = c, c \in \set{0, 1}$.

If we now consider multiplying $(q + t_x)$ by $z$, we obtain $(q + t_x) * z = qz + qt_x = c + 1$.

Therefore, $\forall q \in S^{\prime}$, we can map $q \rightarrow q + t_x$, where $qz$ and $(q + t_x)z$ have differing dot products.
Since I am able to create a one to one mapping of the vectors with a dot product of 0 and a dot product of 1, I know that 
for half of the vectors $s \in S, s * z = 0$.

As a result of this, $\forall z \notin s^{\perp}$, $z·s = 0$ for half of the elements in $S$

**End of proof**.

Using what was proved above, I can state that $\forall z$, half the elements in $S$ are orthogonal to $z$. With this information, I know that the second 
summation in 
$\frac{1}{\sqrt{2^n|S|}}({\displaystyle\sum_{z \in s^{\perp}}{} } {\displaystyle\sum_{s \in S}{} (-1)^{(x + s)z}|z\rangle} + {\displaystyle\sum_{z \notin s^{\perp}}{} } {\displaystyle\sum_{s \in S}{} (-1)^{(x + s)z}|z\rangle})$
cancels out since I have an even number of $|z\rangle$ and $-|z\rangle$ states.

The expression above can now be modified to be 
$\frac{1}{\sqrt{2^n|S|}}{\displaystyle\sum_{z \in s^{\perp}}{} } {\displaystyle\sum_{s \in S}{} (-1)^{(x + s)z}|z\rangle}$.

Simplifying the expression further, it becomes
$\frac{1}{\sqrt{2^n|S|}}{\displaystyle\sum_{z \in s^{\perp}}{} } {\displaystyle\sum_{s \in S}{} (-1)^{xz}|z\rangle}$, which is equivalent to
$\frac{1}{\sqrt{2^n|S|}}{\displaystyle\sum_{z \in s^{\perp}}{} } (-1)^{xz}{\displaystyle\sum_{s \in S}{} |z\rangle}$.

Since we are repeatedly summing the $|z\rangle$ state $|S|$ times for each $|z\rangle \in Z$, we can factor out a multiple of 
$|S|$, obtaining $\frac{|S|}{\sqrt{2^n|S|}}{\displaystyle\sum_{z \in s^{\perp}}{}  (-1)^{xz}}$, which simplifies to
$\frac{\sqrt{|S|}}{\sqrt{2^n}}{\displaystyle\sum_{z \in s^{\perp}}{}  (-1)^{xz}|z\rangle}$

We have obtained the following by manipulating our original expression $H^{\otimes n}\frac{1}{\sqrt{|S|}} {\displaystyle\sum_{s \in S}{} |x + s\rangle}$. 

Consequently, we can conclude that  $H^{\otimes n}\frac{1}{\sqrt{|S|}} {\displaystyle\sum_{s \in S}{} |x + s\rangle} = \frac{\sqrt{|S|}}{\sqrt{2^n}}{\displaystyle\sum_{z \in s^{\perp}}{}  (-1)^{xz}|z\rangle}$
### Part 2

Simon's algorithm can be used to solve the boolean hidden subgroup problem since we 
can prepare a superposition of the n qubits, apply $U_f$, do a partial measurement of the second 
register, and then measure to get a basis vector orthogonal to s. We can repeat the previous steps 
until we have n - 1 basis vectors orthogonal to s. Once we have this, we can place all the basis vectors
we measured into a matrix $A$ and solve $As = 0$ to obtain what s is. Since we have found the 
basis vectors orthogonal to s and the value of s, we can say that these n vectors form a basis for 
$S$ since Dim(S) = Dim(span(s)) + Dim(Span($s^{\perp}$)).

Algorithm: 

A = {}
While less than n -1 linearly independent orthogonal vectors to s in A
    Prepare $(H^{\otimes n} \otimes I) |0\rangle^{\otimes (n + 1)}$
    Apply $U_f$ to the first n qubits
    Measure $f(x)$ in the second register
    Measure an orthogonal basis vector in the first register
    Add the basis vector measured to A

Solve the equation $As = 0$ to discover what s is, and have all the basis vectors in $S$.
    
    


## Question 2

### Compute the period of f (x) = 5^x mod 21 — that is, find the smallest integer r such that 5^r ≡ 1 mod 21

Computing the output of $f(x)$ for x $\in \{1, 2, 3, 4, 5, 6\}$, I have that 
$f(1) = 5, f(2) = 4, f(3) = 20, f(4) = 16, f(5) = 17, f(6) = 1$.

From this, I have that $r = 6$.

### Part 2
Using the value of r defined above, $5^{3} = 125$.

Computing the values of $GCD(125 - 1, 21)$ and $GCD(125 + 1, 21)$, they are 
1 and 21 respectively.

The problem with these values is that they are both trivial factors which do not tell
us about the prime factors of 21.

### Part 3
Using $f(x) = 2^x mod 21$, the period of the function is 6.

x = 1: f(x) = 2

x = 2: f(x) = 4

x = 3: f(x) = 8

x = 4: f(x) = 16

x = 5: f(x) = 11

x = 6: f(x) = 1

Computing the values of $GCD(2^3 - 1, 21)$ and $GCD(2^3 + 1, 21)$, they are 
7 and 3 respectively.

This tells me that the prime factors of 21 are 7 and 3.

## Question four

X = 

$$
\begin{bmatrix}
0 & 0 & 1 \\
1 & 0 & 0 \\
0 & 1 & 0 \\
\end{bmatrix}
$$

### Part 1

#### Showing X has an order of 3

$XXX$ = 

$$
\begin{bmatrix}
0 & 0 & 1 \\
1 & 0 & 0 \\
0 & 1 & 0 \\
\end{bmatrix} 
\begin{bmatrix}
0 & 0 & 1 \\
1 & 0 & 0 \\
0 & 1 & 0 \\
\end{bmatrix}
\begin{bmatrix}
0 & 0 & 1 \\
1 & 0 & 0 \\
0 & 1 & 0 \\
\end{bmatrix} 
$$

= 

$$
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
1 & 0 & 0 \\
\end{bmatrix} 
\begin{bmatrix}
0 & 0 & 1 \\
1 & 0 & 0 \\
0 & 1 & 0 \\
\end{bmatrix}
$$

= 

$$
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{bmatrix}
$$

#### Showing Z has an order of 3

$Z$ = 

$$
\begin{bmatrix}
1 & 0 & 0 \\
0 & {\omega}_3 & 0 \\
0 & 0 & {\omega}^2_3 \\
\end{bmatrix}
$$

$ZZZ$ 

= 

$$
\begin{bmatrix}
1 & 0 & 0 \\
0 & {\omega}_3 & 0 \\
0 & 0 & {\omega}^2_3 \\
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0 \\
0 & {\omega}_3 & 0 \\
0 & 0 & {\omega}^2_3 \\
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0 \\
0 & {\omega}_3 & 0 \\
0 & 0 & {\omega}^2_3 \\
\end{bmatrix}
$$

= 

$$
\begin{bmatrix}
1 & 0 & 0 \\
0 & ({\omega}_3)^2 & 0 \\
0 & 0 & ({\omega}^2_3)^2 \\
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0 \\
0 & {\omega}_3 & 0 \\
0 & 0 & {\omega}^2_3 \\
\end{bmatrix}
$$

= 

$$
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{bmatrix}
$$

### Part 2

$XZ$  =

$$
\begin{bmatrix}
0 & 0 & 1 \\
1 & 0 & 0 \\
0 & 1 & 0 \\
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0 \\
0 & {\omega}_3 & 0 \\
0 & 0 & {\omega}^2_3 \\
\end{bmatrix}
$$

= 

$$
\begin{bmatrix}
0 & 0 & {\omega}^2_3 \\
1 & 0 & 0 \\
0 & {\omega}_3 & 0 \\
\end{bmatrix}
$$
 
$ZX {\omega}^2_3$:

$$
\begin{bmatrix}
1 & 0 & 0 \\
0 & {\omega}_3 & 0 \\
0 & 0 & {\omega}^2_3 \\
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0 \\
0 & {\omega}_3 & 0 \\
0 & 0 & {\omega}^2_3 \\
\end{bmatrix}
\begin{bmatrix}
0 & 0 & 1 \\
1 & 0 & 0 \\
0 & 1 & 0 \\
\end{bmatrix} {\omega}^2_3
$$

= 


$$
\begin{bmatrix}
0 & 0 & 1 \\
{\omega}_3 & 0 & 0 \\
0 & {\omega}^2_3 & 0 \\
\end{bmatrix} {\omega}^2_3
$$

= 

$$
\begin{bmatrix}
0 & 0 & {\omega}^2_3 \\
1 & 0 & 0 \\
0 & {\omega}_3 & 0 \\
\end{bmatrix}
$$

I will now determine the value of k in 
$X^i Z^j = {\omega}^k Z^j X^i , i, j \in \set{0, 1, 2}$ by trying out different values of $i$ and $j$.

#### i = 0, j = 0

$X^0 Z^0 = {\omega}^k Z^0 X^0$, which simplifies to $I = {\omega}^k I$. For this to be true, $k = 0$.

#### i = 1, j = 0
$X^1 Z^0 = {\omega}^k Z^0 X^1$, which simplifies to 
$X = {\omega}^kX$. Multiplying by $X^{-1}$ on the left, we obtain
$X^{-1}(X = {\omega}^kX)$, which simplifies to $I =  {\omega}^k I$. For this to be true, $k = 0$.

### i = 0, j = 1

$X^0 Z^1 = {\omega}^k Z^1 X^0$, which simplifies to
$Z = {\omega}^k Z$. Multiplying by $Z^{-1}$ on the left, we obtain
$Z^{-1}(Z = {\omega}^kZ)$, which simplifies to $I =  {\omega}^k I$. For this to be true, $k = 0$.

### i = j = 1

$X^1 Z^1 = {\omega}^k Z^1 X^1$. Using the fact that
$XZ = {\omega}^2_3 Z X$, we know that $k = 2$.

### i = 1, j = 2

$X^1 Z^2 = {\omega}^k Z^2 X^1$, which simplifies to
${\omega}^2_3 ZX  Z = {\omega}^k Z^2 X^1$. Multiplying by $Z^{-1}$ on the left, we obtain
${\omega}^2_3 X  Z = {\omega}^k Z X^1$. Using the fact that
$XZ = {\omega}^2_3 Z X$, the expression  ${\omega}^2_3 X  Z = {\omega}^k Z X^1$ becomes
${\omega}^1_3 Z  X = {\omega}^k Z X^1$. Multiplying by ${Z}^-1$ on the left and ${X}^-1$ on the right, 
we obtain ${\omega}^1_3 = {\omega}^k$, meaning $k = 1$.

### i = 2, j = 1
$X^2 Z^1 = {\omega}^k Z^1 X^2$, which simplifies to
$X {\omega}^2_3 ZX = {\omega}^k Z^1 X^2$. Multiplying by $X^{-1}$ on the right, we obtain
${\omega}^2_3 XZ = {\omega}^k ZX$. Using the fact that
$XZ = {\omega}^2_3 Z X$, the expression  ${\omega}^2_3 XZ = {\omega}^k ZX$ becomes
${\omega}^1_3 Z  X = {\omega}^k Z X$. Multiplying by ${Z}^-1$ on the left and ${X}^-1$ on the right,
we obtain ${\omega}^1_3 = {\omega}^k$, meaning $k = 1$.

### i = 0, j = 2

$Z^2 = {\omega}^k Z^2$, multiplying by $Z^{-2}$ on the left, we obtain 
$I = {\omega}^k I$, which means that $k = 0$.

### i = 2, j = 0

$X^2 = {\omega}^k X^2$, multiplying by $X^{-2}$ on the left, we obtain
$I = {\omega}^k I$, which means that $k = 0$.

### i = j = 2
$X^2 Z^2 = {\omega}^k Z^2 X^2$, which simplifies to
$X {\omega}^2_3 ZX Z = {\omega}^k Z^2 X^2$. Simplifying the expression further, we obtain
$X {\omega}^2_3 ZZ X = {\omega}^k Z^2 X^2$. Multiplying by $X^{-1}$ on the right, we obtain
$X {\omega}^2_3 ZZ  = {\omega}^k Z^2 X$, which simplifies to 
$Z {\omega}^2_3 XZ  = {\omega}^k Z^2 X$. Multiplying by $Z^{-1}$ on the right, we obtain
${\omega}^2_3 XZ  = {\omega}^k ZX$, which 
further simplifies to ${\omega}^2_3 ZX  = {\omega}^k ZX$. 

Review this step.

For this to be true, we need $k = 2$.

Using the data obtained for different values of $i, j$, I obtain that 
$k = 2 * i * j \mod 3$.

### Part 3

$H$ 

=

$$ \frac{1}{\sqrt{3}}
\begin{bmatrix}
1 & 1 & 1 \\
1 & {\omega}_3 & {\omega}^2_3 \\
1 & {\omega}^2_3 & {\omega}_3 \\
\end{bmatrix}
$$

$H^{\dagger}$ 

=

$$ \frac{1}{\sqrt{3}}
\begin{bmatrix}
1 & 1 & 1 \\
1 & {\omega}^2_3 & {\omega}_3 \\
1 & {\omega}_3 & {\omega}^2_3 \\
\end{bmatrix}
$$

$H^{\dagger}ZH$

$$ \frac{1}{3}
\begin{bmatrix}
1 & 1 & 1 \\
1 & {\omega}^2_3 & {\omega}_3 \\
1 & {\omega}_3 & {\omega}^2_3 \\
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0 \\
0 & {\omega}_3 & 0 \\
0 & 0 & {\omega}^2_3 \\
\end{bmatrix}
\begin{bmatrix}
1 & 1 & 1 \\
1 & {\omega}_3 & {\omega}^2_3 \\
1 & {\omega}^2_3 & {\omega}_3 \\
\end{bmatrix}
$$

=

$$ \frac{1}{3}
\begin{bmatrix}
1 & {\omega}_3 & {\omega}^2_3 \\
1 & 1 & 1 \\
1 & {\omega}^2_3 & {\omega}_3 \\
\end{bmatrix}
\begin{bmatrix}
1 & 1 & 1 \\
1 & {\omega}_3 & {\omega}^2_3 \\
1 & {\omega}^2_3 & {\omega}_3 \\
\end{bmatrix}
$$

=

$$ \frac{1}{3}
\begin{bmatrix}
1 +  {\omega}_3 + {\omega}^2_3 & 1 +  {\omega}_3 + {\omega}^2_3  & 3 \\
3 & 1 +  {\omega}_3 + {\omega}^2_3  & 1 +  {\omega}_3 + {\omega}^2_3  \\
1 +  {\omega}_3 + {\omega}^2_3   & 3 & 1 +  {\omega}_3 + {\omega}^2_3    \\
\end{bmatrix}
$$

Using the fact that the sum of the nth roots of unity is 0, the above matrix becomes

$$
\begin{bmatrix}
0 & 0 & 1 \\
1 & 0 & 0 \\
0 & 1 & 0 \\
\end{bmatrix}
$$

We can note that the simplified matrix above is equivalent to $X$, showing that 
$H^{\dagger}ZH = X$.

### Part 4

Knowing that $X = HZH^{\dagger}$ in the qubit case, we know that
the eigenvalues of $X$ are the values along the diagonal of $Z$, being 
$1, {\omega}_3,$ and ${\omega}^2_3$.

The unit eigenvectors corresponding to these eigenvalues are 
$$
\begin{bmatrix}
1 \\
1 \\
1 \\
\end{bmatrix},
\begin{bmatrix}
1 \\
{\omega}_3 \\
{\omega}^2_3 \\
\end{bmatrix}
, \text{and}

\begin{bmatrix}
1 \\
{\omega}^2_3 \\
{\omega}_3 \\
\end{bmatrix},
\text{respectively}
$$ 

[//]: # (,)

[//]: # ()
[//]: # ($$)

[//]: # (\begin{bmatrix})

[//]: # (1 \\)

[//]: # ({\omega}_3 \\)

[//]: # ({\omega}^2_3 \\)

[//]: # (\end{bmatrix})

[//]: # (, \text{and})

[//]: # ($$)

[//]: # ()
[//]: # ()
[//]: # ($$)

[//]: # (\begin{bmatrix})

[//]: # (1 \\)

[//]: # ({\omega}^2_3 \\)

[//]: # ({\omega}_3 \\)

[//]: # (\end{bmatrix},)

[//]: # (\text{respectively})

[//]: # ($$)

## Question six

### Part 1

#### Using the fact about non-zero amplitudes to prove the other fact

In this superposition,
${\displaystyle\sum_{x \in \{0, 1\}^n}{}} {\displaystyle\sum_{y \in \{0, 1\}}{}} (-1)^{y(1 \oplus \phi (x))}|x \rangle$, 
the only way that $|x\rangle$ has a non-zero amplitude is if for different values of y, $(-1)^{y(1 \oplus \phi (x))}|x \rangle$ 
does not destructively interfere. 

In order to have constructive interference, we need that $y_1(1 \oplus \phi (x)) = y_2(1 \oplus \phi (x)), y_1 = 0, y_2 = 1$.
Expanding out the expression above, we have that $0 = 1 \oplus \phi (x)$. The only way this equation holds is if 
$\phi (x) = 1$. 

#### Using the value of the function to prove that the state has a non-zero amplitude

If $\phi (x) = 1$, substituting this value in the expression   
${\displaystyle\sum_{x \in \{0, 1\}^n}{}} {\displaystyle\sum_{y \in \{0, 1\}}{}} (-1)^{y(1 \oplus \phi (x))}|x \rangle$ 
yields 
${\displaystyle\sum_{x \in \{0, 1\}^n}{}} {\displaystyle\sum_{y \in \{0, 1\}}{}} (-1)^{y(1 \oplus 1)}|x \rangle$, which 
is equivalent to
${\displaystyle\sum_{x \in \{0, 1\}^n}{}} {\displaystyle\sum_{y \in \{0, 1\}}{}} (-1)^{y(0)}|x \rangle$, which further 
simplifies to
${\displaystyle\sum_{x \in \{0, 1\}^n}{}} {\displaystyle\sum_{y \in \{0, 1\}}{}} |x \rangle$.

As a result of $\phi (x)$ taking on a specific value, each basis state has a non-zero probability of occurring.


### Part 2
The transformation on the right hand side is not a unit vector for every value of $\phi (x)$.

If $\phi (x) = 0$, then the superposition simplifies to
$\frac{1}{2 \sqrt{2^n}}{\displaystyle\sum_{x \in \{0, 1\}^n}{}} {\displaystyle\sum_{y \in \{0, 1\}}{}} (-1)^{y(1 \oplus 0)}|x \rangle$, which
is equivalent to 
$\frac{1}{2 \sqrt{2^n}}{\displaystyle\sum_{x \in \{0, 1\}^n}{}} {\displaystyle\sum_{y \in \{0, 1\}}{}} (-1)^{y}|x \rangle$.

Expanding out the last line to explicitly show the values that $(-1)^{y}|x \rangle$ can take on, we see that it becomes
$\frac{1}{2 \sqrt{2^n}}{\displaystyle\sum_{x \in \{0, 1\}^n}{}}  (-1)^{1}|x \rangle + (-1)^{0}|x \rangle $.

For any computational basis state $|x\rangle$, we will sum $(-1)^0|x\rangle$ and $(-1)^{-1}|x\rangle$, having the 
basis state removed due to destructive interference.

Since this occurs for all basis states, our superposition of states will sum to zero. As a result of this, we will have
that the superposition is not a unit vector since its length is not 1.

### Part 3

In the expression $\frac{1}{2 \sqrt{2^n}}{\displaystyle\sum_{x \in \{0, 1\}^n}{}} {\displaystyle\sum_{y \in \{0, 1\}}{}} (-1)^{y(1 \oplus \phi (x))}|xy\rangle$, 
having $phi (x) = 0$ does not generate destructive interference.
For $phi (x) = 0$, the transformation becomes $\frac{1}{2 \sqrt{2^n}}{\displaystyle\sum_{x \in \{0, 1\}^n}{}} {\displaystyle\sum_{y \in \{0, 1\}}{}} (-1)^{y}|xy\rangle$.

Since the state $|x0\rangle$ is distinct from $-|x1\rangle$, none of the states get removed. As a result of this, the superposition obtained 
is unitary.

However, for $phi (x) = 1$ or $phi (x) = 0$, we will receive no destructive interference (though we will obtain a relative phase difference), 
not allowing us to determine the value of $\phi (x)$ from whether there is a simulation or not.

### Part 4
If an efficient quantum algorithm for SAT was easily discoverable, it would have been discovered decades ago. Since it has not been 
discovered yet, that either means that the algorithm is complex or that the methods used to approach the problem must change.




