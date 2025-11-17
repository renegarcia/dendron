

The energy method is a very natural way to see the bound 

$$
||u||_{X^k} \leq C ||f||_{X^k}, \qquad (-\varepsilon \Delta + 1) u = f
$$

and in this problem it runs very cleanly because the Laplacian commutes with itself so you can differentiate the equation by powers of $\Delta$ without producing nasty commutators. Below I give a self-contained energy-style proof that

$$\|u\|_{H^{2s}} \le \|f\|_{H^{2s}}\qquad(\text{and hence } \|u\|_{H^{k}}\le C_k\|f\|_{H^{k}}\text{ for all }k),$$

and then show how to combine that with the $L^\infty$-estimate to get the $X^k$-bound. Everything below holds on a compact Riemannian manifold $S$ (no boundary), and the constant is independent of $\varepsilon>0$.

# 1. The basic $L^2$ energy estimate

Start from

$$(-\varepsilon\Delta + 1)u = f.$$

Take the $L^2$-inner product of the equation with $u$. Using $\langle -\Delta u,u\rangle = \langle\nabla u,\nabla u\rangle = \|\nabla u\|_{L^2}^2$​ (integration by parts; no boundary terms on a compact manifold) we obtain

$$\varepsilon\|\nabla u\|_{L^2}^2 + \|u\|_{L^2}^2 \;=\; \langle f,u\rangle \le \|f\|_{L^2}\|u\|_{L^2}.$$

From this coercivity we immediately get

$$\|u\|_{L^2} \le \|f\|_{L^2},$$

and also $\varepsilon\|\nabla u\|_{L^2}^2 \le \|f\|_{L^2}\|u\|_{L^2} \le \|f\|_{L^2}^2$, but we will not need the latter for the main uniform-in-$\varepsilon$ $H^k$-bounds. The important point: the operator is coercive and gives an $L^2$-control of $u$ by $f$ with constant 1.

# 2. Higher (even) derivatives by applying powers of $\Delta$

Because $\Delta$ commutes with itself and with the scalar 1, we can apply $\Delta^{s}$ (for any integer $s\ge0$) to the PDE and get

$$(-\varepsilon\Delta + 1)\bigl(\Delta^{s} u\bigr) \;=\; \Delta^{s} f,$$

(i.e. $\Delta^{s}$ passes through the constant-coefficient operator $-\varepsilon\Delta+1$). Now take the $L^2$-inner product of this equation with $\Delta^{s}u$. Exactly the same coercivity algebra gives

$$\varepsilon\|\nabla(\Delta^{s}u)\|_{L^2}^2 + \|\Delta^{s}u\|_{L^2}^2 = \langle \Delta^{s} f,\;\Delta^{s}u\rangle \le \|\Delta^{s}f\|_{L^2}\,\|\Delta^{s}u\|_{L^2}.$$

Therefore

$$\|\Delta^{s}u\|_{L^2} \le \|\Delta^{s}f\|_{L^2}.$$

This is the same structure as the base $L^2$ inequality, but at the differentiated level — and again the constant is 1 and independent of $\varepsilon$.

# 3. From $\|\Delta^{s}(\cdot)\|_{L^2}$​ to Sobolev norms

On a compact manifold the Sobolev norm $H^{2s}$ is equivalent to the graph norm of the (positive) Laplacian:

$$\|w\|_{H^{2s}} \simeq \Bigl(\sum_{j=0}^{2s}\|\nabla^j w\|_{L^2}^2\Bigr)^{1/2}$$

and, spectrally, $\|w\|_{H^{2s}}$​ is equivalent to $\| (1-\Delta)^s w\|_{L^2}$​. In particular there are constants $C_1$, $C_2$​ (depending only on $s$ and the geometry of $S$) such that

$$C_1\|\Delta^{s} w\|_{L^2} \le \|w\|_{H^{2s}} \le C_2\bigl(\|w\|_{L^2}+\|\Delta^{s} w\|_{L^2}\bigr).$$

Using the estimate $\|\Delta^{s}u\|_{L^2}\le\|\Delta^{s}f\|_{L^2}$ together with the base $L^2$-bound $\|u\|_{L^2}\le\|f\|_{L^2}$​ gives

$$\|u\|_{H^{2s}} \le C_s\,\|f\|_{H^{2s}}$$

for some constant $C_s$​ depending only on $s$ and the manifold $S$, but not on $\varepsilon$. (If you use the spectral identity $\|w\|_{H^{2s}}\simeq\|(1-\Delta)^s w\|_{L^2}$ you can even arrange $C_s=1$ for the part coming from $\Delta^s$; the equivalence constants appear when moving between different definitions of the Sobolev norm.)

This proves uniform-in-$\varepsilon$ control for all even Sobolev orders $H^{2s}$.

# 4. Odd / arbitrary integer _k_

If $k$ is arbitrary integer, pick $s$ with $2s\ge k$. The control in $H^{2s}$ and the continuous embedding $H^{2s}\hookrightarrow H^{k}$ (on compact $S$) yield

$$\|u\|_{H^{k}} \le C_{k}\|f\|_{H^{k}}.$$

So every integer Sobolev order is handled. For non-integer orders use interpolation (or fractional powers of $1-\Delta$); the same argument with $(1-\Delta)^{\sigma}$ in place of $\Delta^s$ (or spectral functional calculus) gives the estimate for all real $k\ge0$.

# 5. The $L^\infty$-part and the $X^k$-estimate

If the manifold has dimension $n$ and $k>n/2$, Sobolev embedding gives $H^k\hookrightarrow L^\infty$. From step 3 we have a uniform $H^k$-bound

$$\|u\|_{H^{k}} \le C_k \|f\|_{H^{k}}.$$

Therefore also

$$\|u\|_{L^\infty} \le C_{\mathrm{emb}} \|u\|_{H^k} \le C'_{k}\|f\|_{H^k}.$$

Combining $\|u\|_{H^k}$​ and $\|u\|_{L^\infty}$​ gives the desired $X^k$-bound

$$\|u\|_{X^{k}} = \|u\|_{H^k} + \|u\|_{L^\infty} \le C_k'' \,\|f\|_{X^{k}}.$$

(If the $X^k$-norm is defined as the max or another equivalent norm, the same conclusion holds with possibly different constants.)

# 6. Comments / why this is cleaner than a naive energy attempt

- The key simplification is that you may apply powers of $\Delta$ directly to the equation because $\Delta$ commutes with $-\varepsilon\Delta+1$. That avoids any commutator terms which would otherwise introduce $\varepsilon^{-1}$-type factors or geometric curvature terms.
    
- The estimate is uniform in $\varepsilon$ because the factor $\varepsilon$ multiplies the $-\Delta$ term on the left-hand side but every differential-level energy identity keeps the same coercive shape:
    
    $$\varepsilon\|\nabla(\Delta^s u)\|_{L^2}^2+\|\Delta^s u\|_{L^2}^2=\langle\Delta^s f,\Delta^s u\rangle,$$
    
    and the inequality $\|\Delta^s u\|_{L^2}\le\|\Delta^s f\|_{L^2}$ follows exactly as in the base case without producing $\varepsilon^{-1}$ factors.
    
- If you had variable coefficients in front of $\Delta$ (e.g. $-\varepsilon \nabla\cdot(A(x)\nabla u)$) or lower-regularity metric terms, commutators would appear and you would need to control them; that can introduce dependence on $\varepsilon$ unless handled carefully.

