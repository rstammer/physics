---
layout: topic
title: "Symmetries and Conservation Laws"
tags:
  - Classical Mechanics
  - Foundations
  - Symmetry
---

## The Central Idea

One of the deepest insights in physics is that **every continuous symmetry of a physical system corresponds to a conserved quantity**. This is **Noether's theorem**, and it connects two fundamental concepts:

- **Symmetry**: the action is invariant under a continuous family of transformations
- **Conservation law**: a quantity that does not change with time

This connection is not a coincidence — it is a mathematical theorem with a precise proof.

---

## Noether's Theorem

### Statement

Let <span class="math-inline">L(q, \dot{q}, t)</span> be a Lagrangian with <span class="math-inline">n</span> degrees of freedom. Suppose there is a one-parameter family of transformations

<span class="math-display">q_i \to q_i + \varepsilon \, \delta q_i(q, \dot{q}, t)</span>

that leaves the action invariant (i.e., <span class="math-inline">\delta L = \frac{d}{dt}\Lambda</span> for some function <span class="math-inline">\Lambda</span>). Then the quantity

<span class="math-display">Q = \sum_{i=1}^{n} \frac{\partial L}{\partial \dot{q}_i} \delta q_i - \Lambda</span>

is **conserved** along solutions of the Euler-Lagrange equations: <span class="math-inline">\frac{dQ}{dt} = 0</span>.

### Proof Sketch

Compute the time derivative of <span class="math-inline">Q</span>:

<span class="math-display">\frac{dQ}{dt} = \sum_{i} \left[\frac{d}{dt}\frac{\partial L}{\partial \dot{q}_i}\right] \delta q_i + \sum_{i} \frac{\partial L}{\partial \dot{q}_i} \frac{d(\delta q_i)}{dt} - \frac{d\Lambda}{dt}</span>

Using the Euler-Lagrange equations <span class="math-inline">\frac{d}{dt}\frac{\partial L}{\partial \dot{q}_i} = \frac{\partial L}{\partial q_i}</span>, the first sum becomes <span class="math-inline">\sum_i \frac{\partial L}{\partial q_i} \delta q_i</span>. Combined with the second sum:

<span class="math-display">\frac{dQ}{dt} = \sum_{i} \frac{\partial L}{\partial q_i}\delta q_i + \sum_{i} \frac{\partial L}{\partial \dot{q}_i}\delta\dot{q}_i - \frac{d\Lambda}{dt} = \delta L - \frac{d\Lambda}{dt} = 0</span>

The last equality holds because the symmetry condition requires <span class="math-inline">\delta L = \frac{d\Lambda}{dt}</span>. <span class="math-inline">\square</span>

---

## The Three Fundamental Examples

### 1. Space Translation → Momentum Conservation

**Symmetry**: The Lagrangian is invariant under spatial translation <span class="math-inline">q_i \to q_i + \varepsilon</span> in direction <span class="math-inline">i</span>.

This means <span class="math-inline">\frac{\partial L}{\partial q_i} = 0</span> — the coordinate <span class="math-inline">q_i</span> is **cyclic** (does not appear explicitly in <span class="math-inline">L</span>).

**Conserved quantity**: The conjugate momentum

<span class="math-display">p_i = \frac{\partial L}{\partial \dot{q}_i}</span>

The Euler-Lagrange equation directly gives <span class="math-inline">\dot{p}_i = \frac{\partial L}{\partial q_i} = 0</span>.

**Example**: A free particle <span class="math-inline">L = \frac{1}{2}m(\dot{x}^2 + \dot{y}^2 + \dot{z}^2)</span> is translation-invariant in all three directions. All three components of momentum <span class="math-inline">\mathbf{p} = m\dot{\mathbf{x}}</span> are conserved.

**Example**: A particle in a potential <span class="math-inline">V(x, y) = V(r)</span> that depends only on <span class="math-inline">r = \sqrt{x^2 + y^2}</span>. In polar coordinates, <span class="math-inline">\theta</span> is cyclic, so the angular momentum <span class="math-inline">p_\theta = mr^2\dot{\theta}</span> is conserved.

### 2. Time Translation → Energy Conservation

**Symmetry**: The Lagrangian does not depend explicitly on time: <span class="math-inline">\frac{\partial L}{\partial t} = 0</span>.

**Conserved quantity**: The **energy** (Hamiltonian)

<span class="math-display">E = H = \sum_{i} p_i \dot{q}_i - L</span>

**Proof**: Compute directly:

<span class="math-display">\frac{dL}{dt} = \sum_i \frac{\partial L}{\partial q_i}\dot{q}_i + \sum_i \frac{\partial L}{\partial \dot{q}_i}\ddot{q}_i + \frac{\partial L}{\partial t}</span>

Using the Euler-Lagrange equations:

<span class="math-display">\frac{dL}{dt} = \sum_i \frac{d}{dt}\left(\frac{\partial L}{\partial \dot{q}_i}\dot{q}_i\right) + \frac{\partial L}{\partial t}</span>

Therefore:

