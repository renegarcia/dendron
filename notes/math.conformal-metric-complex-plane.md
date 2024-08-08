---
id: n2m0ds94d0uzg0x1csytrx7
title: Conformal metrics on the complex plane
desc: 'I compute the curvature of a general conformal metric on the complex plane'
updated: 1723094543637
created: 1723094456583
---

Let $M$ be a Riemannian manifold with metric $g$, recall the Laplace-Beltrami operator of the metric is the elliptic operator defined as
$$
\Delta_g f = \frac{1}{\sqrt{|g|}} \partial_i \left( \sqrt{|g|} g^{ij} \partial_j f\right).
$$
In the previous equation we use the Einstein convention of summing over repeated indexes in covariant and contravariant position. If the manifold is an open region in the complex plane, the Theorem of Liouville asserts that there exists a positive function $\lambda$, such that under a suitable change of coordinates,  $g = \lambda^2 dz d\bar{z}$, the curvature of this metric can be computed as
$$
\kappa = - \Delta_g \log(\lambda) = -\frac{1}{\lambda} \Delta \log (\lambda),
$$
where $\Delta_g$ is the Laplace-Beltrami operator of the metric and  $\Delta = 4 \partial_z\bar{\partial_z} = \partial^2_x + \partial^2_y$ is the flat Laplacian.  
