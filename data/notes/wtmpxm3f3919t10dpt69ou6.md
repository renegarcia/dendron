
## Definitions

Let $G$ be a group of isometries in a metric space $X$, we say that the action of $G$ is proper if the action map

$$
\phi: G\times X \to X \times X, \qquad (g, x) \mapsto (x, g.x),
$$

is a proper map (i.e. the preimage $\phi^{-1}(C)$ of any compact set $C \subset X \times X$ is compact). Equivalently, $\phi$ is proper if and only if, for any compact set $K \subset X$, the set

$$
\left\{ g \in G\mid g(K) \cap K \neq \emptyset \right\}
$$

is compact. For discrete subgroups, this definition is equivalent to requiring that the set @eq-proper-action-equiv is finite, as in the definition of Scott @scott1983 pg. 86.

### Discrete subgroups of isometries

The following proposition resumes the basic properties of groups of isometries acting on a metric space $X$, the tool for the proof will be [Arzela-Ascoli theorem](https://en.wikipedia.org/wiki/Arzel%C3%A0%E2%80%93Ascoli_theorem). Recall a family of continuous functions $\mathcal{F}$ is *equicontinuous* if for all $\epsilon > 0$ exists $\delta > 0$ such that

$$
d(x,y) < \delta \Rightarrow d(f(x), f(y)) < \epsilon,
$$

independently of the value of $x$ and $y$.

::: {#thm-arzela-ascoli}
Let $\mathcal{F} \subset \mathcal{C}(X, Y)$ be a family of maps between metric spaces, then $\mathcal{F}$ is relatively compact in the topology of [compact convergence](https://en.wikipedia.org/wiki/Compact_convergence) (i.e. the topology of uniform convergence on compact sets) if and only if $\mathcal{F}$ is equicontinuous and $\mathcal{F}(x)$ is relatively compact in $Y$ for any $x\in X$.
:::

Note that families of isometries of the metric space $X$ are trivially equicontinuous,

::: {#prp-1 .prp}
If $\Gamma \subset X$ is a discrete subgroup of isometries of the complete metric space $(X, d)$ with the Heine-Borel property (each closed bounded set in $X$ is compact), then:

1. The action of $\Gamma$ is proper.
2. For any $x \in X$, the orbit $\Gamma x$ has no accumulation point in $X$.
:::

The source of the proof for the first part can be found [here](https://math.stackexchange.com/questions/3211710/properly-discontinuous-actions-and-discrete-groups-in-complete-riemannian-manifo).

::: proof
Suppose the existence of a compact set $K\subset X$ and an infinite sequence of distinct elements $\gamma_n \in \Gamma$ such that $\gamma_n (K) \cap K \neq \emptyset$. Let $p \in K$ and $R = 2 \operatorname{diam}(K)$, then $\gamma_n(p)$ is contained in the closed ball $\overline{B}(p, R)$, hence for any $x \in X$,

$$
\begin{align*}
d(\gamma_n(x), p) &\leq d(\gamma_n(x), \gamma_n(p)) + d(\gamma_n(p), p)\\
&= d(x, p) + d(\gamma_n(p), p) \\
&\leq d(x, p) + R.
\end{align*}
$$

Since $X$ has the Heine-Borel property, the inequality above implies $\Gamma x$ is relatively compact for all $x$ and since $\Gamma$ is a group of isometries, it is also equicontinuous, therefore by the Arzela-Azcoli theorem, $\Gamma$ is relatively compact in the topology of uniform convergence on compact sets, hence we can suppose there is a continuous function, in fact an isometry, $\gamma: X \to X$, such that $\gamma_n \to \gamma$ uniformly on compact sets, hence $\gamma_n^{-1}\gamma_{n+1} \to e$, uniformly on compact sets, but since the topology of $\Gamma$ is discrete, $\gamma_n = \gamma_{n+1}$ for $n$ sufficiently large, a contradiction.

For the second part assume towards a contradiction the existence of a limit point $y$ for the orbit $\Gamma x$, hence there is an infinite sequence $\{\gamma_n\} \subset \Gamma$ such that $\gamma_n x \to y$. If $K$ is the compact set $\{x\} \cup \{\gamma_n x\} \cup \{y\}$, then $\gamma_n(K)\cap K \neq 0$ for all $\gamma_n$ in the sequence, a contradiction.
:::

In particular, complete Riemannian manifolds have the Heine-Borel property and therefore discrete subgroups of isometries act properly.

## Critical exponent of groups of isometries

Let $\Gamma$ be a discrete subgroup of isometries of the complete metric space $X$ with the Heine-Borel property and let $x, y \in X$ be any pair of points, we can form the Poincare series of the group, defined as,

$$
P(s; x, y) = \sum_{\gamma \in \Gamma} e^{-s d(x, \gamma y)}, \qquad s \in \mathbb{R}.
$$

The *critical exponent* of the group is the number $\delta_\Gamma$ such that the series is convergent for $s > \delta_\Gamma$. It can be shown that $\delta_\Gamma$ is independent of the pair of points chosen in $X$, in fact, it is well known that

$$
\delta_\Gamma = \limsup_{R \to \infty} \frac{\log (\#\{\gamma \in \Gamma \mid \gamma x \in B(x, R)\})}{R}.
$$

If $X$ is also endowed with a measure $m$, we can define the *volume entropy* of $X$ as,

$$
\delta_X = \limsup_{R \to \infty} \frac{\log m(B(x,R))}{R}.
$$

The following facts are well known for manifolds of negative curvature, however they are valid for more general metric spaces.

::: prp-deltag-deltax
Let $X$ be a complete metric space with the Heine-Borel property equipped with a measure $m$ compatible with the metric, in the sense that for any measurable set $A \subset X$ and any isometry $f$, we have $m(f(A)) = m(A)$. If $\Gamma$ is a discrete group of isometries, then

$$
\delta_\Gamma \leq \delta_X,
$$

moreover, if $\Gamma$ is co-compact (the quotient space $\Gamma \setminus X$ is compact), then $\delta_\Gamma = \delta_X$.
:::

The following proof can be found in @quint.

::: proof
Since $\Gamma$ is discrete and $X$ has the Heine-Borel property, the action of $\Gamma$ is proper, hence no orbit $\Gamma x$ has accumulation points, therefore there exists a real number $s > 0$ such that for every\
$\gamma \in \Gamma$, if $B(\gamma x, s) \cap B(x, s) \neq \emptyset$ then $\gamma x = x$. Let $n$ be the number of elements of $\Gamma$ that fix $x$, by the triangle inequality,

$$
\#\{\gamma \in \Gamma \mid \gamma x \in B(x, r)\} m(B(x,r)) \leq n m(B(x, r+s)),
$$

taking logarithms, Quint deduces $\delta_\Gamma \leq \delta_X$. If $\Gamma$ is co-compact, there is a compact fundamental region $F \subset X$ such that $\Gamma(F) = X$. If $s > 0$ is sufficiently large for $F \subset B(x, s)$, then $X = \cup_{\gamma \in \Gamma}B(\gamma x, s)$, since each $\gamma$ is an isometry and $\gamma (B(x, s)) = B(\gamma x, s)$. Thus for any $r > 0$, the triangle inequality implies

$$
B(x,r) \subset \cup_{\{\gamma \in \Gamma \mid\gamma x\in B(x, r+s)\}} B(\gamma x, s),
$$

hence,

$$
m(B(x, r)) \leq \#\{\gamma \in \Gamma \mid \gamma x \in B(x, r+s)\} m(B(x, s)),
$$

where we have used that the measure is compatible with the metric. Taking logs, the last inequality implies $\delta_X \leq \delta_\Gamma$.
:::

## The visual boundary in a metric space

Let $(X, d)$ be a complete metric space, a geodesic in $X$ is a continuous function $\gamma: \mathbb{R} \to X$ such that

$$
d(\gamma(s), \gamma(t)) = |s - t|.
$$

Given any two geodesics $\gamma_1, \gamma_2$, we define the equivalence relation $\gamma_1 \sim \gamma_2$ if and only if there is a constant $c > 0$, such that $d(\gamma_1(t), \gamma_2(t)) \leq c$ for all $t \geq 0$. We denote the set of equivalence classes as $X(\infty)$ and call it the *visual boundary* of $X$. Let $\overline{X} = X \cup X(\infty)$, we call $\overline{X}$ the completion of $X$, if $\xi \in X(\infty)$ and $\gamma$ is a geodesic in the equivalence class, we also denote $\xi$ as $\gamma(\infty)$ and call $\xi$ the end of $\gamma$. Let us introduce a topology on $\overline{X}$ in the following manner: Let $p \in X$, $\xi \in X(\infty)$, $\Theta \in \mathbb{R}$, and assume there is a geodesic $\gamma$ such that $\gamma(0) = p$ and $\gamma(\infty) = \xi$, we define the cone set

$$
C(p, \xi, \Theta) = \{x \in \overline{X} \mid \angle_p(x, \xi) < \Theta\}.
$$

### References

1. Quint, J.-F. n.d. “An Overview of Patterson-Sullivan Theory.”
2. Scott, Peter. 1983. “The Geometries of 3-Manifolds.” Bulletin of the London Mathematical Society 15 (5): 401–87. <https://doi.org/10.1112/blms/15.5.401>.
