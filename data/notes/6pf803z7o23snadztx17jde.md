
I'll give a clean, self-contained explanation showing

$$
\|u\|_{X^{k}} \;\le\; C_k \|f\|_{X^{k}}, \qquad u=( -\varepsilon\Delta +1)^{-1} f
$$

and point out exactly where $G_\varepsilon\to\delta$ is used.

# 1) Representation by the Green kernel

On a compact Riemannian manifold $S$ the solution of


$$
(-\varepsilon\Delta_x +1)G_\varepsilon(x,y)=\delta_y(x)
$$

is the (symmetric, smooth off the diagonal) resolvent kernel $G_\varepsilon(x,y)$, and the solution $u$ of

$$
(-\varepsilon\Delta +1)u=f
$$
has the representation


$$
u(y)=\int_S G_\varepsilon(x,y)\,f(x)\,d\!V_x.
$$

So the operator $(-\varepsilon\Delta+1)^{-1}$ is the integral operator with kernel $G_\varepsilon$​.

# 2) $L^\infty$-estimate (where the weak convergence to $\delta$ is relevant)

Integrate the kernel equation in $x$:

$$
\int_S\bigl(-\varepsilon\Delta_x G_\varepsilon(x,y)+G_\varepsilon(x,y)\bigr)\,dV_x =\int_S\delta_y(x)\,dV_x=1.
$$

The Laplacian term integrates away (or use divergence theorem), so

$$
\int_S G_\varepsilon(x,y)\,dV_x = 1\qquad\text{for every }y.
$$

Moreover the maximum principle gives $G_\varepsilon\ge 0$. Thus $G_\varepsilon(\cdot,y)$ is a probability density on $S$ for each fixed $y$. From the kernel representation

$$
|u(y)| \le \|f\|_{L^\infty}\int_S G_\varepsilon(x,y)\,dV_x = \|f\|_{L^\infty},
$$

so

$$
\|u\|_{L^\infty}\le \|f\|_{L^\infty}.
$$

(Here the weak convergence $G_\varepsilon\rightharpoonup\delta$ explains that the kernel concentrates as $\varepsilon\downarrow0$, and in the limit the integral operator tends pointwise to evaluation at the point — but the inequality above does not require taking limits: it follows from positivity and unit mass of $G_\varepsilon$​.)

# 3) $H^k$-estimate (spectral / Fourier multipliers)

Let $\{\varphi_j\}$ be an $L^2$-orthonormal basis of eigenfunctions of $-\Delta$ with eigenvalues $\lambda_j\ge0$:

$$-\Delta\varphi_j=\lambda_j\varphi_j.$$

Expand $f=\sum_j f_j\varphi_j$​, then

$$u=(1+\varepsilon\lambda_j)^{-1}f_j\varphi_j,$$

so the Fourier coefficient of $u$ on $\varphi_j$​ is $u_j=\dfrac{f_j}{1+\varepsilon\lambda_j}$.
The $H^k$-norm squared is (up to equivalent normalization)

$$\|w\|_{H^k}^2 \simeq \sum_j (1+\lambda_j)^k |w_j|^2.$$

Hence

$$\|u\|_{H^k}^2 = \sum_j \frac{(1+\lambda_j)^k}{(1+\varepsilon\lambda_j)^2}\,|f_j|^2.$$

But for every $\lambda_j\ge0$ and every $\varepsilon>0$,

$$\frac{(1+\lambda_j)^k}{(1+\varepsilon\lambda_j)^2}\le (1+\lambda_j)^k\cdot 1 = (1+\lambda_j)^k,$$

because $(1+\varepsilon\lambda_j)^2\ge1$. Therefore

$$\|u\|_{H^k}^2 \le \sum_j (1+\lambda_j)^k |f_j|^2 = \|f\|_{H^k}^2,$$

so

$$\|u\|_{H^k}\le \|f\|_{H^k}.$$

(Equivalently, the multiplier $(1+\varepsilon\lambda)^{-1}$ has modulus $\le 1$, so $(-\varepsilon\Delta+1)^{-1}$ is a contraction on every Sobolev space $H^k$.)

# 4) Combine to get the $X^k$-estimate

Recall $X^k := H^k\cap L^\infty$ with norm $\|v\|_{X^k}=\|v\|_{H^k}+\|v\|_{L^\infty}$. From the two bounds above we get, with $C_k=1$,

$$\|u\|_{X^k} \;=\;\|u\|_{H^k}+\|u\|_{L^\infty} \le \|f\|_{H^k}+\|f\|_{L^\infty} = \|f\|_{X^k}.$$

So the desired inequality holds (in fact with constant 1) for every $\varepsilon>0$.

---

# Remarks / why Ricciardi mentioned $G_\varepsilon\to\delta$

- The convergence $G_\varepsilon\rightharpoonup\delta$ explains the limiting behaviour of the solution as $\varepsilon\downarrow0$: $u=(G_\varepsilon * f)\to f$ pointwise (and in suitable norms) — consistent with the fact that $(-\varepsilon\Delta+1)^{-1}\to\mathrm{Id}$.
    
- But to prove the operator norm bound $\|u\|_{X^k}\le C_k\|f\|_{X^k}$​ you do not actually need the weak convergence; you only need the two facts used above:
    
    1. $G_\varepsilon(\cdot,y)\ge0$ and $\int_S G_\varepsilon(\cdot,y)=1$ for each $y$ (gives the $L^\infty$ bound),
        
    2. the spectral multiplier $(1+\varepsilon\lambda)^{-1}$ has modulus $\le1$ (gives the $H^k$ bound).
        

So the convergence to the delta is a helpful intuition and gives pointwise limit information, but the inequality itself follows from the kernel mass + positivity and from the spectral (Fourier multiplier) estimate.

