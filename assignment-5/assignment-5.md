## Question 1

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

## Question six

### Part 1
In this superposition,
${\displaystyle\sum_{x \in \{0, 1\}^n}{}} {\displaystyle\sum_{y \in \{0, 1\}}{}} (-1)^{y(1 \oplus \phi (x))}|x \rangle$, 
the only way that $|x\rangle$ has a non-zero amplitude is if for different values of y, $(-1)^{y(1 \oplus \phi (x))}|x \rangle$ 
does not destructively interfere. 

In order to have constructive interference, we need that $y_1(1 \oplus \phi (x)) = y_2(1 \oplus \phi (x)), y_1 = 0, y_2 = 1$.
Expanding out the expression above, we have that $0 = 1 \oplus \phi (x)$. The only way this equation holds is if 
$\phi (x) = 1$. 
