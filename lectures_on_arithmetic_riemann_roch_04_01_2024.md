---
cssclass: clean-embeds
aliases: []
tags: [_meta/self_written, _meta/notes]
---
# Local version of the Riemann-Roch-Grothendieck theorem

Speaker: [[finski_siarhei]]

Let's recall Characteristic classes and Riemann-Roch-Grothendieck (RRG) theorem.

Let $X$ be a compact complex manifold. (Most of the time, we won't need $X$ to be compact), let $E$ be a holomorphic vector bundle over $X$.

We would like to define $\operatorname{ch}(E) \in H_{\text{DR}}^\bullet(X)$ and $\operatorname{Td}(E)$.

Let $L$ be a line bundle. Associated to it is the first Chern class $c_1(L) \in H^2(X)$. This is compatible with pullbacks. 

When $E = \bigoplus L_i$, define $\operatorname{Ch}(E) = \sum \operatorname{Ch}(L_i) = \sum e^{c_1(L_i)} \in H^{2 \bullet}(X)$, where the exponential function is defined by the usual formal power series.

The Todd class $\operatorname{Td}(E)$ is defined as $\prod_{i=1}^{n} \frac{c_1(L_i)}{1-e^{-c(L_i)}}$

Given a short exact sequence
$$0 \to E_0 \to E_1 \to E_2 \to 0,$$
we have

$$\operatorname{Ch}(E_1) = \operatorname{Ch}(E_2) + \operatorname{Ch}(E_0)$$

and

$$\operatorname{Td}(E_1) = \operatorname{Td}(E_0) \cdot \operatorname{Ch}(E_2)$$

> [!Grauert's theorem]
> - Given a proper holomorphic map $f: X \to Y$ of compact manifolds and a vector bundle $E/X$, the sheaves $R^\bullet \pi_* E$[^2] are coherent sheaves over $Y$.
> - If $X$ is a projective manifold, and $\mathcal{E}$ is a coherent sheaf on $X$, then there is a global resolution
> $$0 \to E_n \to E_{n-1} \to \cdots \to E_0 \to \mathcal{E} \to 0$$
> by vector bundles.
> 
> In particular, we can define the Chern character $\operatorname{Ch}(E) = \sum_i \operatorname{Ch}(E_i) (-1)^i$. This definition is not dependent on the choice of global resolution and it is a well defined class in $H^\bullet(X)$.

[^2]: I think that Siarhei means $f$ when he write $\pi$.

> [!RRG Theorem]
> Let $f: X \to Y$ be a holomorphic and smooth map of smooth projective manifolds and let $E/X$ be a vector bundle. Then (in $H^\bullet(Y)$), we have
> $$\sum_{i=1}^n (-1)^i \operatorname{Ch}(R^i f_* E) \cdot \operatorname{Td}(TY) = f_* (\operatorname{Ch}(E) \cdot \operatorname{Td}(TX))$$[^2]
> 

## Example
For example, let $i: D \to Y$ be a smooth divisor in $Y$. Let us apply the RRG theorem for $X = D$, $E = \mathcal{O}_D$, and $f = i$. Now $i$ is a finite map, so $R^j \pi_* \mathcal{O}_Y = \begin{cases} 0 & \text{if } g \geq 1 \\ i_* \mathcal{O}_Y &\text{otherwise} \end{cases}$

The RRG theorem says that 

$$\operatorname{ch}(i_* \mathcal{O}_D) \cdot \operatorname{Td}(TY) = i_* (\operatorname{Td}(TD)).$$

Let us verify this by hand. We have the short exact sequence

$$0 \to \mathcal{O}(-D) \xrightarrow{s_D (\text{multiplication by the canonical section})} \mathcal{O}_Y \to i_* \mathcal{O}_D \to \text{Res}.$$

We have $\operatorname{Ch}(i_* \mathcal{O}_D) = 1 - e^{-c_1(\mathcal{O}(D))}$. We also have

$$c_1(D) \cdot \frac{1-e^{-c_1(\mathcal{O}(D))}}{c_1(D)} \cdot \operatorname{Td}(TY) = i_* (\operatorname{Td}(TD)).$$

Moreover, the LHS above equals

$$i_* \left( \frac{1-e^{c_1(D)|_D}}{c_1(D)|_D} \cdot \operatorname{Td}(TY|_D) \right)$$

Writing $TY|_D = TD \oplus N$ and $N = c_1(D)|_D$, we have that

$$\operatorname{Td}(TY|_D) = \operatorname{Td}(TY) \cdot \operatorname{Td}(N)$$

## Example
As for another example, let $Y$ be a point. The theorem says that

$$\sum(-1)^i \dim H^i(X,E) = \int \operatorname{Ch}(E) \operatorname{Td}(TX))$$

which is the Riemann-Roch-Hirzebruch formula.

## Example

Degree $1$ piece or RRG. Knudsen and Mumford associated to a general coherent sheaf $\mathcal{E}$ on $X$ the determinant bundle $\det \mathcal{E}$, which is a line bundle on $X$. 

When $\mathcal{E} = E$ is a vector bundle, $\det E = \wedge^{\text{top}} E$.

We consider $\lambda(E) = \otimes (\det R^i f_* E)^{(-1)^i}$. One thing that is true is that $\operatorname{Ch}_1(\mathcal{E}) = c_1(\det \mathcal{E})$. The RRG theorem can be re-written as

$$\tag{1} c_1(\lambda(E)) \cdot \operatorname{Td}(TY) = \pi_* ( \operatorname{Ch}(E) \cdot \operatorname{Td}(X))$$



We will refine the equation (1) under an assumption --- that $f$ is a submersion.

# Chern-Weil theory


"Pass characteristic classes to differential forms" representing them in DeRham cohomology $H^\bullet(X)$.

Given a complex vector bundle $E \to X$, let $\nabla^E: \mathcal{C}^\infty(X,E) \to \Omega^1(X,E)$ be an arbitrary connection, where $\Omega^1(X,E)$ denotes the $1$-differential forms with values in $E$. The connection $\nabla^E$ can be extended in a unique way --- as

$$\nabla^E: \Omega^i(X,E) \to \Omega^{i+1} (X,E)$$

--- in such a way that it respects the Leibniz rule.


Now we can define curvature:

$$R^E = (\nabla^E)^2$$

> [!Proposition]
> $R^E \in \Omega^2(X, \operatorname{End}(E))$

Proof: Let $f \in \mathcal{C}^\infty(X)$.  Verify that $[R^E, f] = 0$[^3]:

$$[(\nabla^E)^2, f] = [\nabla^E, [\nabla^E, f]] = ddf = 0$$

[^3]: The commutator of $R^E$ and $f$

$\square$

Now let $ f$ be a formal analytic function (there are no convergence conditions). The series $f(R^E)$ is an element of $\Omega^{2 \bullet}(X, \operatorname{End}(E))$. Moreover, $\operatorname{Tr}^E[f(R^E)] \in \Omega^{2 \bullet}(E)$

> [!Proposition]
> - $\operatorname{Tr}[f(\Omega^E)]$ is closed
> - The DeRham cohomology class is independent of the choice of $\nabla^E$.

> [!Lemma]
> For $\alpha \in \Omega^\bullet(X, \operatorname{End}(E))$, $d\operatorname{Tr}^E[\alpha] = \operatorname{Tr}^E[[\nabla^E, \alpha]]$

Now we have $d\operatorname{Tr}[f(R^E)] = \operatorname{Tr}[[\nabla^E, f(R^E)]] = 0$.

Thus, $\operatorname{Tr}[f(\Omega^E)]$ is closed.

To show that the DeRham cohomology class is independent of the choice of $\nabla^E$, we show that 

$$\frac{d}{dt} \operatorname{Tr}[f(r_t^E)] = \operatorname{Tr}[(\frac{d}{dt} \nabla_t^2) f(R_t^E)].$$

The RHS equals 

$$\operatorname{Tr}[[\frac{d}{dt} \nabla_t \nabla_t] f(\nabla_t^2)] = \operatorname{Tr}[[\Delta_t, \frac{d}{dt} \nabla_t f(\nabla_t^2)]] = d \operatorname{Tr}[\frac{d\nabla}{dt} + f'(\nabla_t^2)].$$



...

$\square$

Now let $E \to X$ be a holomorphic vector bundle over a complex manifold. Let $h^E$ be a Hermitian metric on $E$. There exists a unique connection $\nabla^E$ such that $\nabla^{E,0} = \delta$ and $\nabla^E$ is Hermitian with respect to   $h^E$. From now on, write 

$$\operatorname{ch}(E, h^E) = \operatorname{ch}(E, \nabla^E)$$

> [!Main question]
> Let $\pi: X \to B$ be a holomorphic submersion. Also assume that $X$ and $B$ are Kahler. Let $E \to X$ be a vector bundle. Let $h^E$ be a Hermitian metric on $E$. Let $g^{\text{TX}}/B$ be a Kahler metric on the fibers of $\pi$. In other words, $TX/B = TX/ \pi^* TB$.
> 
> Can we find a Hermitian metric $\|\cdot\|$ on $X$ such that
> $$\lambda(E) = \otimes (\det R^i \pi_* E)$$
> satisfies
> $$\operatorname{c}_1(\lambda(E), \|\cdot\|) = \pi_* (\operatorname{Td}(TX/ B, g^{\text{TX}/B}) \operatorname{Ch}(E, h^E))$$
> holds pointwise?

> [!Answer]
> In relative dimension $1$, Quillen 
> ...Bismut-Gillet-Soule


Bismut-Gillet-Soule have a series of three papers 

We call $\| \cdot \| = \| \cdot \|_Q$ the <b style="border-width:1px;border-style:solid;padding:3px" definition="">Quillen norm</b>

# Quillen norm


> [!Definition]
> $\|\cdot\|_Q = \|\cdot \|_{L^2} \cdot \text{Analytic torsion}$

![[Pasted image 20240401155328.png]]

$\lambda(E)_\mathcal{B} = \det H^i(X_\mathcal{B}, E)^{(-1)^i}$

Now fix $Y$ with a Riemannian metric $g^{TY}$ and let $E$ be a vector bundle on $Y$ with a Hermitian metric $h^E$. There is the $L^2$-metric given by

$$\langle s, s' \rangle_{L^2} = \int_y \langle s(X), s'(X) \rangle_{h^E} dv_{g^{\text{TX}}}$$

where $s,s' \in \mathcal{C}^\infty(Y,E)$.

On $H^0(Y,E)$, $\|\cdot\|_{L^2}$ is just the restriction.

# Hodge theory

The Kodaira Laplacian $\square^E$ is given as follows: take $\delta: \Omega^{0,i}(X,E) \to \Omega^{0,i+1}(X,E)$. Define $\square^E_i = \delta^* \delta + \delta \delta^*$. The Kodaira Laplacian preserves the degree of a differential form.

Hodge theory states the following:

 - $\ker \square_i$ is finite dimensional.
 - $\ker \square_i \cong H^i(X,E)$. More precisely, Given $s \in \ker \square_i$, we have $$\langle \square s, s \rangle = \langle \delta s, \delta \rangle \langle \delta^*, \delta^* s \rangle$$...

Proof.

A. Let $\square_i$ be an elliptic operator. For $s \in \mathcal{C}^\infty(X,E)$, $\|s\|_{H^2} \subseteq C \cdot (\|\square \cdot s\|_{L^2} + \| s\|_{L^2})$. In particular, if $\square s = 0$, then $\ker \square_i \cap B_{L^2}(0,1) \subset B_{H^2}(0,C)$ for some constant $C$. We know that $B_{H^2}(0,C)$ embeds compactly into $B(0,C)$.

B. We can decompose

$$\mathcal{C}^\infty(X,E) = \ker \square \oplus_{\perp} \operatorname{Im} \square.$$

It is also the case that 

$$\operatorname{Im} \square = \operatorname{Im} \delta \oplus \operatorname{Im} \delta^*.$$

Moreover, $\operatorname{Im} \delta \subset \ker \delta$ and $\ker \delta \perp \operatorname{Im} \delta^*$, and if $\alpha = \delta^* \beta$, then

$$0 = \langle \delta \delta^* \beta, \beta \rangle = \langle \delta^* \beta,   \delta^* \beta \rangle.$$

# Analytic torsion

Analytic torsion is a spectral invariant of the fibers.

Given $E \to Y$ a vector bundle , $g^{TY}$ a Riemannian metric, and $h^E$ a Hermitian metric, $\square$ is an operator $\Omega^{0,i} (X,E)$ and $\square$ are essentially self-adjoint.


$$\operatorname{Spec}(\square)$$ is discrete, so it consists of positive real numbers $\lambda_1,\ldots,\lambda_n$.


# Weyl's law
Weyl's laws tells you about the growth of the $\lambda_i$'s: 

$$\lambda_i \sim C \cdot \operatorname{vol}(M) \cdot i^{\frac{2}{n}}.$$

# Spin geometry

Let $s$ be an eigenvalue of $\square$. We have 

$$\|s\|_{H^2} \leq (\|\square s\|_{L^2} + \|s\|_{L^2}) \leq c ... \|s\|_{L^2}$$
$$\|s\|_{H^{2k}} \subseteq \Lambda^k \|s\|_{L^2}$$

Now write

$$\det \square = \prod_{i=1}^\infty \lambda_i$$

But this does not make sense because the eigenvalues are growing. We use the zeta function to consolidate this:

$$\zeta(s) = \sum \frac{1}{\lambda_i^s}$$

If converges and is holomorphic for $\operatorname{Re} s > \frac{n}{2}$$

> [!Fact]
> $\zeta$ has a meromorphic extension to $\mathbb{C}$ and $0$ is a holomorphic point of this extension.

This is important because 

$$\zeta'(0) = \sum -\log(\lambda_i)$$

and we can define

$$\det \square := \exp(-\zeta(0)).$$

Roy-Singer made this definition.

The Quillen norm is then defined by

$$\|\cdot\|_Q = \|\cdot\|_{L^2} \cdot T(X_\mathcal{B}, E) = \prod (\det \square_i)^{\frac{i \cdot (-1)^i}{2}}$$

Here, $X \to B$ is a fibration of Kahler manifolds, $g^{\text{TX} / \Delta}$ is a rests of a Kahler metric

> [!Theorem]
> (Quillen, Bismut-Gillet-Soule)
> - $\|\cdot\|_Q$ is smooth 
> - $C_d(\lambda(E), \|\cdot\|_Q) = \pi_* (\operatorname{Td}(TX/B, g^{\text{TX}} ) \operatorname{Ch}(E,h^E))$

> [!Remark]
> RRG is a trivial consequence of this theorem; The above theorem says that certain characters coincide point-by-point whereas RRG is a statement that characters coincide globally.

# Why do we care?

There are a bunch of applications.
- It all started with arithmetic geometry --- with the arithmetic Riemann-Roch theorem of Gillet-Soule, Faltings, Bost
- Related to the theory of automorphic forms (Yoshikawa)
- Applications to mirror symmetry (there is something called BCOV torsion)
- Applications to dynamical systems (Kontsevich-Zorich)
- Applications to probability (Work of Dubidot)


# See Also

# Meta
## References

## Citations and Footnotes