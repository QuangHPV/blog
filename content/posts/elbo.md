+++
date = '2025-11-28T11:24:10+08:00'
draft = true
title = 'ELBO'
+++
# Variational Inference
Variation Inference takes a different approach from sampling, instead formulate the inference problem as an optimization one. 
- Basically, given a distribution $p(x)$ whose marginal/MAP are intractable, we choose a simpler family of distribution $q\in \mathcal{Q}$ whose marginal *IS* tractable. 
- Then we minimize the divergence between the 2 distribution , so that we may use $q$’s inference result as an approximate to $p$’s.

What’s being optimized: Support $q\in \mathcal{Q}$ is generally defined by a distribution parameterized by $\theta$. Then we optimize the following quantity
$$D_{KL}(q\|p)=\int q(x)\log \frac{q(x)}{p(x)}dx$$
This is the *reverse* KL divergence from the approximating distribution to the target true distribution. This is opposite from the *forward* KL divergence $D_{KL}(p\|q)$, and the optimization of each lead to different behaviour
- The reverse KL divergence is *mode-seeking*, meaning that it encourages $q$ to concentrate its probability on 1 mode in particular
- The forward KL divergence is *mass-covering*, meaning that it encourages q to concentrate its mass on all modes
→ 
