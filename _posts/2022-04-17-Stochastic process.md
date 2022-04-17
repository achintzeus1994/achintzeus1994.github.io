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


# Stratonovich Integral

The Ito integral is given by
$$\\begin{aligned}
    \\int_0^T F'(B_t)dB_t=F(B_T)-F(B_0)-\\frac{1}{2}\\int_0^T F''(B_t)dt\\end{aligned}$$
To get to Stratonovich integral, we replace the left hand side by the
Stratonovich interpretation,
$$\\begin{aligned}
    \\int_0^T F'(B_t)\\circ dB_t :=\\int_0^T F'\\left(\\frac{B_t+B\_{t+dt}}{2}\\right) dB_t=\\int_0^TF'\\left(B_t+\\frac{dB\_{t}}{2}\\right) dB_t.\\end{aligned}$$
On using Taylor expansion and the fact that
*d**B*<sub>*t*</sub>*d**B*<sub>*t*</sub> = *d**t*, we get,
$$\\begin{aligned}
    \\int_0^T F'\\left(B_t+\\frac{dB\_{t}}{2}\\right) dB_t= \\int_0^T F'(B_t)dB_t+\\frac{1}{2}\\int_0^T F''(B_t) dt\\end{aligned}$$
Substituting equation 1 into the above expression gives the final
expression for the Stratonovich integral,
$$\\begin{aligned}
    \\int_0^T F'(B_t)\\circ dB_t = F(B_T)-F(B_0)\\end{aligned}$$

# Forward/Backward Kolmogorov Equation

Consider the stochastic differential equation,
$$\\begin{aligned}
    dx_t=f(x_t,t)dt+g(x_t,t)dw_t\\end{aligned}$$
Let us use a function of the random variable *h*(*x*<sub>*t*</sub>),
then the Taylor equation gives us,
$$\\begin{aligned}
    dh(x_t)=\\left(\\frac{\\partial h(x_t)}{\\partial x_t}f(x_t,t)+\\frac{g^2(x_t,t)}{2}\\frac{\\partial^2 h(x_t)}{\\partial x_t^2}\\right)dt+\\left(\\frac{\\partial h(x_t)}{\\partial x_t}g(x_t,t)\\right)dw_t\\end{aligned}$$
Taking average with respect to
*p*(*x*,*t*\|*x*<sub>0</sub>,*t*<sub>0</sub>) gives,
$$\\begin{aligned}
    \\langle \\frac{dh(x_t)}{dt} \\rangle = \\langle \\left(\\frac{\\partial h(x_t)}{\\partial x_t}f(x_t,t)+\\frac{g^2(x_t,t)}{2}\\frac{\\partial^2 h(x_t)}{\\partial x_t^2}\\right) \\rangle\\end{aligned}$$
Using integration by parts, we get the forward Kolmogorov
equation(Fokker-Planck equation),
$$\\begin{aligned}
    \\frac{\\partial p(x,t)}{\\partial t}=-\\frac{\\partial \[f(x,t)p(x,t)\]}{\\partial x}+\\frac{1}{2}\\frac{\\partial^2\[g^2(x,t)p(x,t)\]}{\\partial x^2}\\end{aligned}$$
The Kolmogorov backward equation is given by,
$$\\begin{aligned}
    -\\frac{\\partial p(x_T,T\|x,t)}{\\partial t}=f(x,t)\\frac{\\partial \[p(x_T,T\|x,t)\]}{\\partial x}+\\frac{g^2(x,t)}{2}\\frac{\\partial^2\[p(x_T,T\|x,t)\]}{\\partial x^2}\\end{aligned}$$
This equation is valid for *t* ≤ *T*, with final condition,
*x*(*T*) = *x*<sub>*T*</sub>.

Some questions:

-   What happens after *t* \> *T*?

-   How to derive it using Feynman-Kac formula?
