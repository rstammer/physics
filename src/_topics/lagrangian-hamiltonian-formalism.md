---
layout: topic
title: "Lagrangian and Hamiltonian Formalism"
tags:
  - Classical Mechanics
  - Foundations
  - Lagrangian Mechanics
---

## Motivation: Why Go Beyond Newton?

Newton's <span class="math-inline">\mathbf{F} = m\mathbf{a}</span> works well for simple systems, but becomes unwieldy for constrained systems, curvilinear coordinates, or many degrees of freedom. More importantly, the Newtonian formulation does not generalize naturally to field theory or quantum mechanics.

The **Lagrangian formulation** replaces forces with a single scalar function and derives the equations of motion from a variational principle. The **Hamiltonian formulation** then reframes the problem in phase space, providing the direct bridge to quantum mechanics via canonical quantization.

For a detailed introduction to the Lagrangian itself, see [What is a Lagrangian?](/physics/topics/what-is-a-lagrangian/).

---

## Generalized Coordinates

A system with <span class="math-inline">n</span> degrees of freedom is described by **generalized coordinates** <span class="math-inline">q = (q_1, \ldots, q_n)</span>, which parametrize the **configuration space** <span class="math-inline">Q</span>. These need not be Cartesian — they can be angles, distances, or any coordinates adapted to the system's constraints.

**Example**: A pendulum of length <span class="math-inline">\ell</span> has one degree of freedom, the angle <span class="math-inline">\theta</span>. The configuration space is <span class="math-inline">Q = S^1</span>.

**Example**: A double pendulum has two angles <span class="math-inline">(\theta_1, \theta_2)</span>. The configuration space is <span class="math-inline">Q = S^1 \times S^1 = T^2</span> (the 2-torus).

The **generalized velocities** <span class="math-inline">\dot{q} = (\dot{q}_1, \ldots, \dot{q}_n)</span> live in the tangent bundle <span class="math-inline">TQ</span>.

---

## The Lagrangian

The **Lagrangian** is a function <span class="math-inline">L: TQ \times \mathbb{R} \to \mathbb{R}</span>:

<span class="math-display">L(q, \dot{q}, t) = T(q, \dot{q}) - V(q)</span>

where <span class="math-inline">T</span> is the kinetic energy and <span class="math-inline">V</span> is the potential energy.

---

## The Principle of Least Action

### The Action Functional

The **action** is a functional on the space of paths <span class="math-inline">q: [t_1, t_2] \to Q</span>:

<span class="math-display">S[q] = \int_{t_1}^{t_2} L(q(t), \dot{q}(t), t) \, dt</span>

### Variational Principle

The physical trajectory is a **stationary point** of the action: for all variations <span class="math-inline">\delta q(t)</span> with <span class="math-inline">\delta q(t_1) = \delta q(t_2) = 0</span>,

<span class="math-display">\delta S = 0</span>

### Derivation of the Euler-Lagrange Equations

Consider a variation <span class="math-inline">q(t) \to q(t) + \varepsilon \eta(t)</span> where <span class="math-inline">\eta(t_1) = \eta(t_2) = 0</span>. Then:

<span class="math-display">\frac{d}{d\varepsilon}\bigg|_{\varepsilon=0} S[q + \varepsilon\eta] = \int_{t_1}^{t_2} \left(\frac{\partial L}{\partial q}\eta + \frac{\partial L}{\partial \dot{q}}\dot{\eta}\right) dt</span>

Integrating the second term by parts (boundary terms vanish since <span class="math-inline">\eta</span> vanishes at the endpoints):

<span class="math-display">= \int_{t_1}^{t_2} \left(\frac{\partial L}{\partial q} - \frac{d}{dt}\frac{\partial L}{\partial \dot{q}}\right)\eta \, dt = 0</span>

Since this must hold for **all** <span class="math-inline">\eta</span>, the fundamental lemma of the calculus of variations gives the **Euler-Lagrange equations**:

<span class="math-display">\frac{d}{dt}\frac{\partial L}{\partial \dot{q}_i} - \frac{\partial L}{\partial q_i} = 0, \quad i = 1, \ldots, n</span>

### Example: Free Particle

<span class="math-display">L = \frac{1}{2}m\dot{x}^2</span>

Euler-Lagrange: <span class="math-inline">\frac{d}{dt}(m\dot{x}) = 0</span>, so <span class="math-inline">m\ddot{x} = 0</span> — Newton's first law.

### Example: Particle in a Potential

<span class="math-display">L = \frac{1}{2}m\dot{x}^2 - V(x)</span>

Euler-Lagrange: <span class="math-inline">m\ddot{x} = -V'(x)</span> — Newton's second law.

### Example: Pendulum

With <span class="math-inline">q = \theta</span>, the kinetic energy is <span class="math-inline">T = \frac{1}{2}m\ell^2\dot{\theta}^2</span> and the potential is <span class="math-inline">V = -mg\ell\cos\theta</span>, so:

<span class="math-display">L = \frac{1}{2}m\ell^2\dot{\theta}^2 + mg\ell\cos\theta</span>

Euler-Lagrange gives:

<span class="math-display">m\ell^2\ddot{\theta} = -mg\ell\sin\theta \quad \Longrightarrow \quad \ddot{\theta} + \frac{g}{\ell}\sin\theta = 0</span>

No need to decompose forces into components — the constraint is handled automatically.

---

## The Legendre Transformation

The passage from Lagrangian to Hamiltonian mechanics is a **Legendre transformation** — a standard construction from convex analysis.

### Conjugate Momenta

Define the **conjugate momentum** to <span class="math-inline">q_i</span>:

<span class="math-display">p_i = \frac{\partial L}{\partial \dot{q}_i}</span>

