## Question 2
$\psi$ = $\frac{1}{\sqrt{3}}|0\rangle + \frac{i}{\sqrt{3}}|1\rangle - \frac{1}{\sqrt{3}}|2\rangle$

$\phi$ = $\frac{1}{\sqrt{2}}|1\rangle - \frac{i}{\sqrt{2}}|2\rangle$

### Give the explicit column vectors of |ψ⟩ and |φ⟩


$$ |\psi\rangle =  \frac{1}{\sqrt{3}}\begin{bmatrix}
1 \\
i \\
-1 \\
\end{bmatrix} $$

$$ |\phi\rangle =  \frac{1}{\sqrt{2}}\begin{bmatrix}
0 \\
1 \\
-i \\
\end{bmatrix} $$ 


### Calculate the following:

$\langle\psi|\psi\rangle$:

$$\langle\psi| = \frac{1}{\sqrt{3}}\begin{bmatrix}
1 -i -1
\end{bmatrix} $$

$\langle\psi|\psi\rangle$ 

= 

$$\frac{1}{\sqrt{3}}\begin{bmatrix}
1 -i -1
\end{bmatrix} 
\frac{1}{\sqrt{3}}\begin{bmatrix}
1 \\
i \\
-1 \\
\end{bmatrix}
$$

= 1

$\langle\phi|\phi\rangle$:

$$ \langle\phi| =  \frac{1}{\sqrt{2}}\begin{bmatrix}
0  & 1 & i
\end{bmatrix} $$ 

$\langle\phi|\phi\rangle$

$$ = \frac{1}{\sqrt{2}}\begin{bmatrix}
0 & 1 & i
\end{bmatrix}
\frac{1}{\sqrt{2}}\begin{bmatrix}
0 \\
1 \\
-i \\
\end{bmatrix} $$

= 1

$\langle\psi|\phi\rangle$:


$$\frac{1}{\sqrt{3}}\begin{bmatrix}
1 -i -1
\end{bmatrix}
\frac{1}{\sqrt{2}}\begin{bmatrix}
0 \\
1 \\
-i \\
\end{bmatrix} $$

= 0

$|\psi\rangle\langle\phi$:

$$ |\psi\rangle =  \frac{1}{\sqrt{3}}\begin{bmatrix}
1 \\
i \\
-1 \\
\end{bmatrix}
\frac{1}{\sqrt{2}}\begin{bmatrix}
0 & 1 & -i
\end{bmatrix} $$ 



=

$$ \frac{1}{\sqrt{6}}\begin{bmatrix}
0 & 1 & -i \\
0 & i &  1 \\
0 & -1 &  i \\
\end{bmatrix} $$


$|\phi\rangle \otimes \psi\rangle$:

$|\phi\rangle \otimes \psi\rangle$

=

$$
\frac{1}{\sqrt{3}}\begin{bmatrix}
1 \\
i \\
-1 \\
\end{bmatrix} \otimes
\frac{1}{\sqrt{2}}\begin{bmatrix}
0 \\
1 \\
-i \\
\end{bmatrix}
$$

=

$$ \frac{1}{\sqrt{6}}\begin{bmatrix}
0 \\
1 \\
-i \\
0 \\
i \\
1 \\
0 \\
-1 \\
i \\
\end{bmatrix} $$


#### Is the vector |ψ⟩ + |φ⟩ a unit vector? If not, normalize it to get a unit vector.

Let $|T\rangle = \psi\rangle + \phi\rangle$


=


$$ \frac{1}{\sqrt{3}}\begin{bmatrix}
1 \\
i \\
-1 \\
\end{bmatrix} +
\frac{1}{\sqrt{2}}\begin{bmatrix}
0 \\
1 \\
-i \\
\end{bmatrix} $$  


= 

$\frac{1}{\sqrt{3}}|0\rangle + (\frac{i}{\sqrt{3}} + \frac{1}{\sqrt{2}})|2\rangle + (-\frac{1}{\sqrt{3}} - \frac{i}{\sqrt{2}})|2\rangle$

$|||T\rangle|| = \sqrt{(\frac{1}{\sqrt{3}})^2 + (\frac{i}{\sqrt{3}} + \frac{1}{\sqrt{2}})^2 + (-\frac{1}{\sqrt{3}} - \frac{i}{\sqrt{2}})^2}$

