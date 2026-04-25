# String Theory - Zweibach

These notes follow the early arc of Barton Zwiebach's string theory treatment: start with the relativistic point particle, replace a worldline with a worldsheet, use gauge symmetry to simplify the dynamics, and then quantize the remaining physical oscillators. The big idea is beautifully economical: a string is not a particle with extra decoration. A particle is the limiting case of an object whose history is a line; a string's history is a two-dimensional surface.

## Relativistic Free Particle Action

Before writing a string action, it helps to remember how a free relativistic particle is described. The action should count invariant length in spacetime, so it should not depend on the particular parameter we use to trace the worldline.

1. With coordinate time:

$$
S=-m\int dt\sqrt{1-v^2}
$$

This form is intuitive: the particle extremizes proper time. It is also a little awkward because it singles out coordinate time $t$.

2. With an arbitrary worldline parameter:

$$
S=-m\int d\tau \sqrt{-\dot{x}^2},\qquad \dot{x}^2=\eta_{\mu\nu}\dot{x}^{\mu}\dot{x}^{\nu}
$$

Here $\tau$ is any parameter along the trajectory, not necessarily proper time. The square root makes the action invariant under reparameterizations $\tau\to \tilde{\tau}(\tau)$.

3. With an einbein:

$$
S=\frac{1}{2}\int d\tau \left(e^{-1}\dot{x}^2-em^2\right),\qquad \dot{x}^2=\eta_{\mu\nu}\dot{x}^{\mu}\dot{x}^{\nu}
$$

The scalar density $e(\tau)$ is the one-dimensional analogue of a metric on the worldline. It linearizes the square root and also behaves well for $m=0$, where the square-root action is less convenient.

Varying $e(\tau)$ gives the constraint

$$
\dot{x}^2+e^2m^2=0.
$$

Varying $x^{\mu}$ gives

$$
\frac{d}{d\tau}\left(\frac{1}{e}\dot{x}_{\mu}\right)=0.
$$

In the gauge $e=1/m$, this is just straight-line motion with constant momentum. The lesson is the one we will reuse for strings: introduce an auxiliary metric-like variable, then use its equation of motion to recover the geometric square-root action.

## Relativistic Free String Action

A particle sweeps out a worldline. A string sweeps out a worldsheet, parameterized by $(\tau,\sigma)$ and embedded in spacetime by $X^\mu(\tau,\sigma)$. The parameter $\tau$ plays the role of worldsheet time, while $\sigma$ labels points along the string.

### Nambu-Goto Action

