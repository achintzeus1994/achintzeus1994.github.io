# Quantizing QED

The goal is to make sense of the photon path integral

$$
\mathcal{Z}= \int [dA]e^{iS[A]}.
$$

For free QED, or equivalently the Maxwell field without charged matter,

$$
\mathcal{Z}=\int [dA]\exp\left[i\int d^4x\left(-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}\right)\right].
$$

After integrating by parts and dropping boundary terms, the action can be written as a quadratic form:

$$
S=\int d^4x\,\mathcal{L}
=\frac{1}{2}\int d^4x\,A_{\mu}
\left(\partial ^2\eta^{\mu\nu}-\partial ^{\mu}\partial^{\nu}\right)A_{\nu}.
$$

Define the kinetic operator

$$
\mathcal{O}^{\mu\nu}=\partial ^2\eta^{\mu\nu}-\partial ^{\mu}\partial^{\nu}.
$$

To compute correlation functions, we need the photon Green's function:

$$
\mathcal{O}^{\mu\nu}D_{\nu\rho}^F(x,y)=i\delta_{\rho}^{\mu}\delta^{4}(x-y).
$$

But there is a problem: no inverse exists yet. The operator has zero modes because the Maxwell action is gauge invariant under

$$
A_\mu(x)\to A_\mu^\lambda(x)=A_\mu(x)+\partial_\mu\lambda(x).
$$

In momentum space,

$$
\partial ^2\eta^{\mu\nu}-\partial ^{\mu}\partial^{\nu}
\longrightarrow p^2 \eta^{\mu \nu}-p^{\mu}p^{\nu}.
$$

Acting on a pure-gauge direction $p_\mu\alpha(p)$ gives

$$
(p^2 \eta^{\mu \nu}-p^{\mu}p^{\nu})p_{\mu}\alpha(p)
=(p^2p^{\nu}-p^2p^{\nu})\alpha(p)=0.
$$

So the path integral is trying to integrate over infinitely many physically identical configurations. The Faddeev-Popov procedure is the clean way to divide out this gauge redundancy.

## Faddeev-Popov Procedure

### 1. Delta Functional Warm-Up

For an ordinary variable, if $y=y(x)$ has a simple zero, then

$$
1=\int dy\,\delta(y)=\int dx\,\delta(y(x))\left|\frac{dy}{dx}\right|.
$$

The functional version is the same idea:

$$
1=\int [d\lambda]\,
\delta[G(A^\lambda)]
\det\left(\frac{\delta G(A^\lambda)}{\delta\lambda}\right).
$$

Here $G(A)=0$ is the gauge condition. For Lorenz gauge,

$$
G(A)=\partial_\mu A^\mu.
$$

The determinant is the Jacobian for changing variables from the gauge parameter $\lambda$ to the gauge-fixing function $G(A^\lambda)$. It counts how the gauge slice cuts through each gauge orbit.

### 2. Insert the Identity

Start with the gauge-redundant partition function:

$$
\mathcal{Z}=\int[dA]\,e^{iS[A]}.
$$

Insert the Faddeev-Popov identity:

$$
\mathcal{Z}
=\int[dA][d\lambda]\,
\delta[G(A^\lambda)]
\det\left(\frac{\delta G(A^\lambda)}{\delta\lambda}\right)
e^{iS[A]}.
$$

Since the Maxwell action and the path-integral measure are gauge invariant,

$$
S[A^\lambda]=S[A],
\qquad
[dA^\lambda]=[dA].
$$

The integral over $[d\lambda]$ is just the volume of the gauge group. It is infinite, but it is also an overall constant, so it is removed from normalized correlation functions. What remains is the gauge-fixed path integral:

$$
\mathcal{Z}
=\int[dA]\,
\delta[G(A)]
\det\left(\frac{\delta G(A^\lambda)}{\delta\lambda}\right)
e^{iS[A]}.
$$

### 3. Evaluate the Determinant for QED

For QED,

$$
A_\mu^\lambda=A_\mu+\partial_\mu\lambda.
$$

Therefore

$$
G(A^\lambda)
=\partial_\mu A^{\lambda\mu}
=\partial_\mu A^\mu+\partial^2\lambda.
$$

Taking the functional derivative gives

$$
\frac{\delta G(A^\lambda)(x)}{\delta\lambda(y)}
=\partial_x^2\delta^4(x-y).
$$

So the Faddeev-Popov determinant is

$$
\Delta_{FP}[A]
=\det(\partial^2).
$$

The important simplification is that this determinant is independent of $A_\mu$. In abelian QED, the ghosts decouple. If we introduce ghost fields anyway,

$$
\det(\partial^2)=\int[d\bar{c}][dc]\,
\exp\left(i\int d^4x\,\bar{c}\,\partial^2c\right),
$$

they are free fields with no photon interaction. This is very different from non-abelian Yang-Mills theory, where the determinant depends on $A_\mu$ and ghosts interact.

### 4. Replace the Sharp Gauge Slice by a Gaussian Average

The delta function imposes the exact Lorenz gauge condition $\partial_\mu A^\mu=0$. More generally, choose

$$
G(A)=\partial_\mu A^\mu-f(x),
$$

and average over the arbitrary function $f(x)$ with a Gaussian weight:

$$
\int[df]\,
\exp\left[-\frac{i}{2\xi}\int d^4x\,f(x)^2\right].
$$

Because the result is independent of the particular gauge slice, this averaging only changes the normalization. Using the delta functional to set $f=\partial_\mu A^\mu$ gives the covariant gauge-fixed partition function:

$$
\mathcal{Z}
=\int[dA]\,\det(\partial^2)\,
\exp\left(i\int d^4x\,\mathcal{L}_{FP}\right).
$$

The gauge-fixed Lagrangian is

$$
\mathcal{L}_{FP}
=-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}
-\frac{1}{2\xi}(\partial_\mu A^{\mu})^2.
$$

Here $\xi$ is the gauge parameter. Different $\xi$ values change the propagator, but not gauge-invariant observables.

## The Gauge-Fixed Photon Propagator

The quadratic action is now invertible. The kinetic operator becomes

$$
\mathcal{O}^{\mu\nu}_\xi
=\partial ^2\eta^{\mu\nu}
-\left(1-\frac{1}{\xi}\right)\partial ^{\mu}\partial^{\nu}.
$$

In momentum space, using the usual $i\epsilon$ prescription, the Feynman propagator is

$$
D_{\mu\nu}^F(p)
=\frac{-i}{p^2+i\epsilon}
\left[
\eta_{\mu\nu}
-(1-\xi)\frac{p_\mu p_\nu}{p^2+i\epsilon}
\right].
$$

Two common choices are:

- Feynman gauge: $\xi=1$, so

$$
D_{\mu\nu}^F(p)=\frac{-i\eta_{\mu\nu}}{p^2+i\epsilon}.
$$

- Landau gauge: $\xi\to 0$, so the propagator is transverse:

$$
p^\mu D_{\mu\nu}^F(p)=0.
$$

## Intuition

The original photon kinetic operator fails because it tries to invert directions that are not physical: pure gauge fluctuations. The Faddeev-Popov trick inserts a clever form of $1$ into the path integral, picks one representative per gauge orbit, and supplies the correct Jacobian. For QED that Jacobian is field independent, so ghosts are harmless spectators. The payoff is the gauge-fixed propagator, which is what we need for perturbation theory.
