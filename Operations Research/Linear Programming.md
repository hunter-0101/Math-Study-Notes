The **canonical form** of **linear programming (LP)** is $$\begin{array}{l}\max& c^Tx\\\text{s.t.}&Ax\le b\\&x\ge0\end{array}$$Where $x\in\mathbb R^n$ and $A,b,c$ are of proper sizes. Any LP problem can be made into the above form via substitution and replacing $A'x'=b'$ with $A'x'\le b',-A'x'\le -b'$.
- **Standard form**: while some authors defined the **standard form** the same as canonical form, some other authors define the standard form as a minimizer problem consisting of only equivalence relations: $$\begin{array}{l}\min& c^Tx\\\text{s.t.}&Ax= b\\&x\ge0\end{array}$$To turn a general LP into such form, we need to introduce **slack variables** an inequality can be made into an equality via **slack variable**: $$x_1+x_2\ge2\quad\iff\quad x_1+x_2-s_1=2,s_3\ge0$$A free variable $x_3$ can be replaced by two slack variables $x_3=s_2-s_3,s_2,s_3\ge0$.
	- **Discussion on $b$**: it's usually a good practice to keep $b\ge0$. This ensures that the solution obtained via simplex tableau is directly feasible.
- **Feasible region**: feasible region $D$ refers to the region in $\mathbb R^n$ in which the conditions in an LP problem is satisfied, whose elements are called **feasible solutions**. It's always a **convex polytope** ([[Convexity]]) since it's the intersection of half spaces. 
- **Optimal solution**: the solution to the LP problem is called the optimal solution.
	- **Vertex property**: the optimal solution, when exists, must be achieved at some vertex of the polytope. This is obvious since by linearity we always have $$c^Tx=\frac{1}{2}\left(c^T(x+\varepsilon\vec r)+c^T(x-\varepsilon \vec r)\right),\quad\forall x,x\pm\varepsilon\vec r\in D$$Here $\varepsilon>0$ is assumed to be small enough.
