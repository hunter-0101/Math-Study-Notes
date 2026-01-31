For a functor $F:\mathcal C\to\mathcal D$ with objects $A,A'\in \mathcal C,X\in\mathcal D$, a **universal morphism** from $X$ to $F$ is a unique pair $(A,u:X\to F(A))$ in $\mathcal D$ satisfying the **universal property**: for any morphism $f:X\to F(A')$, there exists a unique morphism $h:A\to A'$ s.t. the following diagram commutes: 
<p align="center"><img align="center" src="https://i.upmath.me/svg/%0A%5Cbegin%7Btikzcd%7D%0AX%20%5Carrow%5Br%2C%20%22u%22%5D%20%5Carrow%5Brd%2C%20%22f%22'%5D%20%26%20F(A)%20%5Carrow%5Bd%2C%20%22F(h)%22%2C%20dashed%5D%20%26%20A%20%5Carrow%5Bd%2C%20%22h%22%2C%20dashed%5D%20%5C%5C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20F(A')%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20A'%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%0A%5Cend%7Btikzcd%7D%0A" 
 /></p>

- **Commutative diagram suggestion**: when drawing a commutative diagram there are some general mathematical aesthetic rules to follow, listed below according to descending priority.
	1. **Inside rule**: for closed shapes, it's standard to keep labels on the outside of the perimeter to keep the "interior" clear for showing that the diagram commutes.
	2. **Avoid overlap**: if an arrow is diagonal, place the label so it doesn't "fall" into the center of the diagram where it might collide with other morphisms. 
	3. **Left-hand rule**: imagine yourself waking along the arrow from source to target, then the label should generally be on your **left**. 
  For arrangement of objects, we should mostly follow the **gravity principle**: information should flow **from top-left to bottom-right**. 
## Examples
Definition of [[Free Group]] and group product ([[Product of Groups]]).