

Let $\Psi_\varepsilon(-\Delta)=(1+\varepsilon(-\Delta))^{-1}$ and let $\{\varphi_j\}_{j\ge0}$​ be an orthonormal $L^2$-basis of eigenfunctions of $-\Delta$ with eigenvalues $\lambda_j\ge0$:

$$-\Delta\varphi_j=\lambda_j\varphi_j.$$

The spectral functional calculus gives

$$\Psi_\varepsilon(-\Delta)f=\sum_{j\ge0}\Psi_\varepsilon(\lambda_j)\,f_j\,\varphi_j, \qquad f_j=\langle f,\varphi_j\rangle_{L^2},$$

with multiplier $\Psi_\varepsilon(\lambda)=\dfrac{1}{1+\varepsilon\lambda}$. Hence the integral kernel of $\Psi_\varepsilon(-\Delta)$ is the series

 $$\boxed{\,G_\varepsilon(x,y)\;=\;\sum_{j\ge0}\frac{1}{1+\varepsilon\lambda_j}\,\varphi_j(x)\varphi_j(y)\,.}$$

This series converges in the sense of distributions and in $C^\infty$ away from the diagonal $x=y$. Applying the operator to $f$ gives the usual kernel formula

$$(\Psi_\varepsilon(-\Delta)f)(y)=\int_S G_\varepsilon(x,y)\,f(x)\,dV_x.$$

One checks immediately that

$$(-\varepsilon\Delta_x+1)G_\varepsilon(x,y)=\sum_j \frac{1+\varepsilon\lambda_j}{1+\varepsilon\lambda_j}\varphi_j(x)\varphi_j(y)=\sum_j\varphi_j(x)\varphi_j(y)=\delta_y(x)$$

(in the distributional sense), so indeed $G_\varepsilon$​ is the Green kernel for $-\varepsilon\Delta+1$.

## 2) Convergence as $\varepsilon\downarrow0$: distributional and strong operator limits

From the spectral formula,

$$G_\varepsilon(x,y)=\sum_j \frac{1}{1+\varepsilon\lambda_j}\varphi_j(x)\varphi_j(y).$$

For each fixed $j$ we have $\dfrac{1}{1+\varepsilon\lambda_j}\to 1$ as $\varepsilon\to0$. Thus the kernel coefficients tend to those of the formal series $\sum_j \varphi_j(x)\varphi_j(y)$, which equals $\delta_y(x)$ in the sense of distributions. Concretely, for any test functions $\phi,\psi\in C^\infty(S)$,

$$\iint G_\varepsilon(x,y)\,\phi(x)\,\psi(y)\,dx\,dy = \langle \Psi_\varepsilon(-\Delta)\phi,\psi\rangle_{L^2} \longrightarrow \langle\phi,\psi\rangle_{L^2} = \iint \delta(x-y)\phi(x)\psi(y)\,dx\,dy,$$

$G_\varepsilon\rightharpoonup\delta$ as measures/distributions.

You can also state convergence in function spaces:

- **Strong $L^2$ convergence on functions.** For any fixed $f\in L^2(S)$,
    
    $$\|\Psi_\varepsilon(-\Delta)f - f\|_{L^2}^2 = \sum_j\Big(1-\frac{1}{1+\varepsilon\lambda_j}\Big)^2 |f_j|^2 \xrightarrow{\varepsilon\to0}0$$
    by dominated convergence (the pointwise factors are $\le1$ and tend to 0 for each fixed $j$). So $\Psi_\varepsilon(-\Delta)\to I$ strongly on $L^2$ (and similarly on $H^k$ if $f\in H^k$, because the multipliers are bounded by 1 uniformly).