This defines a map from the tangent bundle <span class="math-inline">TQ</span> (positions and velocities) to the cotangent bundle <span class="math-inline">T^*Q</span> (positions and momenta). The cotangent bundle is the **phase space**.

### The Hamiltonian

The **Hamiltonian** is the Legendre transform of <span class="math-inline">L</span> with respect to the velocities:

<span class="math-display">H(q, p, t) = \sum_{i=1}^{n} p_i \dot{q}_i - L(q, \dot{q}, t)</span>

where <span class="math-inline">\dot{q}_i</span> is expressed in terms of <span class="math-inline">(q, p)</span> by inverting <span class="math-inline">p_i = \frac{\partial L}{\partial \dot{q}_i}</span>.

For a standard Lagrangian <span class="math-inline">L = T - V</span> with <span class="math-inline">T = \frac{1}{2}\sum_{ij} g_{ij}(q)\dot{q}_i\dot{q}_j</span>:

<span class="math-display">H = T + V = \text{total energy}</span>

---

## Hamilton's Equations

The Euler-Lagrange equations become a system of **first-order ODEs** in phase space:

<span class="math-display">\dot{q}_i = \frac{\partial H}{\partial p_i}, \qquad \dot{p}_i = -\frac{\partial H}{\partial q_i}</span>

These are **Hamilton's equations**. They have a beautiful geometric structure: the flow preserves the **symplectic form**

<span class="math-display">\omega = \sum_{i=1}^{n} dp_i \wedge dq_i</span>

on phase space. This is **Liouville's theorem**: Hamiltonian flows preserve phase space volume.

### Example: Harmonic Oscillator

<span class="math-display">H = \frac{p^2}{2m} + \frac{1}{2}m\omega^2 q^2</span>

Hamilton's equations:

<span class="math-display">\dot{q} = \frac{p}{m}, \qquad \dot{p} = -m\omega^2 q</span>

The phase space trajectories are **ellipses** — the system orbits forever with constant energy.

---

## Poisson Brackets

For any two functions <span class="math-inline">f, g</span> on phase space, the **Poisson bracket** is:

<span class="math-display">\{f, g\} = \sum_{i=1}^{n} \left(\frac{\partial f}{\partial q_i}\frac{\partial g}{\partial p_i} - \frac{\partial f}{\partial p_i}\frac{\partial g}{\partial q_i}\right)</span>

The fundamental brackets are:

<span class="math-display">\{q_i, q_j\} = 0, \qquad \{p_i, p_j\} = 0, \qquad \{q_i, p_j\} = \delta_{ij}</span>

Hamilton's equations take the compact form:

<span class="math-display">\dot{f} = \{f, H\}</span>

for any observable <span class="math-inline">f(q, p)</span>. A quantity is **conserved** if and only if <span class="math-inline">\{f, H\} = 0</span>.

The Poisson bracket gives the space of observables the structure of a **Lie algebra**. This structure survives quantization: the **canonical quantization** prescription replaces

<span class="math-display">\{f, g\} \longrightarrow \frac{1}{i\hbar}[\hat{f}, \hat{g}]</span>

This is why the Hamiltonian formulation is the natural starting point for quantum mechanics.

---

## Summary: Newton vs. Lagrange vs. Hamilton

| Aspect | Newton | Lagrange | Hamilton |
|--------|--------|----------|----------|
| Variables | <span class="math-inline">\mathbf{x}, \dot{\mathbf{x}}</span> | <span class="math-inline">q, \dot{q}</span> | <span class="math-inline">q, p</span> |
| Space | <span class="math-inline">\mathbb{R}^{3N}</span> | Configuration <span class="math-inline">TQ</span> | Phase space <span class="math-inline">T^*Q</span> |
| Equations | 2nd order ODE | 2nd order ODE | 1st order ODE |
| Central object | Force <span class="math-inline">\mathbf{F}</span> | Lagrangian <span class="math-inline">L</span> | Hamiltonian <span class="math-inline">H</span> |
| Constraints | Awkward | Natural | Natural |
| Symmetries | Case by case | Noether's theorem | Poisson brackets |
| Quantization | No direct path | Path integrals | Canonical quantization |

---

## Connection to Quantum Mechanics and QFT

The Hamiltonian formulation leads directly to quantum mechanics:
- **Canonical quantization**: Promote <span class="math-inline">q_i, p_j</span> to operators with <span class="math-inline">[\hat{q}_i, \hat{p}_j] = i\hbar\delta_{ij}</span>
- **Schrödinger equation**: <span class="math-inline">i\hbar\frac{\partial}{\partial t}|\psi\rangle = \hat{H}|\psi\rangle</span>

The Lagrangian formulation leads to quantum field theory:
- **Path integrals**: <span class="math-inline">\langle \text{out}|\text{in}\rangle = \int \mathcal{D}q \, e^{iS[q]/\hbar}</span>
- **Field theory Lagrangians**: Replace <span class="math-inline">L(q, \dot{q})</span> with <span class="math-inline">\mathcal{L}(\phi, \partial_\mu\phi)</span>

Both roads lead to quantum theory — and both start here, in classical mechanics.

---

## References

- L. D. Landau and E. M. Lifshitz, *Mechanics*, 3rd ed. (Pergamon, 1976), Chapters 1–7
- V. I. Arnold, *Mathematical Methods of Classical Mechanics*, 2nd ed. (Springer, 1989)
- H. Goldstein, C. Poole, and J. Safko, *Classical Mechanics*, 3rd ed. (Addison-Wesley, 2002), Chapters 2, 8–9
- R. Abraham and J. E. Marsden, *Foundations of Mechanics*, 2nd ed. (AMS Chelsea, 2008)
- D. Tong, *Lectures on Classical Dynamics* — [Free online notes](http://www.damtp.cam.ac.uk/user/tong/dynamics.html)