$$
S=-T\int d\tau d\sigma\sqrt{(\dot{X}\cdot X')^2-\dot{X}^2X'^2}.
$$

Here $\dot{X}=\partial_\tau X$, $X'=\partial_\sigma X$, and $T$ is the string tension. This action is the area of the worldsheet multiplied by $-T$, just as the point-particle action is the length of the worldline multiplied by $-m$.

The tension is usually written in terms of the Regge slope $\alpha'$:

$$
T=\frac{1}{2\pi\alpha'}.
$$

Large tension means a stiff string; large $\alpha'$ means a more easily excited string.

### Polyakov Action

$$
S=-\frac{T}{2}\int d\tau d\sigma \sqrt{-h}\,h^{\alpha\beta}\partial_{\alpha}X^{\mu}\partial_{\beta}X^{\nu}\eta_{\mu\nu}.
$$

The Polyakov action introduces an independent worldsheet metric $h_{\alpha\beta}$. Classically, eliminating $h_{\alpha\beta}$ by its equation of motion gives the Nambu-Goto action. The advantage is enormous: the Polyakov form is quadratic in $X^\mu$, so the equations of motion become wave equations after gauge fixing.

## Symmetries of the Polyakov Action

- Poincare invariance: The target spacetime coordinates transform as $X^\mu\to \Lambda^\mu_{\ \nu}X^\nu+a^\mu$. This is ordinary spacetime symmetry.
- Reparameterization invariance: The worldsheet coordinates $(\tau,\sigma)$ can be relabeled without changing physics. This is two-dimensional diffeomorphism invariance.
- Weyl invariance: The worldsheet metric can be locally rescaled, $h_{\alpha\beta}\to e^{2\omega(\tau,\sigma)}h_{\alpha\beta}$, without changing the classical action.

The last two symmetries are what make string theory special. Together they let us remove the unphysical parts of the worldsheet metric. In two dimensions, "metric geometry" becomes mostly gauge.

## Conformal Gauge

Using reparameterization plus Weyl invariance, we can choose conformal gauge:

$$
h_{\alpha\beta}=\eta_{\alpha\beta}.
$$

This makes the worldsheet metric flat locally and simplifies the equation of motion to

$$
\Box X^{\mu}=(\partial_\tau^2-\partial_\sigma^2)X^{\mu}=0.
$$

This is the 1+1 dimensional wave equation, whose general local solution is

$$
X^{\mu}(\tau,\sigma)=X_L^{\mu}(\tau+\sigma)+X_R^{\mu}(\tau-\sigma).
$$

$X_L^\mu$ and $X_R^\mu$ are left-moving and right-moving waves on the string. The string is literally made of waves, and the different standing or traveling wave patterns are what later appear as different particle states.

Conformal gauge does not remove every constraint. The stress tensor must still vanish:

$$
T_{\alpha\beta}=0.
$$

In light-cone coordinates $\sigma^\pm=\tau\pm\sigma$, this becomes

$$
(\partial_+X)^2=0,\qquad (\partial_-X)^2=0.
$$

These are the Virasoro constraints. They remove negative-norm excitations and connect the oscillator modes to the spacetime mass spectrum.

## Open and Closed String Solutions

- For closed strings, waves can travel clockwise and counter-clockwise around the loop. The left- and right-moving sectors are independent, except for a matching condition called level matching.
- For open strings, waves reflect at the endpoints. The boundary conditions tie left- and right-moving waves together, producing standing wave modes.

Boundary conditions are not a side detail; they decide what kind of object the string endpoint can touch. Neumann conditions mean an endpoint is free to move in that direction. Dirichlet conditions mean it is fixed to a surface, which is the seed of D-branes.

## Light-Cone Gauge

Light-cone gauge solves the constraints explicitly by using coordinates

$$
X^\pm=\frac{1}{\sqrt{2}}(X^0\pm X^{D-1}).
$$

One chooses $X^+$ to be proportional to worldsheet time. Then $X^-$ is determined by the constraints, leaving only the transverse coordinates

$$
X^I(\tau,\sigma),\qquad I=1,\dots,D-2
$$

as independent physical degrees of freedom. This is why the transverse oscillator number operator is central:

$$
N^{\perp}=\sum_{n=1}^{\infty}\alpha^{I}_{-n}\alpha^{I}_{n}.
$$

Each oscillator $\alpha^I_{-n}$ creates a quantum of vibration with mode number $n$ and transverse polarization $I$.

## Open String

For an open string, take $\sigma\in[0,\pi]$.

### Neumann Boundary Conditions

Free endpoints obey

$$
\partial_{\sigma}X^{\mu}(\tau,0)=\partial_{\sigma}X^{\mu}(\tau,\pi)=0.
$$

The mode expansion is

$$
X^{\mu}(\tau,\sigma)=x_0^{\mu}+\sqrt{2\alpha'}\alpha_0^{\mu}\tau+i\sqrt{2\alpha'}\sum_{n \neq 0}\frac{1}{n}\alpha_n^{\mu}e^{-in\tau}\cos n\sigma.
$$

The cosine appears because Neumann boundary conditions require the derivative in the $\sigma$ direction to vanish at both endpoints.

Canonical quantization gives

$$
[\alpha^I_m,\alpha^J_n]=m\delta_{m+n,0}\delta^{IJ}.
$$

The open-string mass formula is

$$
M^2=-p^{\mu}p_{\mu}=\frac{1}{\alpha'}(N^{\perp}-1).
$$

The constant $-1$ is the normal-ordering intercept in bosonic string theory. It gives a tachyonic ground state at $N^\perp=0$, while the first excited level $N^\perp=1$ is massless.

That first excited state has the form

$$
\alpha^I_{-1}|0;p\rangle.
$$

It transforms like a vector in spacetime. In more complete string theories, this is the beginning of gauge particles appearing as vibrational modes.

The transverse Virasoro operators are

$$
L_{n}^{\perp}=\frac{1}{2}\sum_{p=-\infty}^{\infty}\alpha^{I}_{n-p}\alpha^{I}_{p}\qquad (n\neq 0),
$$

and

$$
L_{0}^{\perp}=\alpha'p^{I}p^{I}+N^{\perp}.
$$

Their commutator is

$$
[L_{m}^{\perp},L_{n}^{\perp}]=(m-n)L_{m+n}^{\perp}+\frac{D-2}{12}(m^3-m)\delta_{m+n,0}.
$$

The central term is the quantum residue of the infinitely many oscillator modes. Requiring Lorentz symmetry after quantization fixes the bosonic string's critical dimension:

$$
D=26.
$$

## Closed String

For a closed string, take $\sigma\in[0,2\pi]$ with periodicity

$$
X^{\mu}(\tau,\sigma+2\pi)=X^{\mu}(\tau,\sigma).
$$

The closed string has two independent oscillator families, one left-moving and one right-moving:

$$
X^{\mu}(\tau,\sigma)=x_0^{\mu}+\sqrt{2\alpha'}\alpha_0^{\mu}\tau
+i\sqrt{\frac{\alpha'}{2}}\sum_{n\neq 0}\frac{1}{n}\left(
\alpha_n^\mu e^{-in(\tau-\sigma)}
+\tilde{\alpha}_n^\mu e^{-in(\tau+\sigma)}
\right).
$$

The oscillator algebra is

$$
[\alpha^I_m,\alpha^J_n]=m\delta_{m+n,0}\delta^{IJ},\qquad
[\tilde{\alpha}^I_m,\tilde{\alpha}^J_n]=m\delta_{m+n,0}\delta^{IJ},
$$

with left and right oscillators commuting with each other.

The number operators are

$$
N^\perp=\sum_{n=1}^{\infty}\alpha^I_{-n}\alpha^I_n,\qquad
\tilde{N}^\perp=\sum_{n=1}^{\infty}\tilde{\alpha}^I_{-n}\tilde{\alpha}^I_n.
$$

The closed-string mass formula is

$$
M^2=\frac{2}{\alpha'}\left(N^\perp+\tilde{N}^\perp-2\right),
$$

with the level-matching condition

$$
N^\perp=\tilde{N}^\perp.
$$

The first excited closed-string level is

$$
\alpha^I_{-1}\tilde{\alpha}^J_{-1}|0;p\rangle.
$$

The product of two vector polarizations decomposes into three pieces:

- a symmetric traceless tensor $G_{\mu\nu}$, interpreted as the graviton;
- an antisymmetric tensor $B_{\mu\nu}$;
- a scalar trace part $\Phi$, called the dilaton.

This is one of the most striking moments in perturbative string theory: a quantum theory of one-dimensional extended objects automatically contains a massless spin-2 excitation. In spacetime language, that is gravity.

## Big Picture

The early structure of string theory can be summarized as a ladder:

1. A relativistic particle extremizes worldline length.
2. A relativistic string extremizes worldsheet area.
3. The Polyakov action replaces the area square root with a two-dimensional metric.
4. Gauge symmetries reduce the dynamics to transverse waves.
5. Quantized waves become particle states.
6. Open strings naturally give vector-like states; closed strings naturally give gravity-like states.

The formal machinery can feel heavy, but the intuition is clean: particles are notes played by a string. Mass, spin, and interaction type are not separate ingredients added by hand; they arise from the allowed vibrational patterns.
