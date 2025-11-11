## Uniform distribution
- Denote as $U(a,b)$ for $a<b$, and the PDF is $$f(x)=\frac{1}{b-a}, \quad x\in[a,b]$$
- $M_X(t)=\frac{e^{tb}-e^{ta}}{t(b-a)}$.
- Assume that $X_i\sim U(0,1),1\le i\le n$, then $F_{\sum X_i}(x)=\frac{x^n}{n!}$. Denote $N=\min_n(X_1+\dots+X_n>1)$, then $\mathbb{E}(N)=e$.
## Bernoulli process
A Bernoulli process is a sequence $(X_i)_{i\in I}$ where $X_i\sim B(p)$ for some $0\le p\le 1$. Formally, let $\Omega=2^\mathbb N$, and denote the $\sigma$-algebra consisting of all sequences of finite length as $\mathcal B$ with product measure $P([\omega_1,\cdots,\omega_n])=p^k(1-p)^{n-k}$, then Bernoulli process is given by $(\Omega,\mathcal B,P)$.
- **Binomial distribution**: the number of successes in first $n$ trials follows $$B(n,p)=\sum_{i=1}^nB(p),\quad P(X=x)=C_n^xp^x(1-p)^{n-x}$$
	- $EX=np,\var(X)=np(1-p)$.
	- $B(m,p)+B(b,p)\sim B(m+n,p)$ which can be easily verified using binomial theorem or with the fact $B(n,p)\sim\sum_{i=1}^n B(p)$.
	- **Maximum**: $B(n,p)$ reaches its maximum at $\lceil(n+1)p\rceil-1$.
	- $M_X(t)=(pe^t+1-p)^n$. 
	- **Multinomial distribution**: define $X\sim M_n(m;p_1,\cdots,p_n)$ if $$P(X=x)=\binom{m}{x_1,\cdots,x_n}p_1^{x_1}\cdots p_n^{x_n},\quad\sum x_i=m$$We have that any marginal distribution of $M_n$ is $B(m,p_i)$.
- **Geometric distribution**: the number of trials required for the first success follows $$P(X=n)=(1-p)^{n-1}p$$We denote this distribution as $X\sim \text{Geo}(p)$.
	- $EX=\frac{1}{p},Var(X)=\frac{1-p}{p^2}$.
	- $M_X(t)=\frac{pe^t}{1-(1-p)e^t}$.
	- **Memoryless-ness**: geometric distribution is the only memoryless distribution such that  $$P(X>m+n\mid X>n)=P(X>m)$$The identity can be used to derive the geometric distribution. Note that exponential distribution is its continuous analogy.
- **Negative binomial distribution**: the number of trials required for $r$ successes follows $$P(X=n)=C_{n-1}^{r-1}p^r(1-p)^{n-r}$$We denote this as $\text{NB}(r,p)$. Obviously $\operatorname{NB}(r,p)=\sum_{i=1}^r\operatorname{Geo}(p)$.
	- $EX=\frac{r}{p},\var(X)=\frac{r(1-p)}{p^2}$.
	- $M_X(t)=\Big[\frac{pe^t}{1-(1-p)e^t}\Big]^r$.
	- Independent trials with $p$ success probability, $n$ the number of trials needed to accumulate $r$ successes.
## Poisson process
Poisson process is characterized as a point counts of Poisson distribution.
**Poisson's limit theorem**: for $B(n,p),np\equiv\lambda$ the generating function is $$G_n(x)=\sum_{k=0}^np_{n,k}x^k=\left(1-\frac{\lambda}{n}+\frac{\lambda}{n}x\right)^n$$Now take $n\to\infty$ while fixing $np=\lambda$, then $$\lim_{n\to\infty}G_n(x)=\lim_{n\to\infty}\left(1+\frac{\lambda(x-1)}{n}\right)^n=e^{\lambda(x-1)}=\sum_{k=0}^\infty e^{-\lambda}\frac{\lambda^k}{k!}x^k$$Or the approximation can also be derived using Stirling's formula ([[Series]]). Hence we have $\lim_{n\to\infty}B(k;n,\lambda/n)=e^{-\lambda}\frac{\lambda^k}{k!}$.
- **Poisson distribution**: for a Poisson random variable $X\in\mathbb N$ with coefficient $\lambda$,$$p(i)=P(X=i)=e^{-\lambda}\frac{\lambda^i}{i!}$$It expresses the probability of a given number of events occurring in a fixed interval of time if they occur with a known constant mean rate and independently of time since last event.
	- $EX=\var(X)=\lambda$.
	- $M_X(t)=\exp\{\lambda(e^t-1)\}$.
	- **Extremum**: $\operatorname{Poi}(x)$ reaches its maximum at $[\lambda]$, since $p(k;\lambda)/p(k-1;\lambda)=\lambda/k$. Note that this ratio uniquely determines the Poisson distribution.
	- Assume that $X_i\sim \Poi(\lambda_i)$, then $\sum X_i\sim \Poi(\sum\lambda_i)$.
	- Used for approximating $B(n,p)$ when $n$ is large and $p$ is small (in this case $\lambda =np$), or other cases that events are weakly dependent.
	- **Poisson Paradigm**: Consider n events. If $p_i$ small, and trials are independent or at most "weakly dependent", then the number of these events that occurs approximately has a Poisson distribution with mean $\sum p_i$.