<span class="math-display">\frac{d}{dt}\left(\sum_i p_i\dot{q}_i - L\right) = -\frac{\partial L}{\partial t} = 0</span>

For a standard Lagrangian <span class="math-inline">L = T - V</span> where <span class="math-inline">T</span> is quadratic in velocities, <span class="math-inline">H = T + V</span> = total energy.

### 3. Rotation → Angular Momentum Conservation

**Symmetry**: The Lagrangian is invariant under rotations around an axis, say the <span class="math-inline">z</span>-axis:

<span class="math-display">x \to x - \varepsilon \, y, \qquad y \to y + \varepsilon \, x</span>

(infinitesimal rotation by angle <span class="math-inline">\varepsilon</span>).

**Conserved quantity**: The <span class="math-inline">z</span>-component of **angular momentum**

<span class="math-display">L_z = xp_y - yp_x = m(x\dot{y} - y\dot{x})</span>

**Full rotational symmetry**: If <span class="math-inline">L</span> is invariant under all rotations (e.g., a central force), all three components of <span class="math-inline">\mathbf{L} = \mathbf{x} \times \mathbf{p}</span> are conserved.

---

## Summary Table

| Symmetry | Transformation | Conserved Quantity |
|----------|---------------|-------------------|
| Space translation | <span class="math-inline">q_i \to q_i + \varepsilon</span> | Momentum <span class="math-inline">p_i</span> |
| Time translation | <span class="math-inline">t \to t + \varepsilon</span> | Energy <span class="math-inline">H</span> |
| Rotation | <span class="math-inline">\mathbf{x} \to R(\varepsilon)\mathbf{x}</span> | Angular momentum <span class="math-inline">\mathbf{L}</span> |
| Boost (Galilean) | <span class="math-inline">\mathbf{x} \to \mathbf{x} + \varepsilon t \, \hat{\mathbf{n}}</span> | Center-of-mass motion <span class="math-inline">m\mathbf{X} - \mathbf{P}t</span> |

These four symmetries generate the **Galilean group**, the symmetry group of non-relativistic mechanics.

---

## Noether's Theorem in the Hamiltonian Framework

In the Hamiltonian formulation, Noether's theorem takes an elegant algebraic form. A conserved quantity <span class="math-inline">Q</span> satisfies:

<span class="math-display">\{Q, H\} = 0</span>

Moreover, <span class="math-inline">Q</span> **generates** the symmetry transformation via the Poisson bracket:

<span class="math-display">\delta f = \varepsilon\{f, Q\}</span>

**Examples**:
- Momentum <span class="math-inline">p_i</span> generates translations: <span class="math-inline">\{q_j, p_i\} = \delta_{ij}</span>
- Angular momentum <span class="math-inline">L_z</span> generates rotations: <span class="math-inline">\{x, L_z\} = -y</span>, <span class="math-inline">\{y, L_z\} = x</span>
- The Hamiltonian <span class="math-inline">H</span> generates time evolution: <span class="math-inline">\{f, H\} = \dot{f}</span>

The conserved quantities form a **Lie algebra** under the Poisson bracket. For the Galilean group, the angular momentum components satisfy:

<span class="math-display">\{L_i, L_j\} = \varepsilon_{ijk}L_k</span>

This is the Lie algebra <span class="math-inline">\mathfrak{so}(3)</span> — the same algebra that governs spin in quantum mechanics.

---

## Outlook: Gauge Symmetries in Field Theory

In field theory, Noether's theorem generalizes to **local** (gauge) symmetries and yields far-reaching consequences:

| Classical Symmetry | Field Theory Analogue | Consequence |
|-------------------|----------------------|-------------|
| Global phase <span class="math-inline">U(1)</span> | Electromagnetic gauge symmetry | Electric charge conservation |
| <span class="math-inline">SU(2)</span> isospin | Weak gauge symmetry | Weak charge conservation |
| <span class="math-inline">SU(3)</span> color | Strong gauge symmetry | Color charge conservation |
| Spacetime translations | General covariance | Energy-momentum conservation |

The entire structure of the Standard Model — with its gauge group <span class="math-inline">SU(3) \times SU(2) \times U(1)</span> — is built on the idea that symmetries dictate dynamics. This idea begins here, with Noether's theorem in classical mechanics.

---

## References

- E. Noether, "Invariante Variationsprobleme," *Nachrichten von der Gesellschaft der Wissenschaften zu Göttingen* (1918), pp. 235–257
- L. D. Landau and E. M. Lifshitz, *Mechanics*, 3rd ed. (Pergamon, 1976), Chapters 2, 4
- V. I. Arnold, *Mathematical Methods of Classical Mechanics*, 2nd ed. (Springer, 1989), Chapter 4
- H. Goldstein, C. Poole, and J. Safko, *Classical Mechanics*, 3rd ed. (Addison-Wesley, 2002), Chapters 2, 13
- Y. Kosmann-Schwarzbach, *The Noether Theorems: Invariance and Conservation Laws in the Twentieth Century* (Springer, 2011)
