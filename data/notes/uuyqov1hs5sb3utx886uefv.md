
SOL is one of the eight Thurston's geometries of three dimensional manifolds. Topologically it is $\mathbb{R}^3$ with the metric
$$
ds^2 = e^{-2z}dx^2 + e^{2z}dy^2 + dz^2.
$$
It also is a solvable Lie group, such that the exponential map $\mathfrak{sol} \to \mathrm{SOL}$ is a diffeomorphism and the metric above described is left invariant with respect to the group operation
$$
(x,y,z) \cdot (x',y',z') = (x+ e^z x',y+ e^{-z} y', t + t').
$$

## Volume entropy

We aim to compute the volume entropy of the group, defined as
$$
\delta_{\mathrm{SOL}} = \lim_{r \to \infty} \frac{1}{r} \log \operatorname{Vol}(B(0,r)),
$$
where $B(0,r)$ is the geodesic ball centred at the origin of radius $r$. For the compuation, we follow Schwartz and notice the projection $\eta_X: \mathrm{SOL} \to \mathbb{R}^2$, $(x, y, z) \mapsto (0, y, z)$ decreases areas and sends the geodesic sphere $\mathcal{S}_r = \partial B(0, r)$ onto the hyperbolic disk $\mathbb{D}(0, r) = \{(y, z) \in \mathbb{R}^2 \mid d(0, (0, y, z)) < r\}$.
The area of the hyperbolic disk is $4\pi\sinh(r/2)^2$ and the projection is two-to-one, whence
$$
8\pi\sinh(r/2)^2 \leq \operatorname{Area}(\mathcal{S}_r).
$$
On the other hand,
$$
8\pi\sinh(r/2)^2 = 2\pi(\cosh(r) - 1),
$$
and the volume of the geodesic ball is
$$
\operatorname{Vol}(B_r) = \int_0^r \operatorname{Area}(\mathcal{S}_t) dt,
$$
we conclude,
$$
2\pi (\sinh(r) - r) \leq \operatorname{Vol}(B(0, r)).
$$
From this inequality, is follows that $1 \leq \delta_{\mathrm{SOL}}$.

### An upper bound for the entropy

The upper bound for the volume entropy is a work of Schwartz and Kopczynski, their argument is remarkably simple, it comes from the observation that every point $(x, y, z) \in \mathcal{S}_r$ satisfies the
inequalitites,
$$
\begin{align}
    |x|, |y| \leq e^r + r, &&
    |z| \leq r, &&
    (|x| - r)(|y| - r) \leq e^r,
\end{align}
$$
then they estimate the upper bound $72r^2e^r$ for $\operatorname{Vol}(B(0,r))$, by this upper bound, together with the lower bound of the previous section, they conclude that the volume entropy of $\operatorname{SOL}$ is 1.

## References

* Schwartz, Richard Evan. ‘On Area Growth in Sol’, 2020. <https://doi.org/10.48550/ARXIV.2004.10622>.
