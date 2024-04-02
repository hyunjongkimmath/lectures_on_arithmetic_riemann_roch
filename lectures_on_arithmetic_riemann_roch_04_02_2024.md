---
cssclass: clean-embeds
aliases: []
tags: [_meta/self_written, _meta/notes]
---
# Local version of the Riemann-Roch-Grothendieck theorem

Speaker: [[finski_siarhei]]

![[Pasted image 20240402150528.png]]

Take a holomorphic submersion $X \xrightarrow{\pi} B$ where $X$ and $B$ are both Kahler. Pick a Kahler form $\omega_X$. Assume that $\pi$ is proper. Let $(E,h^E)$ be a holomorphic line bundle on $X$ with Riemannian metric $h^E$.

$\lambda(E)$ is the holomorphic line bundle over $B$  defined by

$$\lambda(E) = \bigotimes_{i=0}^{\text{rel dim}} \det(R^i \pi_* E)^{\otimes (-1)^i}$$

> $R^i \pi_* {E}$ are sheaves over $B$ and they satisfy
> $$H^0(U, R^i\pi_* {E}) = H^i(\pi^{-1}(U), E)$$ and the stalks satisfy
> $$R^i \pi* {E}_b = H^i(X_b, E).$$

The RRG theorem says that 

$$c_1(\lambda(E)) = \pi_*(\operatorname{Td}(TX/B) \cdot \operatorname{ch}(E)) \in H^2_{\text{DR}}(B)$$

The curvature theorem of Bismut-Gillet-Soule says that

$$c_1(\lambda(E), \|\cdot\|_Q) = \pi_*(\operatorname{Td}(TX/B, \omega_X) \cdot \operatorname{Ch}(E, h^E))^{[2]} \in \Omega^2(B)$$

where $\|\cdot\|_Q$ is the Quillen metric. The curvature theorem is a pointwise identity, unlike the RRG theorem.

Recall that the Quillen norm is defined by

$$\|\cdot\|_{Q,b} = \|\cdot\|_{L^2,b} \cdot T(X_b, E), \quad b \in B$$

$\|\cdot\|_{L^2,b}$ is the restriction of the $L^2$-norm on $C^\infty(X_b, \wedge^{0,i} T^* X_b \otimes E)$ to harmonic representations. Moreover, $\langle s,s' \rangle_{L^2,b}$ is defined by

$$\langle s,s'\rangle_{L^2,b} = \int_{X_b} \langle s(x), s'(x) \rangle_{\omega \otimes h} dV$$
for $s,s' \in C^\infty ( X_b, \wedge^{0,i} T^* X_b \otimes E)$. The Analytic torsion is defined by

$$T(X_b, E) = (\det \square_i)^{(-1)^i i/2}$$

where $\square_i$ is the Kodaira Laplacian $\delta \delta^* + \delta^* \delta$. $\det \square_i$ is defined formally as

$$\det \square_i = \prod_{j=1}^\infty \lambda_j^i$$

where the $\lambda_j^i$ are the nonzero eigenvalues of $\square_i$. We define the zeta function 

$$\zeta_i(s) = \sum \frac{1}{(\lambda_j^i)^s}$$


# 

Imagine that $B = C$ is a Riemann compact connected surface. Then

$$H^2(C) = \mathbb{R}.$$

The RRG theorem then tells us that one number in this vector space equals another. The Bismut-Gillet-Soule theorem says that one function on this vector space equals another pointwise. And then the RRG theorem says that integral of one function equals the integral of the other function, so the Bismut-Gillet-Soule theorem is saying something much stronger.

## Example

For $B = U$ contractible in $\mathbb{C}^n$, then $H^2(U) = 0$. So the RRG says something trivial --- that $0 = 0$. However, the Bismut-Gillet-Soule theorem says something stronger --- the theorem says that two functions on $U$ agree.

# Proof of the BGS theorem

This proof is only carried out when $R^i \pi_* E$ is locally free. We will see that 

