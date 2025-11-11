**An epsilon of room** is very similar with the [[Standard Mechanism]], but they differ in the direction of how we approach the target statement and plan our journey to it. The general idea goes as follows:
1. **Weaken the statement a little bit**: we'll first impose stronger conditions to make the target statement weaker, hence easier to prove. 
2. **Strengthening our result**: based on the fact that the weaker statement is always true given arbitrary "pre-requisite", we can step forward to obtain the original statement via some related limit argument. 
In contrast, [[Standard Mechanism]] would start with the simplest case (usually simple functions or step functions), and then carry the result over to general case using density argument or other related limit arguments.
## Scaler version
- **Proof of inequalities**: proof of many inequalities requires using an epsilon of room to widen the distance to find some intermediate bridge. Such as DCT in [[Lebesgue Integral]]
- **Spectral radius**: [[Eigendecomposition]] and [[Spectrum]] provides typical examples for application for this technique.
## Regularize-and-pass
This method is used to prove identities, inequalities, or representations in cases where the desired result does not directly hold due to insufficient decay, integrability, or regularity. Key steps includes:
1. **Regularize**: stronger assumption is imposed on the functions of discussion, so that the desired result is immediate.
2. **Pass to the limit**: remove the regularization using a proper convergence theorem.
Several examples are listed below to illustrate this technique.
- **Fourier inverse formula for [[FT on L1]]**: the target equality is a double integral over $\mathbb R^2$: $$I(x)=\int\left(\int f(t)e^{2\pi i\xi(x-t)}dt\right)d\xi$$whose integrability is not known. To this end we introduce a Gaussian kernel to get $$I_\epsilon(x)=\int\left(\int f(t)e^{-\epsilon^2\xi^2/4}e^{2\pi i\xi(x-t)}dt\right)d\xi$$In this expression we have $\|f\|_1,\|\exp(-\epsilon^2\xi^2/4)\|_1<\infty$, hence $\|I_\varepsilon\|<\infty$, ensuring validity of Fubini's theorem.
- **Integral expression in [[Hardy Space]]**: in Hardy space we used $$F^\epsilon(z)=F(z)\frac{1}{(1-i\epsilon z)^2}\to F(z),\quad\forall\Im z>0,\epsilon\searrow0$$mainly for application of [[Contour Integral]] technique via uniform boundedness.
- **Paley-Wiener theorem ([[Analytic Continuation]])**: similar to Hardy space, we used $$\begin{align}f_{1,\epsilon}(z)&=\frac{f(z)}{(1+i\epsilon z)^2}\to f(z),\quad\epsilon\searrow0,\forall\Im z\le0\\ f_{2,\epsilon}(z)&=\frac{f(z)}{(1-i\epsilon z)^2}\to f(z),\quad\epsilon\searrow0,\forall\Im z\ge0\end{align}$$for upper and lower complex plane, for exactly the same goal.
- Maximum principle in [[Diffusion Equation]].