# Time-fractional Allen-Cahn Equation Solver
## Problem
Allen and Cahn purposed a phase field model to describe the antiphase motion
of the alloys in 1970s. Consider the energy functional [[1]](#1)

$$
E[u] = \int_{\Omega} \dfrac{\epsilon^2}{2} \vert \nabla u \vert^2 + W(u) dx
$$

where $W(u)=\frac{(1-u^2)^2}{4}$ is the double-well potential and $\epsilon$ is the width of interface. $u(x,t)$ is the order parameter of the concentration for the two phases at $x$ and time $t$.

To minimize $E[u]$, which leads to Allen-Cahn equation


$$
    \dfrac{\partial u}{\partial t} = \epsilon^2\Delta u - W'(u)
$$

which is the $L^2$ gradient flow of $E[u]$.

The well-known method to solve Allen-Cahn equation numerically is convex splitting method, see [[3]](#3) for more detail.

Regarding the time-fractional Allen-Cahn equation, the temporal derivative term is replaced with a Caputo derivative with respect to time as following

$$
{}_CD_t^{\alpha} u = \epsilon^2 \Delta u -W'(u)
$$
where $\displaystyle {}_CD_t^{\alpha} u=\int_0^t \frac{(t-s)^{\alpha}}{\Gamma{(1-\alpha)}}u'(s)d$ represents the Caputo derivative with respect to time for $u$.


## Reference 
<a id="1">[1]</a> 
Allen, Samuel M., and John W. Cahn. "A microscopic theory for antiphase boundary motion and its application to antiphase domain coarsening." Acta metallurgica 27.6 (1979): 1085-1095.

<a id="2">[2]</a>
Du, Qiang, Jiang Yang, and Zhi Zhou. "Time-fractional Allen–Cahn equations: analysis and numerical methods." Journal of Scientific Computing 85.2 (2020): 42.

<a id="3">[3]</a>
Eyre, David J. "An unconditionally stable one-step scheme for gradient systems." Unpublished article 6 (1998).