## The simplex method
A LP problem in standard form can be represented as $$\begin{bmatrix}1&-c^T&0\\0&A&b\end{bmatrix}$$where the first row specify the objective function, and the remaining rows keep track of the constraints.
1. **Initialization (Choose a Basis)**: we select a set $I_B \subset[n]$ of $m$ linearly independent columns of $A$, called the **basis**. The variables are partitioned into $x_B$ (**basic variables**) and $x_N$ (**nonbasic variables**). Now we set $x_N = 0$ and solve $A_B x_B = b$. To this point we're having $$x_B+B^{-1}Nx_N=B^{-1}b\quad\text{with}\quad A=\begin{bmatrix}B&N\end{bmatrix}$$If $x_B \geq 0$, this gives a **basic feasible solution (BFS)**.
2. **Compute Reduced Costs**: let $c_B$ be the cost coefficients of the basic variables, $c_N$ of the non-basics. Define the **simplex multipliers** (dual variables) as $$y^T=c_B^TB^{-1}$$Compute **reduced costs** for the nonbasic variables: $$\bar{c}_N^T = c_N^T - y^T N$$Here $\bar{c}_j$ tells how much the objective changes if $x_j$ enters the basis.
3. **Optimality Check**: if all reduced costs satisfy $$\bar{c}_j \leq 0 \quad \forall j \in N$$then the current BFS is **optimal**, with solution $(x_B, x_N)$ and objective value $z = c_B^T x_B$. Otherwise, choose an entering variable  with $\bar{c}_k > 0$ (for maximization).        
4. **Determine Leaving Variable (Ratio Test)**: compute the direction in which $x_k$ increases: $$d_B = A_B^{-1} A_k, \quad d_N = e_k$$Feasibility requires $x_B - \theta d_B \geq 0$. The maximum step size is $$\theta^* = \min_{i: d_{B,i} > 0} \frac{x_{B,i}}{d_{B,i}}$$The index $i$ attaining the minimum corresponds to the **leaving variable**.   
5. **Pivot (Update Basis)**: replace the leaving variable with the entering variable in the basis. Update $A_B$, $c_B$, and recompute $x_B = b - A_N x_N$. This gives a new BFS with strictly improved objective value.
6. **Iterate**: return to Step 2 with the updated basis. Continue until the optimality condition in Step 3 is satisfied.
### Worked example
Consider $$\begin{array}{l}\max& z=3x_1+2x_2+4x_3\\\st&x_1+x_2+x_3\le30\\&2x_1+x_2+3x_3\le60\\&x_1,x_2,x_3\ge0\end{array}$$by constructing the slack variables $s_1,s_2$ we have $$\begin{array}{l}x_1+x_2+x_3+s_1=30\\2x_1+x_2+3x_3+s_2=60\end{array}$$Below we start illustrating the algorithm.
1. **Initialization**: based on the above data we have the tableau $$\begin{array}{c|ccccc|c}\text{Basic}&x_1&x_2&x_3&s_1&s_2&\text{RHS}\\\hline z&-3&-2&-4&0&0&0\\\hline s_1&1&1&1&1&0&30\\s_2&2&1&3&0&1&60\\ \end{array}$$Here the reduced costs $\xi_j$ are calculated via $$y^T=c_B^TB^{-1},\quad\xi_j=c_j-y^Ta_j$$since there are positive elements in $\xi_j$, we pick the smallest $\xi_3=-4$, and perform ratio test $$\theta_i=\frac{b_i}{a_{ij}}$$the variable with the minimal positive ratio $\theta_3=20$ is picked as the update variable. 
2. **Update tableau**: divide pivot row by pivot, then eliminate that column from other rows. Doing that yields the updated tableau: $$\begin{array}{c|ccccc|c}\text{Basic}&x_1&x_2&x_3&s_1&s_2&\text{RHS}\\\hline z&-1/3&-2/3&0&0&4/3&80\\\hline s_1&1/3&2/3&0&1&-1/3&10\\x_3&2/3&1/3&1&0&1/3&20\\ \end{array}$$Here the checking calculation are exactly the same, and by calculation we find that $\xi_2=-\frac{2}{3}$ is the largest positive , and the corresponding smallest positive ratio is $\theta_2=15$, which is the variable for the next update.
3. **Final optimality check and solution**: we repeat the updating process, yielding $$\begin{array}{c|ccccc|c}\text{Basic}&x_1&x_2&x_3&s_1&s_2&\text{RHS}\\\hline z&0&0&0&1&1&90\\\hline x_2&1/2&1&0&3/2&-1/2&15\\x_3&1/2&0&1&-1/2&1/2&15\\ \end{array}$$at this time we check that all $\xi_i$ are non-negative, hence we're reaching an optimal solution, and the final result is $$z^*=3x_1+2x_2+4x_2=3\times0+2\times15+4\times15=90$$and this completes the solving process of this LP problem.
### Discussion
- **Cost coefficients $\xi_j$**: here we're defining $\xi_j$ as exactly the values in the $z$ line in the tableau, not their additive inverse. The updating proceeds by finding the extremal $\xi_j$ (largest or smallest, depending on the problem type $\min/\max$)
	- **Intuition about $\xi_j$**: we can basically think about $-\xi_j$ as a signal of whether giving it some value would make the total value larger/smaller. If $\xi_j>0$ then it helps to maximize the target, while when $\xi_j<0$ it helps to minimize the target.
- **Which variable to tighten**: after picking the variable to be loosened, we need to pick another variable to be tightened, and this is done by picking the basic variable with the **smallest positive ratio**.
	- **What if zero ratio shows up**: when RHS contains an $0$ the ratio, which is $0$, is obviously the smallest among all non-negative ones. In such case whether it should be chosen as the tightening variable depends on whether the basic solution after the iteration is feasible. A **rule of thumb** is that, it's allowed to be chosen only when the corresponding $a_{ij}>0$.
