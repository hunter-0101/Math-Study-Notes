**Difference with classical [[Statistic]]**: in classical statistics the [[Sampling]] usually has a fixed dimension of features $d$, and the number of samples $n$ is allowed to increase, hence results like [[Central Limit Theorem]] and LLN can be applied. However, in modern settings,
1. **Larger feature dimension**: the data arising in many parts of modern science & engineering have a "high-dimensional flavor", with $d$ on the same order as, or possibly larger than, the sample size $n$.
2. **Deficiency of classical theory**:  for many of these applications, classical larger $n$, fixed $d$ theory fails to provide useful predictions.
3. **Breaking of classical models**: classical methods can break down dramatically in high-dimensional regimes.
These facts motivate the study of high-dimensional statistical models, as well as the associated methodology and theory for estimation, testing, and inference in such models.

**Why tail & concentration bounds are central**: almost all high-dimensional results (Johnson–Lindenstrauss lemma, random matrix spectral norm bounds, compressed sending RIP proofs, generalization error bounds, etc.) depend on concentration, while tail control gives rise to robustness of estimators. 
## HDS vs data synthesis
Two main strategies exist to address the scarcity of information in high dimensions:
1. **Data augmentation (increase $n$)**: generating synthetic data to make the data distribution denser. 
	- **Advantage**: fills empty space, directly addresses data sparsity. 
	- **Disadvantage**: risk of introducing **bias** or **spurious correlations** if the generation model is poor.
	- **Suited for**: [[Computer Vision]] and domains with strong underlying structural laws (e.g., chemical informatics)
	- **Examples**: TimeGAN (or more generally, [[TS & GAN]])
2. **Algorithm design (reduce effective $p$)**: building algorithms that impose and exploit low-dimensional structure (e.g., sparsity) through regularization.
	- **Advantage**: provides **statistical consistency** and reduces variance (prevents overfitting).
	- **Disadvantage**: failure if the **sparsity assumption** is false (if the true signal is dense).
	- **Suited for**: **genomics/proteomics** (where only a few genes are relevant), and **financial modeling** (where low-rank factor structure is assumed). 
	- **Examples**: [[Generalized Sampling Theorem]], and techniques in [[Dimensionality Reduction]].