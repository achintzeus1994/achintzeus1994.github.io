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

<h1 id="introduction">Introduction</h1>
<p>Imagine two thermodynamic systems A defined by state variables <span class="math inline">\(\{\mathbf{x}\}\)</span> and parameters <span class="math inline">\(\{\boldsymbol{\theta}\}\)</span>, and B described by state variables <span class="math inline">\(\{\mathbf{z}\}\)</span> and parameters <span class="math inline">\(\{\boldsymbol{\phi}\}\)</span> respectively. We assume that the state of system B determines the state of system A. (Think that X represents the neural activity and Z represents hidden neural activity.) So, the probability of a state {<span class="math inline">\(\mathbf{z}\)</span>} given state {<span class="math inline">\(\mathbf{x}\)</span>} is given by, <span class="math display">\[p_{\theta}(\mathbf{z|x})=\frac{e^{-\beta E(\mathbf{z|x})}}{\mathcal{Z}}\]</span> Here, <span class="math inline">\(\beta=(k_B T)^{-1}\)</span> and <span class="math inline">\(\mathcal{Z}\)</span> is the partition function given by: <span class="math display">\[\begin{aligned}
    \mathcal{Z}=\int e^{-\beta E(\mathbf{z|x})}\, d\mathbf{z}\end{aligned}\]</span> Now, we observe the state of system A and we want to find the parameters that describe system A and B. The general idea is that we would like to minimize the Helmholtz free energy of system B given the observations of system A. The free energy is given by, <span class="math display">\[F=U-TS\]</span> The entropy of system B is given by, <span class="math display">\[S=-k_B \int p_{\theta}(z|x)\mathrm{ln}(p_{\theta}(z|x)) \, dz\]</span> The internal energy of the system B is given by, <span class="math display">\[\begin{aligned}
    U&amp;=\int p_{\theta}(z|x) E(z|x) \, dz \\
    &amp;=\int p_{\theta}(z|x) E(z|x) \, dz \\
    &amp;=-\frac{1}{\beta}\int p_{\theta}(z|x)\mathrm{ln}(p_{\theta}(z|x))  \, dz-\frac{\mathrm{ln}(\mathcal{Z})}{\beta}\\
    &amp;=-\frac{1}{\beta}\int p_{\theta}(z|x)\mathrm{ln}\left[\frac{p_{\theta}(x,z)}{p_{\theta}(x)}\right]  \, dz-\frac{\mathrm{ln}(\mathcal{Z})}{\beta}\\
    &amp;=-\frac{1}{\beta}\int p_{\theta}(z|x)\mathrm{ln}(p_{\theta}(x,z))  \, dz+\frac{\mathrm{ln}(p_{\theta}(x))-\mathrm{ln}(\mathcal{Z})}{\beta}\end{aligned}\]</span> Since, <span class="math inline">\(\mathcal{Z}=p_{\theta}(x)\)</span>, the second term cancels out. Assuming <span class="math inline">\(\beta=1\)</span>, we find <span class="math display">\[\begin{aligned}
    F(x)=-\int p_{\theta}(z|x)\mathrm{ln}(p_{\theta}(x,z))\, dz+\int p_{\theta}(z|x)\mathrm{ln}(p_{\theta}(z|x)) \, dz\end{aligned}\]</span> Since the posterior is intractable <span class="math inline">\(p_{\theta}(z|x)\)</span> we approximate it by <span class="math inline">\(q_{\phi}(z|x)\)</span> to get variational Helmholtz free energy, <span class="math display">\[F[q_{\phi}(z|x)]=-\int q_{\phi}(z|x)\mathrm{ln}(p_{\theta}(x,z))\, dz+\int q_{\phi}(z|x)\mathrm{ln}(q_{\phi}(z|x)) \, dz\]</span> We vary <span class="math inline">\(q_{\phi}(z|x)\)</span> to find the minimum of the above functional. The negative of the above expression is called ELBO. We thus have, <span class="math display">\[\begin{aligned}
    \mathrm{ELBO}&amp;=\mathbb{E}_{q_{\phi}(z|x)}[\mathrm{ln}(p_{\theta}(x,z))]-\mathbb{E}_{q_{\phi}(z|x)}[\mathrm{ln}(q_{\phi}(z|x))]\\
    &amp;=\mathbb{E}_{q_{\phi}(z|x)}[\mathrm{ln}(p_{\theta}(z)p_{\theta}(x|z))]-\mathbb{E}_{q_{\phi}(z|x)}[\mathrm{ln}(q_{\phi}(z|x))]\\
    &amp;=\mathbb{E}_{q_{\phi}(z|x)}[p_{\theta}(x|z))]+\mathbb{E}_{q_{\phi}(z|x)}\left[\mathrm{ln}\frac{p_{\theta}(z)}{q_{\phi}(z|x))}\right]\\
    &amp;=-D_{KL}(q_{\phi}(z|x)||p_{\theta}(z))+\mathbb{E}_{q_{\phi}(z|x)}[\mathrm{ln}(p_{\theta}(x|z))]\end{aligned}\]</span></p>
<p>We assume, <span class="math inline">\(q_{\phi}(\mathbf{z|x}) \sim \mathcal{N}(\boldsymbol{\mu,\sigma}^2\mathbf{I})\)</span>, <span class="math inline">\(p_{\theta}(\mathbf{z})\sim \mathcal{N}(\boldsymbol{0,\mathbf{I}})\)</span> so the first term becomes <span class="math display">\[\begin{aligned}
    D_{KL}(q_{\phi}(z|x)||p_{\theta}(z))&amp;=\frac{1}{2}\sum_{j}[\mu_j^2+\sigma^2_j-\mathrm{ln}(\sigma^2_j)-1]\end{aligned}\]</span> We further assume that <span class="math inline">\(p_{\theta}(x|z))\)</span> is Bernoulli or Gaussian depending on the type of data. For Gaussian case, <span class="math inline">\(p_{\theta}(x|z)) \sim \mathcal{N}(\boldsymbol{\mu,\sigma^2 \mathbf{I}})\)</span>. So, we get, <span class="math display">\[\begin{aligned}
    \mathrm{log}[p_{\theta}(x|z))]=-\frac{(x-\mu)^2}{2\sigma^2}-\frac{\mathrm{log}[2\pi\sigma^2]}{2}\end{aligned}\]</span> The <span class="math inline">\(p_{\theta}(x|z))\)</span> is Bernoulli <span class="math display">\[\begin{aligned}
    \mathrm{log}[p_{\theta}(x|z))]=\sum_i x_i\mathrm{log}[y_i]+(1-x_i)\mathrm{log}[1-y_i]\end{aligned}\]</span> The second term is estimated by calculating the binary cross entropy between the reconstruction(<span class="math inline">\(\mathbf{\hat{x}}\)</span>) and <span class="math inline">\(\mathbf{x}\)</span></p>