- **Exponential distribution**: the time that the first count happens follows $$f(x)=\lambda e^{-\lambda x}, \quad F(x)=1-e^{-\lambda x}$$since this is equivalent to $p(0)$ across $[0,x)$, which means the distribution should be $\Poi(\lambda x;0)$. We denote it as $\Exp(\lambda)$.
	- $EX=\frac{1}{\lambda}, Var(X)=\frac{1}{\lambda^2}$.
	- $M_X(t)=\frac{\lambda}{\lambda-t}$.
	- **Memoryless**: if $P(x>s+t|x>t)=P(x>s),\forall s,t>0$, then such probability distribution is memoryless. This is unique to exponential distribution
- **Gamma distribution**: the time that the $r$-th count happens follows $$\Gamma(r,\lambda)=\sum_{i=1}^r\operatorname{Exp}(\lambda),\quad f(x)=\frac{\lambda e^{-\lambda x}(\lambda x)^{r-1}}{\Gamma(r)}$$Here we can generalize to $r\in\mathbb R$.
  **Proof**: $Z_r\le t\iff X_t\ge r$, hence $$F_Z(t)=P(X_t\ge r)=e^{-\lambda t}\sum_{k=r}^\infty\frac{(\lambda t)^k}{k!}\quad\Longrightarrow\quad\frac{d}{dt}F_Z(t)=e^{\lambda t}\frac{\lambda^r}{(r-1)!}t^{r-1}$$hence by its form we get the result. [[Gamma Function]]
	- $EX=\frac{\alpha}{\lambda},Var(X)=\frac{\alpha}{\lambda^2}$.
	- Gamma random variables are closed under convolutions. [[Gamma Function]]
	- **Additivity**: given two independent Gamma RVs we have $$X_1\sim\Gamma(r_1,\lambda),\quad X_2\sim\Gamma(r_2,\lambda)\quad\Longrightarrow\quad X_1+X_2\sim\Gamma(r_1+r_2,\lambda)$$This can be deduced via the convolutional properties of [[Gamma Function]] and Beta function.

## Hypergeometric distribution
In a set of experiments with each draw classified into one of two mutually exclusive categories, hypergeometric distribution measures the number of trials belonging to one category $$P(X=i)=\frac{C_m^iC_{N-m}^{n-i}}{C_N^n}$$Its key difference from binomial distribution is that the probability changes among trials.
- $EX=\frac{mn}{N},\var(X)=np(1-p)(1-\frac{n-1}{N-1}),p=\frac{m}{N}$.
- Choose $n$ samples from $N$ balls containing $m$ white and $N-m$ black, $X$ is the number of black selected.
## Zeta (Zipf) distribution
- For $C$ constant and $\alpha>0$,$$P(X=k)=\frac{C}{k^{\alpha+1}}$$
- Derive from Zeta function.

## Beta distribution
- For $0<x<1$, denote $B(a,b)=\int_0^1x^{a-1}(1-x)^{b-1}dx$, we have $$f(x)=\frac{x^{a-1}(1-x)^{b-1}}{B(a,b)}$$
- $EX=\frac{a}{a+b},Var(X)=\frac{ab}{(a+b)^2(a+b+1)}$.
## Laplace distribution
Also called a double exponential distribution, is defined as $$x\sim\text{Laplace}(\mu,b)\quad\iff\quad f(x|\mu,b)=\frac{1}{2b}\exp\left(-\frac{|x-\mu|}{b}\right)$$where $\mu$ is the location parameter, and $b>0$ is the "diversity". 