- **Difference between $\max$ and $\min$ problems**: the differences mainly lie in how the updating is performed, and how optimality is signified. Basically we can summarize them as: $$\begin{array}{c}\text{problem type}&\text{updating rule}&\text{optimality criterion}\\\hline\max&\text{find smallest non-positive }\xi_j&\xi_j\ge0,\forall j\\\min&\text{find largest non-negative }\xi_j&\xi_j\le0,\forall j\end{array}$$the problem asks to minimize the target function rather than maximize it, then in the updating stage we should pick the variable with minimal non-positive $\xi_j$ rather than maximal non-negative one, and the optimality criterion is that all $\xi_j$ are positive rather than negative.
### Two-stage method
Sometimes it's hard to find the initial variables to start with when there is no identity sub-matrix explicitly shown in the simplex tableau. In such case we consider the two stage method. Assuming that we're dealing with a minimizing problem, and by introducing manual variables $x_{m+1}\cdots,x_{m+k}$ to **proper constraints we ensure that the simplex tableau contains an identity sub-matrix**. Now we can proceed as follows: 
1. **Stage one**: we first try to solve the auxiliary problem $$\min\quad g=\sum_{i=m+1}^{m+k}x_i$$with exactly the same constraints. If it has an optimal solution with $x_i=0$ for all manual variables, then we're also obtaining a feasible solution, based on which we can start the second stage.
	- **Feasibility check**: if in the optimal solution there are some positive $x_i$ in the manual variables, then the original equation has no feasible solution.
2. **Second stage**: we start with the feasible solution obtained in the first stage to perform the simplex algorithm. The rest are the same.
#### Worked example
Consider solving the minimizer problem $$\begin{array}{l}\min& z=5x_1+21x_3\\\st&x_1-x_2+6x_3-x_4=2\\&2x_1+x_2+2x_3=1\\&x_j\ge0,\quad1\le j\le5\end{array}$$For this problem we can notice that a basic feasible solution to start with does no exists, hence we need to apply the two-stage method for finding one.
Introducing two manual variables $x_6,x_7$, then the starting simplex tableau is $$\begin{array}{c|ccccc|cc|c}\text{Basic}&x_1&x_2&x_3&x_4&x_5&x_6&x_7&\text{RHS}\\\hline z&-5&0&-21&0&0&0&0&0\\\hline g&0&0&0&0&0&-1&-1&0 \\\hline x_6&1&-1&6&-1&0&1&0&2\\x_7&1&1&2&0&-1&0&1&1\\ \end{array}$$by adding $x_6,x_7$ to the $g$ row we get the simplex tableau $$\begin{array}{c|ccccc|cc|c}\text{Basic}&x_1&x_2&x_3&x_4&x_5&x_6&x_7&\text{RHS}\\\hline z&-5&0&-21&0&0&0&0&0\\\hline g&2&0&8&-1&-1&0&0&3 \\\hline x_6&1&-1&6&-1&0&1&0&2\\x_7&1&1&2&0&-1&0&1&1\\ \end{array}$$Now we can start the simplex algorithm from $x_6,x_7$, which will results in $$\begin{array}{c|ccccc|cc|c}\text{Basic}&x_1&x_2&x_3&x_4&x_5&x_6&x_7&\text{RHS}\\\hline z&1/4&0&0&-21/8&-21/8&21/8&21/8&63/8\\\hline g&0&0&0&0&0&-1&-1&0 \\\hline x_3&1/4&0&1&-1/8&-1/8&1/8&1/8&3/8\\x_2&1/2&1&0&1/4&-3/4&-1/4&3/4&1/4\\ \end{array}$$Now we can abandon the rows and columns of $x_6,x_7$ and consider only the rest variables $$\begin{array}{c|ccccc|c}\text{Basic}&x_1&x_2&x_3&x_4&x_5&\text{RHS}\\\hline z&1/4&0&0&-21/8&-21/8&63/8\\\hline x_3&1/4&0&1&-1/8&-1/8&3/8\\x_2&1/2&1&0&1/4&-3/4&1/4\\ \end{array}$$It remains to apply the original simplex method for calculation.
## Dual problem
The dual problem of a regular LP problem is $$\begin{array}{l}\min&c^Tx\\\st&Ax\ge b\\&x\ge0\end{array}\quad\longleftrightarrow\quad\begin{array}{l}\max&b^Ty\\\st&A^Ty\le c\\&y\ge0\end{array}$$and the dual problem of a standard LP problem is $$\begin{array}{l}\min&c^Tx\\\st&Ax=b\\&x\ge0\end{array}\quad\longleftrightarrow\quad\begin{array}{l}\max&b^Ty\\\st&A^Ty\le c\\&y\gtrless0\end{array}$$Note that $y\gtrless0$ is usually neglected since it's a free variable (this doesn't mean that all $y$ are free, since some of the constraints in $A^Ty\le c$ poses positivity conditions). 
The relation between a problem and is dual problem can be summarized as follows:

