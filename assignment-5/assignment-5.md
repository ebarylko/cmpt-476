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

In order to proceed further with this expression, I will need to prove that $\forall z$, $z·s = 0$ for half of the elements in $S$.

**Start of proof**:

We know that for every $s \in S$, it can be written as a linear combination of the basis vectors in $S$.

We can therefore express $z * s$ as $z a_1 t_1 + z a_2 t_2 + z a_3 t_3 + ... z a_n t_n$ for the n basis vectors of $S$, where 
the nth basis vector is denoted by $t_n$ and the coefficient for the nth basis vector is denoted by $a_n$.

If we wish for $z * s = 0$, we need an even number of terms in $z * s$ to have a value of 1. 

Counting all the number of ways to select an even number of terms in $s * z$, it is equivalent to $\displaystyle\sum_{i \in \mathbb{N^{even}}}{} \binom{n}{i}$. 

Using the binomial theorem, we know that $(1 + x)^n = \displaystyle\sum_{k = 0}{n} \binom{n}{k} x^k$ and $(1 - x)^n = \displaystyle\sum_{k = 0}{n}  \binom{n}{k}(-1)^k x^k$, respectively.

Summing $(1 + x)^n$ and $(1 - x)^n$, we obtain $2 \displaystyle\sum_{k \in \mathbb{N^{even}}}{} \binom{n}{k}x^k$.

If we set $x = 1$, we obtain that $(1 + 1)^n + (1 - 1)^n = 2 \displaystyle\sum_{k \in \mathbb{N^{even}}}{} \binom{n}{k}$, which is equivalent to 
$2^n = 2 \displaystyle\sum_{k \in \mathbb{N^{even}}}{} \binom{n}{k}$. Dividing by 2, we obtain that
$\displaystyle\sum_{k \in \mathbb{N^{even}}}{} \binom{n}{k} = 2^{n - 1}$.

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
0 & {{\omega}_3}^2 & 0 \\
0 & 0 & {{\omega}^2_3}^2 \\
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




