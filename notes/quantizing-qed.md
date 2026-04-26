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

A "pure-gauge direction" means a change in $A_\mu$ that only moves us along a gauge orbit, not to a new physical field. In position space this direction is

$$
\delta A_\mu(x)=\partial_\mu\lambda(x).
$$

Fourier transform $\lambda(x)$ as

$$
\lambda(x)=\int\frac{d^4p}{(2\pi)^4}\lambda(p)e^{-ip\cdot x}.
$$

Then

$$
\partial_\mu\lambda(x)
=\int\frac{d^4p}{(2\pi)^4}(-ip_\mu)\lambda(p)e^{-ip\cdot x}.
$$

Ignoring the conventional factor of $-i$, the gauge direction in momentum space is proportional to

$$
\delta A_\mu(p)\propto p_\mu\alpha(p),
$$

where $\alpha(p)$ is just the Fourier coefficient of the gauge parameter. So "acting on a pure-gauge direction" means applying the kinetic operator to this longitudinal vector. Explicitly,

$$
(p^2 \eta^{\mu \nu}-p^{\mu}p^{\nu})p_{\mu}\alpha(p)
=(p^2p^{\nu}-p^2p^{\nu})\alpha(p)=0.
$$

This is the zero-mode problem in one line: the operator kills longitudinal vectors. Since a matrix/operator with nonzero vectors in its kernel cannot be inverted, the photon propagator is undefined until we fix gauge.

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

Here $G$ is a functional that takes a gauge field and returns the quantity we want to set to zero. The equation

$$
G(A)=0
$$

selects one representative from each gauge orbit. Geometrically, the set of all fields satisfying $G(A)=0$ is a "slice" through the space of gauge-equivalent fields.

Why impose this? Because without it, the path integral includes every field $A_\mu$ and also every shifted field $A_\mu+\partial_\mu\lambda$, even though they describe the same electromagnetic field strength $F_{\mu\nu}$. Gauge fixing keeps one copy and removes the redundant copies.

For Lorenz gauge,

$$
G(A)=\partial_\mu A^\mu.
$$

So $G(A)=0$ means

$$
\partial_\mu A^\mu=0.
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

Now take the functional derivative with respect to $\lambda(y)$. The identity being used is

$$
\frac{\delta\lambda(x)}{\delta\lambda(y)}=\delta^4(x-y).
$$

Derivatives with respect to $x$ commute through the functional derivative:

$$
\frac{\delta\,\partial_\mu\lambda(x)}{\delta\lambda(y)}
=\partial_\mu^x\delta^4(x-y),
$$

and therefore

$$
\frac{\delta\,\partial^2\lambda(x)}{\delta\lambda(y)}
=\partial_x^2\delta^4(x-y).
$$

Applying this to $G(A^\lambda)(x)$ gives

$$
\frac{\delta G(A^\lambda)(x)}{\delta\lambda(y)}
=\partial_x^2\delta^4(x-y).
$$

The $\partial_\mu A^\mu$ term drops out because it does not depend on $\lambda$:

$$
\frac{\delta}{\delta\lambda(y)}\partial_\mu A^\mu(x)=0.
$$

So the Faddeev-Popov operator is the kernel

$$
M(x,y)=\frac{\delta G(A^\lambda)(x)}{\delta\lambda(y)}
=\partial_x^2\delta^4(x-y).
$$

The Faddeev-Popov determinant is the determinant of this operator:

$$
\Delta_{FP}[A]=\det M
=\det\left[\partial_x^2\delta^4(x-y)\right].
$$

Because the delta function is the identity kernel for functional multiplication, this is usually written compactly as

$$
\Delta_{FP}[A]=\det(\partial^2).
$$

In momentum space, $\partial^2$ is diagonal:

$$
\partial^2 \longrightarrow -p^2.
$$

So formally,

$$
\det(\partial^2)=\prod_p(-p^2),
$$

up to the usual regulator and normalization choices. The important simplification is that this determinant contains no $A_\mu$.

### What are ghost fields?

Ghost fields are a computational device for representing the Faddeev-Popov determinant inside the path integral. They are not new physical particles in QED. They are auxiliary anticommuting fields, usually written $c(x)$ and $\bar{c}(x)$, whose only job is to reproduce the determinant coming from gauge fixing.

The identity behind this is the Grassmann Gaussian integral. For ordinary commuting variables, a Gaussian integral gives an inverse determinant:

$$
\int d^n x\,\exp\left(-x_i A_{ij}x_j\right)\propto \frac{1}{\sqrt{\det A}}.
$$

For anticommuting Grassmann variables $\bar{\psi}_i,\psi_i$, the Gaussian gives a determinant instead:

$$
\int \prod_i d\bar{\psi}_i\,d\psi_i\,
\exp\left(-\bar{\psi}_i A_{ij}\psi_j\right)
=\det A.
$$

The field-theory version replaces the matrix $A_{ij}$ by a differential operator. In QED the Faddeev-Popov operator is

$$
M=\partial^2.
$$

So we may rewrite

$$
\det(\partial^2)=\int[d\bar{c}][dc]\,
\exp\left(i\int d^4x\,\bar{c}\,\partial^2c\right),
$$

up to convention-dependent signs and normalization constants. The corresponding ghost Lagrangian is

$$
\mathcal{L}_{ghost}=\bar{c}\,\partial^2 c.
$$

This has no $A_\mu$ in it, so the ghosts are free fields with no photon interaction. In perturbation theory that means there are no QED ghost-photon vertices. The ghost determinant is just an overall constant in the free abelian theory, so it cancels from normalized expectation values.

This is very different from non-abelian Yang-Mills theory. There the gauge transformation contains a field-dependent term,

$$
A_\mu^a\to A_\mu^a + D_\mu^{ab}\lambda^b,
$$

so the Faddeev-Popov operator contains $A_\mu^a$. The ghost Lagrangian then contains ghost-gauge-field interactions, and ghosts become essential for preserving gauge invariance and unitarity in loop calculations.

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