```sheet
|Original problem|<|Dual problem|<|
|:---:|:---:|:---:|:---:|
|$\max$|<|$\min$|<|
|Coefficients $c$|<|Coefficients $b$|<|
|Coefficients $b$|<|Coefficients $c$|<|
|Variables|$n$|$n$|Constraints|
|^|$\ge0$|$\ge$|^|
|^|$\le0$|$\le$|^|
|^|free|=|^|
|Constraints|$m$|$m$|Variables|
|^|$\le$|$\ge0$|^|
|^|$\ge$|$\le0$|^|
|^|$=$|free|^|
```
About the solution of two problems, we have the following possibility table: 
```sheet
|Original|Dual|<|<|
|:---:|:---:|:---:|:---:|
||have optimal solution|unbounded|no feasible solution|
|have optimal solution|$\checkmark$|$\large\times$|$\large\times$|
|unbounded|$\large\times$|$\large\times$|$\checkmark$|
|no feasible solution|$\large\times$|$\checkmark$|$\checkmark$|
```
- **Duality theorem**: if the original problem has an optimal solution, then so is their dual problem, and the optimal values of tow problem equals
- **Duality relation**: if $\overline x,\overline y$ are feasible solutions for the original and dual problem, then $$c^T\overline x\le b^T\overline y$$which is referred to as **weak duality**. Further, given feasible solutions $\hat x,\hat y$ for original and dual problems, then both are optimal solutions iff $$c^T\hat x=b^T\hat y$$This is referred to as the **strong duality**.
- **Dual slack theorem**: given $\hat x,\hat y$ feasible and $x_s,y_s$ the corresponding feasible solutions for the slack variables, t
- hen $\hat x,\hat y$ are optimal iff $$x_s\odot\hat y=0,\quad y_s\odot\hat x=0$$here $\odot$ means element-wise multiplication. 
	- This can be useful for calculating the optimal solution, taking above as conditions.
- **Optimality criterion**: given 
### Worked examples
![[Pasted image 20251008155846.png]]
![[Pasted image 20251008160129.png]]
## Dual simplex method
The main difference between dual simplex method and original simplex method is that, we pick the loosen variable first, and then pick the tighten variable. 
- **Example 1**: if we're given the following simplex tableau $$\begin{array}{c|ccccc|c}\text{Basic}&x_1&x_2&x_3&x_4&x_5&\text{RHS}\\\hline z&-1&-1&-1&0&0&0\\\hline x_4&-3&-1&-1&1&0&-1\\x_5&1&-4^*&-1&0&1&-2\end{array}$$now the solution is already optimal, but not feasible, hence we **go the other way around** to pick the loosen variable $x_5$ by $-2<-1$, and the corresponding tighten variable $x_2$ by $\frac{-1}{-4}<\frac{-1}{-1}$. The rest are the same - we move on by row transformation of [[Matrix]], and iterate as above until the algorithm converges.
- **Example 2**: below is another example showcasing the complete process of solving the problem via dual simplex method: $$\begin{array}{c|cccccc|c}\text{Basic}&x_1&x_2&x_3&x_4&x_5&x_6&\text{RHS}\\\hline z&-3&-2&-1&0&0&0&0\\\hline x_4&1&1&1&1&0&0&6\\x_5&-1^*&0&1&0&1&0&-4\\x_6&0&-1&1&0&0&1&-3\end{array}$$here we pick $x_5$ to be replaced by $x_1$, yielding $$\begin{array}{c|cccccc|c}\text{Basic}&x_1&x_2&x_3&x_4&x_5&x_6&\text{RHS}\\\hline z&0&-2&-4&0&-3&0&12\\\hline x_4&0&1&2&1&1&0&2\\x_1&1&0&-1&0&-1&0&4\\x_6&0&-1^*&1&0&0&1&-3\end{array}$$again we pick $x_6$ to be replaced by $x_2$, yielding $$\begin{array}{c|cccccc|c}\text{Basic}&x_1&x_2&x_3&x_4&x_5&x_6&\text{RHS}\\\hline z&0&0&-6&0&-3&-2&18\\\hline x_4&0&0&3&1&1&1&-1\\x_1&1&0&-1&0&-1&0&4\\x_6&0&1&-1&0&0&-1&3\end{array}$$at this point we recognize that $-1<0$, while in the same column all coefficients are positive, meaning that there is no variable to be tighten, hence we conclude that the problem does no have a solution.