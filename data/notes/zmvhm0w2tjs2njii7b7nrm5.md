
# Stochastic processes

Let $(\Omega, B, P)$ be a measure space, with Borel $\sigma$-algebra *B*, and probability measure *P*.

**Definition** A *stochastic process* is a parametrized collection of random variables:

$$\{X_t \mid t \geq 0\},$$

such that each $X_t$ is a random variable in the measure space.

## Brownian movement or Wiener process

Let $\{ w_t \mid t \geq 0 \}$ be a stochastic process such that $w_t$ is continous in the weak sense with respect to $t$. $w_t$ is a *Wiener process* if:

1. $0 \leq t_1 \leq t_2$ implies 
$$w_{t_2} - w_{t_1} \sim N(0, t_2 - t_1)$$
2. For any $t_1 < t_2 < t_3$, $$w_{t_3} - w_{t_2}$$ is independent of $$w_{t_2} - w_{t_1}$$.
3. The probability $w_0 = 0$ satisfies $P(w_0 = 0) = 1$.

*Note:* In general, $w_t$ is not differentiable in any point.

## Ito integral

Let $f(t, x_t) = f(t)$, with $x_t$ an stochastic process, such that 

$$\int_a^b E(f(t)) dt < \infty.$$

We will say that $f(t)$ is a *random function*. Let 
$$\{a = t_1 < \cdots < t_{n + 1} = b\}$$ 
be a partition of $[a, b]$, with equally spaced points, and let $\Delta t = (b - a)/n$ and $$\Delta w_i = w_{t_{i + 1}} - w_{t_i}$$. Then, Ito's integral is 

$$\int_a^b f(t) dw_t = \lim\sum_{i = 1}^n f(t_i) \Delta w_i.$$

### Notes

- If $s_n$ represents the nth-partial sum of the integral above, we say that $\lim_{n\to\infty} s_n = I$ in probability if 

$$\lim_{n \to \infty} E((s_n - I)^2) = 0.$$

- Note that there are two stochastic processes involved in the definition: $x_t$, which is implicit in $f(t)$ and $w_t$, which represents *noise* or *decoherence*, depending the problem.

## Ito's stochastic differential equation

**Definition:** $x_t$ is a solution of the *stochastic differential equation*, 

$$dx_t = \alpha(x_t,t) dt + \beta(x_t, t)dw_t,$$

if for any $t > 0$, $x_t$ satisfies

$$x_t = x_0 + \int_0^t \alpha(x_t, t)dt + \int_0^t \beta(x_t, t)dw_t.$$

**Q.** Under which conditions can it be proved that the solution to this equation is unique?.

**Teorem (chain rule)** If $x_t$ is the solution of a stochastic differential equation, and $F(x, t)$ is a real function such that the partial derivatives
$$\partial_t F, \partial_x F, \partial_{xx} F$$
are continous functions, then 

$$dF(x_t, t) = f(x_t, t) dt + g(x_t, t) dw_t,$$

where 

$$f(x, t) = \partial_tF + \alpha(x_t, t) \partial_x F + \frac{1}{2} \beta^2(x_t, t) \partial_{xx}F$$

and 

$$g(x_t, t) = \beta(x_t, t) \partial_x F.$$

### Stochastic maltus model

**Theorem** The solution to the stochastic differential equation
$$dx_t = r x_t dt + c x_t dw_t$$
is 

$x_t = x_0\exp((r - c^2/2)t + c \cdot w_t)$.

**Proof** Let $F = \ln(x)$, by the chain rule:

$$d\ln(x_t) = \left(rx_t\cdot \frac{1}{x_t} + \frac{1}{2} c^2 x_t^2 \left(- \frac{1}{x_t^2}\right)\right) dt + c x_t \cdot \frac{1}{x_t} dw_t,$$

Simplifying the equation, we get

$$d\ln(x_t) = \left(r - \frac{c^2}{2}\right) dt + c \cdot dw_t.$$

It can be shown that the fundamental theorem of calculus is valid for the stochastic integral of a constant function,  therefore, applying this result to the previous equation, we find,

$$\ln\left(\frac{x_t}{x_0}\right) = \left(r - \frac{c^2}{2}\right) t + c\cdot w_t,$$

and the theorem follows.

### Numerical methods

#### I. Euler-Murayama method


$$dx_i = \Delta x_i, \qquad dw_i = \Delta w_i,$$

$$x_{i + 1} = x_i + \alpha(x_i, t_i) \Delta t + \beta(x_i, t_i) \Delta w_i.$$

Note that in order to implement this method we should select $\Delta w_i$ randomly with distribution $N(0, \Delta t)$.

#### II. Milstein method

Modify the last equation into

$$x_{i +1} = x_i + \alpha(x_i, t_i) \Delta t + \beta(x_i, t_i) \Delta w_i + \frac{1}{2} \beta(x_i, t_i) \frac{\partial \beta}{\partial x}(x_i, t_i) \left((\Delta w_i)^2 - \Delta t\right).$$

This last method resembles *predictor-corrector* methods in ordinary differential equations.

---

Originally published by the author in [http://ixxra.github.io/mathannotations/sdes/2014/05/21/stochastic-differential-equations/](http://ixxra.github.io/mathannotations/sdes/2014/05/21/stochastic-differential-equations/)


# References

* Seminar notes, René García-Lara, May 2014, available at [http://ixxra.tumblr.com/post/86507241536/today-in-the-mathematics-seminar-stochastic](http://ixxra.tumblr.com/post/86507241536/today-in-the-mathematics-seminar-stochastic)