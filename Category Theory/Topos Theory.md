## Natural transformation
If $F,G$ are functors between categories $C,D$ (both from $C$ to $D$), then a natural transformation $\eta$ from $F$ to $G$ is a family of morphisms that satisfies two requirements:
1. The natural transformation must associate, to every object $X$ in $C$, a morphism $\eta_X:F(X)\to G(X)$ between objects of $D$. The morphism $\eta_X$ is called the component of $\eta$ at $X$.
2. Components must be such that for every morphism $f:X\to Y$ in  $C$ we have: $\eta_Y\circ F(f)=G(f)\circ\eta_X$.
- **Intuitive understanding**: "natural" means something is definable by the generic properties of objects in the theory under study, rather than by properties of the specific objects for which the thing is being defined. 