---
id: mv9m2rszimwe9iqnhgjl766
title: Spectral norm
desc: 'Spectral characterization of Sobolev norms: on compact manifolds, via Laplacian eigenfunctions. Proof via functional calculus and elliptic regularity, with explicit H¹ calculation.'
updated: 1763328084386
created: 1763326967127
---


# 1. The $H^1$ calculation (concrete)

Let $\{\varphi_j\}_{j\ge0}$​ be an orthonormal $L^2$-basis of eigenfunctions of $-\Delta$ with eigenvalues $\lambda_j\ge0$:

$$-\Delta\varphi_j=\lambda_j\varphi_j,\qquad\langle\varphi_j,\varphi_\ell\rangle_{L^2}=\delta_{j\ell}.$$

Expand $w=\sum_j w_j\varphi_j$​ (convergence in $L^2$). Then

$$\|(1-\Delta)^{1/2}w\|_{L^2}^2 =\sum_j \big(1+\lambda_j\big)\,|w_j|^2,$$

because $(1-\Delta)^{1/2}\varphi_j=(1+\lambda_j)^{1/2}\varphi_j$​ and Parseval / Plancherel give the squared $L^2$-norm as the sum of squared coefficients.

So the spectral sum with weight $(1+\lambda_j)$ is **exactly** the squared $L^2$-norm of $(1-\Delta)^{1/2}$.

Now the usual Sobolev $H^1$ norm on a compact manifold is equivalent to the graph norm of $(1-\Delta)^{1/2}$; concretely there exist constants $c,C>0$ depending only on the manifold so that

$$c\;\|(1-\Delta)^{1/2}w\|_{L^2}\le \|w\|_{H^1}\le C\;\|(1-\Delta)^{1/2}w\|_{L^2}.$$

Combining this with the identity above yields

$$\|w\|_{H^1}^2 \simeq \sum_j (1+\lambda_j)\,|w_j|^2,$$

which is the $H^1$ instance of the claim.

(Why is the equivalence true? On a compact manifold $\|w\|_{H^1}^2$​ is $\|w\|_{L^2}^2+\|\nabla w\|_{L^2}^2$​. Using the eigen-expansion one checks $\|\nabla w\|_{L^2}^2=\sum_j\lambda_j|w_j|^2$. Hence $\|w\|_{H^1}^2=\sum_j(1+\lambda_j)|w_j|^2$ up to the choice of normalization and conventions — so in fact for $H^1$ one often gets equality (no constants) when you identify norms appropriately.)

# 2. The general $H^k$ (spectral functional calculus)

Exactly the same spectral computation works for any real $k\ge0$. By functional calculus

$$(1-\Delta)^{k/2}\varphi_j=(1+\lambda_j)^{k/2}\varphi_j,$$

so for $w=\sum_j w_j\varphi_j$,

$$\|(1-\Delta)^{k/2}w\|_{L^2}^2 =\sum_j (1+\lambda_j)^{k}|w_j|^2.$$

Thus the right-hand spectral sum is exactly the squared $L^2$-norm of $(1-\Delta)^{k/2}w$.

# 3. Equivalence of $(1-\Delta)^{k/2}$-graph norm and the usual Sobolev $H^k$ norm

What remains is to explain why the graph norm $\|(1-\Delta)^{k/2}w\|_{L^2}$​ is equivalent to the standard Sobolev norm $\|w\|_{H^k}$​. On a compact manifold this is standard:

- The operator $1-\Delta$ is a positive, elliptic, self-adjoint pseudodifferential operator of order 2. Its (fractional) powers $(1-\Delta)^{k/2}$ are elliptic pseudo-differential operators of order k.
    
- Elliptic regularity (or basic pseudodifferential calculus) implies that the graph norm of any positive elliptic operator of order k is equivalent to the standard Sobolev $H^k$-norm. Concretely, there exist constants $c,C>0$ (dependent only on the geometry of $S$ and $k$) such that for all $w\in C^\infty(S)$,
    
    $$c\;\|(1-\Delta)^{k/2}w\|_{L^2} \le \|w\|_{H^k} \le C\;\big(\|w\|_{L^2}+\|(1-\Delta)^{k/2}w\|_{L^2}\big).$$
    
    On a compact manifold the two-sided inequality can be tightened (by adjusting constants) to show full equivalence (no extra low-order term needed if you use $(1-\Delta)^{k/2}$ itself as the defining operator).
    

If you prefer an elementary (but longer) route: cover the manifold with finitely many coordinate charts, use a partition of unity, and compare the local Euclidean Sobolev norms defined by derivatives up to order k with the global spectral norm. The finiteness of the cover and standard elliptic estimates give the equivalence constants.

# 4. Conclusion 

Putting items (2) and (3) together yields the desired equivalence:

$$\|w\|_{H^k}^2 \;\simeq\; \sum_{j\ge0} (1+\lambda_j)^k\,|w_j|^2,$$

where the symbol $\simeq$ means equality up to multiplicative constants depending only on $k$ and the Riemannian manifold $S$.

