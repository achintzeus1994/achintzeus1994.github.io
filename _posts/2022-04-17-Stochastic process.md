---
title: 'Stochastic Processes'
date: 2022-04-17
permalink: /posts/2022/04/SP/
tags:
  - Physics
---
<!-- MathJax -->
<script type="text/javascript"
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.3/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>


<h1 id="stratonovich-integral">Stratonovich Integral</h1>
<p>The Ito integral is given by <span
class="math display">\[\begin{aligned}
    \int_0^T F&#39;(B_t)dB_t=F(B_T)-F(B_0)-\frac{1}{2}\int_0^T
F&#39;&#39;(B_t)dt\end{aligned}\]</span> To get to Stratonovich
integral, we replace the left hand side by the Stratonovich
interpretation, <span class="math display">\[\begin{aligned}
    \int_0^T F&#39;(B_t)\circ dB_t :=\int_0^T
F&#39;\left(\frac{B_t+B_{t+dt}}{2}\right)
dB_t=\int_0^TF&#39;\left(B_t+\frac{dB_{t}}{2}\right)
dB_t.\end{aligned}\]</span> On using Taylor expansion and the fact that
<span class="math inline">\(dB_tdB_t=dt\)</span>, we get, <span
class="math display">\[\begin{aligned}
    \int_0^T F&#39;\left(B_t+\frac{dB_{t}}{2}\right) dB_t= \int_0^T
F&#39;(B_t)dB_t+\frac{1}{2}\int_0^T F&#39;&#39;(B_t)
dt\end{aligned}\]</span> Substituting equation 1 into the above
expression gives the final expression for the Stratonovich integral,
<span class="math display">\[\begin{aligned}
    \int_0^T F&#39;(B_t)\circ dB_t =
F(B_T)-F(B_0)\end{aligned}\]</span></p>
<h1 id="forwardbackward-kolmogorov-equation">Forward/Backward Kolmogorov
Equation</h1>
<p>Consider the stochastic differential equation, <span
class="math display">\[\begin{aligned}
    dx_t=f(x_t,t)dt+g(x_t,t)dw_t\end{aligned}\]</span> Let us use a
function of the random variable <span
class="math inline">\(h(x_t)\)</span>, then the Taylor equation gives
us, <span class="math display">\[\begin{aligned}
    dh(x_t)=\left(\frac{\partial h(x_t)}{\partial
x_t}f(x_t,t)+\frac{g^2(x_t,t)}{2}\frac{\partial^2 h(x_t)}{\partial
x_t^2}\right)dt+\left(\frac{\partial h(x_t)}{\partial
x_t}g(x_t,t)\right)dw_t\end{aligned}\]</span> Taking average with
respect to <span class="math inline">\(p(x,t|x_0,t_0)\)</span> gives,
<span class="math display">\[\begin{aligned}
    \langle \frac{dh(x_t)}{dt} \rangle = \langle \left(\frac{\partial
h(x_t)}{\partial x_t}f(x_t,t)+\frac{g^2(x_t,t)}{2}\frac{\partial^2
h(x_t)}{\partial x_t^2}\right) \rangle\end{aligned}\]</span> Using
integration by parts, we get the forward Kolmogorov
equation(Fokker-Planck equation), <span
class="math display">\[\begin{aligned}
    \frac{\partial p(x,t)}{\partial t}=-\frac{\partial
[f(x,t)p(x,t)]}{\partial
x}+\frac{1}{2}\frac{\partial^2[g^2(x,t)p(x,t)]}{\partial
x^2}\end{aligned}\]</span> The Kolmogorov backward equation is given by,
<span class="math display">\[\begin{aligned}
    -\frac{\partial p(x_T,T|x,t)}{\partial t}=f(x,t)\frac{\partial
[p(x_T,T|x,t)]}{\partial
x}+\frac{g^2(x,t)}{2}\frac{\partial^2[p(x_T,T|x,t)]}{\partial
x^2}\end{aligned}\]</span> This equation is valid for <span
class="math inline">\(t\leq T\)</span>, with final condition, <span
class="math inline">\(x(T)=x_T\)</span>.</p>
<p>Some questions:</p>
<ul>
<li><p>What happens after <span class="math inline">\(t&gt;
T\)</span>?</p></li>
<li><p>How to derive it using Feynman-Kac formula?</p></li>
</ul>