= $\sqrt{\frac{1}{3} + (\frac{i}{\sqrt{3}} + \frac{1}{\sqrt{2}})(-\frac{i}{\sqrt{3}} + \frac{1}{\sqrt{2}}) + (-\frac{1}{\sqrt{3}} - \frac{i}{\sqrt{2}})(-\frac{1}{\sqrt{3}} + \frac{i}{\sqrt{2}})}$  

= $\sqrt{\frac{1}{3} + \frac{1}{2} + \frac{1}{3} + \frac{1}{3} + \frac{1}{2}}$ 

= $\sqrt{2}$

$|T\rangle$ is not a unit vector since the length is not one. To make $|T\rangle$ a unit vector, we must divide it by $\sqrt{2}$

$|T^{\prime}\rangle =  \frac{1}{\sqrt{2}}|T\rangle$  

=  
$\frac{1}{\sqrt{6}}|0\rangle + (\frac{i}{\sqrt{6}} + \frac{1}{2})|1\rangle + (-\frac{1}{\sqrt{6}} - \frac{i}{2})|2\rangle$


## Question 3

### Calculate the probabilities of receiving result “0” or “1” if the qubit is measured.

Let $|q\rangle = \frac{1}{\sqrt{2}}|0\rangle + \frac{e^{i\theta}}{\sqrt{2}}|1\rangle$  

The probability of measuring $|0\rangle$ or $|1\rangle$ is $(\frac{1}{\sqrt{2}})^2 + (\frac{e^{i\theta}}{\sqrt{2}})^2$  

= $\frac{1}{2} + (\frac{e^{i\theta}}{\sqrt{2}} * \frac{e^{-i\theta}}{\sqrt{2}})$    

= $\frac{1}{2}  + \frac{1}{2}$  

= 1

The probabilities of receiving result “0” or “1” if the qubit is measured is 1.


### If we first apply the Hadamard gate to the initial state 1 |0⟩ + eiθ |1⟩ and then measure, what are the probabilities of receiving the “0” and “1” results as an function of θ?

$$ \frac{1}{\sqrt{2}}\begin{bmatrix}
1 & 1 \\
1 & -1 \\
\end{bmatrix}|q\rangle
$$  


=

$$ \frac{1}{\sqrt{2}}\begin{bmatrix}
1 \\
1 \\
\end{bmatrix} +
\frac{e^{i\theta}}{\sqrt{2}}\begin{bmatrix}
1 \\
-1 \\
\end{bmatrix} 
$$  

=
$\frac{1}{2}(|0\rangle + |1\rangle) + \frac{e^{i\theta}}{\sqrt{2}}(|0\rangle - |1\rangle)$

= $(\frac{1}{2} + \frac{e^{i\theta}}{\sqrt{2}})|0\rangle + (\frac{1}{2} - \frac{e^{i\theta}}{\sqrt{2}})|1\rangle$ 

Let $\alpha = (\frac{1}{2} + \frac{e^{i\theta}}{\sqrt{2}}), \beta = (\frac{1}{2} - \frac{e^{i\theta}}{\sqrt{2}})$

$\alpha^2 = \frac{1}{4}(1 + \frac{e^{i\theta}}{\sqrt{2}})(1 + \frac{e^{-i\theta}}{\sqrt{2}})$  

= $\frac{1}{4}(1 + e^{i\theta} + e^{-i\theta} + 1)$  

Using the identity $e^{i\theta} = cos(\theta) + isin(\theta)$  

$\frac{1}{4}(1 + e^{i\theta} + e^{-i\theta} + 1)$    


= $\frac{1}{4}(1 + cos(\theta) + isin(\theta) + cos(\theta) -isin(\theta) + 1)$     


= $\frac{1}{4}(2 + 2cos(\theta)) = \frac{1 + cos(\theta)}{2}

$\alpha^2 = \frac{1 + cos(\theta)}{2}$

$\beta^2 = \frac{1}{4}(1 - \frac{e^{i\theta}}{\sqrt{2}})(1 - \frac{e^{-i\theta}}{\sqrt{2}})$    

= $\frac{1}{4}(1 - e^{i\theta} - e^{-i\theta} + 1)$    

= $\frac{1}{4}(2 - (e^{i\theta} + e^{-i\theta}))$    

Using the equivalency $e^{i\theta} + e^{-i\theta} = 2cos(\theta)$,

$\frac{1}{4}(2 - (e^{i\theta} + e^{-i\theta}))$    

$\frac{1}{4}(2 - cos(\theta))$      

= $\frac{1 - cos(\theta)}{2}$
