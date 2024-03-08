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
$||U_2 - V_2|| = E(U_2, V_2)