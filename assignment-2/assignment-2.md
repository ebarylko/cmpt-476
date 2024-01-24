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

Do I start in the $|0\rangle$ state?

I have a state constructed out of a linear combination of $A$ and $B$, which are lienar combinations of the $|0\rangle$ or $|1\rangle$.
We are measuring in the computational basis, so we snap out of the basis $\beta$.
Now, we are either in the $|0\rangle$ or $|1\rangle$ state. 



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