$$\sum (-1)^i \operatorname{ch}(R^i\pi_* E, \|\cdot\|_{L^2}) = - \pi_* ( -//-) = d_B \alpha$$

In lecture $4$, the latter equality will be shown. In lecture 5, it will be shown that $d_B \alpha = \partial \overline{\partial} \beta$ for some $\beta$; this $\beta$ can be explicitly written out.

# Study of Heat kernel

Let's start with a corollary of the most important statement, which is to be stated later:

> [!Corollary]
> Let $M$ be a Riecompact mannian manifold of dimension $n$. Let $E$ be a complex vector bundle over $M$ of rank $r$. Let $\square$ be the Laplacian on $\mathcal{C}^\infty(M,E)$[^1]. It is a degree $2$ operator given by $-\partial_{e_i} \partial_{e_i} + (\text{lower order terms})$, where $e_i$ form an orthonormal basis. It is the case that $\operatorname{Spec} \square = \{\lambda_1,\ldots\}$ is discrete. Then
> $$\sum_{i=0}^{+\infty} e^{-t \lambda_i} =_{t \to 0} \frac{1}{t^{n/2}} \sum_{i=0}^N a_i \cdot t^i + O(t^N)$$
> where 
> $$a_0 = \frac{\operatorname{vol}(M) \operatorname{rk}(E)}{(4\pi)^{n/2}}.$$

[^1]: The set of smooth sections of $E \to M$?

> [!Corollary of the corollary]
> (Weyl's law)
> $\lambda_i \sim c \cdot i^{2/n}$

This corollary follows from the Tauberian theorem (Karamata). See Chapter 2 of the book of BGV.

> [!Corollary]
> (Seeley)
> $\zeta(s) := \sum_{i=0}^\infty \frac{1}{\lambda_i^s}$ extends meromorphically to the whole complex plane and $0$ is a holomorphic point.

> [!Definiiton]
> (Mellin transform)
> Let $f: ]0,+\infty[ \to \mathbb{R}$[^2] be a function. Its Mellin transform is defined as 
> $$M[f](s) = \frac{1}{\Gamma(s)} \int_0^{+\infty} t^{s-1} f(t) dt$$
> where $s \in \mathbb{C}$.

[^2]: $],[$ means open interval; it seems that $(,)$ is more commonly used notation in the U.S.

Note that 

$$M(e^{-t \lambda}) = \frac{1}{\Gamma(s)} \int_0^{+\infty} t^{s-1} e^{-t \lambda} dt = \frac{1}{x^s}$$


> [!Proposition]
> If $f$ satisfies
> - $|f(t)| \leq \exp(-\varepsilon t), \varepsilon > 0$
> - $|f(t) - \sum_{i=-M}^N t^i \alpha_i| \leq Ct^N$,
> then $M[f]$ extends meromorphically to the entire complex plane.

Proof:

$$\begin{align*}
M[f](s) &= \frac{1}{\Gamma(s)} \int_0^\infty t^{-s} f(t) dt \\
&= \frac{1}{\Gamma(s)} \left( \int_0^1  + \int_1^\infty \right)
\end{align*}$$

The $\int_1^\infty$ is holomoprhic, so the integral of interest is $\int_0^1 t^{s-1} f(t)dt$. Since we assume that $|f(t)| < t^{-N}$, the integral will converge when $\operatorname{Re} s > N$. In fact, the integral will be meromorphic when $\operatorname{Re} s > N-1$.

The integral equals
$$\begin{align*}
	\int_0^1 t^{s-1} (f(t) - \frac{a_0}{t^n}) dt + \int_0^1 t^{s-1} \frac{a_0}{t^n} dt 
\end{align*}$$

The left is holomorphic on $\operatorname{Re} s > n-1$. The right integral equals $\frac{a_0}{s-n}$ (or something like that).

Since $\Gamma(z+1) = z\Gamma(z)$ and hence $\Gamma(z)$ has a pole at $0$, some pole cancellation happens, so the meromorphic continuation is holomorphic at $0$.

# Heat transfer

Let $f \in \mathcal{C}^\infty(M,E)$. Let $g(t) = \exp(-t\square) f$. In particular,

$$\frac{\partial}{\partial t} g(t) + \square g(t) = 0.$$

> [!Proposition]
> $\exp(-t\square)$ has a smooth Schwartz kernel, i.e.
> $$\exp(-t\square)(x,y) = E_x \otimes E_y^*$$
> and 
> $$\exp(-t\square) f(x) = \int_M \exp(-t\square)(x,y) f(y) dy$$
> where $x,y \in M$.
> Now $\operatorname{Tr}[\exp(-t\square)] = \int_M \operatorname{Tr}[\exp(-t\square)(x,x)] dU_M(x)$

Proof. Let $e_i$ be an eigenfucntion associated to $\lambda_i$ such that $\|e_i\|_{L^2} = 1$. 

We have

$$\exp(-t\square)(x,y) = \sum e^{-t \lambda_i} e_i(x) \cdot e_i(y)^*$$

Why does the sum above converge? There is an inequality

$$\|e_i\|_{H^2} \leq C(\|\square e_i\|_{L^2} + \|e_i^2\|_{L^2}) = C(\lambda_i +1)$$

Something about the Sobolev embedding
...

$\square$

##
For example, take

$M = \mathbb{R}^n$, $E = \mathbb{R} \times M$ $\square = \sum - \frac{\partial}{\partial x_i^2}$. By explicit calculation, one finds that

$$\exp(-t\square) (x,y) = \frac{1}{4 \pi t}^{n/2} \exp(- \frac{\|x-y\|}{4t} )$$

solves the heat equation.


# Infinite propagation of heat

If you light up fire somewhere, then everywhere else heats up. 

so $\exp(-t\square)$ is a highly global invariant.

...

Localization: roughly $\lim_{t \to \infty} \exp(-t\square)(X,\cdot)$ becomse local around "x"

> [!Theorem 1]
> $|\exp(-t\square)(x,y)| \leq \frac{C}{t^{n/2}} \exp\left(- \frac{\operatorname{dist}(x,y)}{t} \right)$

...

> [!Theorem 2]
> For all $x_0 \in X$, for all $|z|, |z'| \leq \epsilon_0$, $$\exp(-t\square)(z,z') - \frac{1}{t^{n/2}} \exp(-t\square_{\mathbb{R}^n}) (\sqrt{t} z,  \sqrt{t} z') \cdot \sum_{i=0}^N t^{i/2} y_i(\sqrt{t} z, \sqrt{t} z' ) \leq t^{-n/2 + N} C (\text{polynomial in } \sqrt{t}) \exp(-c \frac{|z-z'|^2}{t})$$

See Ma-Marinessew: Bergenou Kernels Chapter 4.2

$J_0(z,t') = \operatorname{Id}_{E_{x_0}}$

This is fundamental because if you let $z = 0$ and $z'=0$, then you get

$$\exp(-t\square)(x_0,x_0) \sim \frac{\alpha_0}{t^{n/2}}$$

...

On $\mathbb{R}^n$ we have homotheties

$$S_t f(z) = f(\sqrt{t} z)$$

> [!Easy fact]
> $S_t t \square^i S_t^{-1}$ converges to $L_0 + t^i \mathcal{O}_i$, where $L_0$ is the standard Laplacian $\sum -\frac{\partial^2}{\partial x_i^2}$.


# See Also

# Meta
## References

## Citations and Footnotes