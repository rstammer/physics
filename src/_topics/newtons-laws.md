---
layout: topic
title: "Newton's Laws of Motion"
tags:
  - Classical Mechanics
  - Foundations
---

## Overview

Newton's three laws of motion form the foundation of classical mechanics. They describe how objects move under the influence of forces and establish the framework that all later formulations — Lagrangian, Hamiltonian, and ultimately quantum mechanics — build upon.

For a reader with a mathematical background, Newton's laws are best understood as a system of ordinary differential equations on <span class="math-inline">\mathbb{R}^3</span>, with forces as the driving terms.

---

## The Three Laws

### First Law (Inertia)

*A body remains at rest or in uniform straight-line motion unless acted upon by a net external force.*

Mathematically: if <span class="math-inline">\mathbf{F} = 0</span>, then

<span class="math-display">\frac{d\mathbf{v}}{dt} = 0 \quad \Longrightarrow \quad \mathbf{v}(t) = \mathbf{v}_0 = \text{const.}</span>

This law is more subtle than it appears — it defines the existence of **inertial reference frames**, i.e., coordinate systems in which the law holds. The mathematical content is that such frames exist and are related by the **Galilean group** of transformations:

<span class="math-display">\mathbf{x}' = R\mathbf{x} + \mathbf{v}t + \mathbf{a}, \quad t' = t + s</span>

where <span class="math-inline">R \in O(3)</span>, <span class="math-inline">\mathbf{v}, \mathbf{a} \in \mathbb{R}^3</span>, and <span class="math-inline">s \in \mathbb{R}</span>.

### Second Law (F = ma)

*The rate of change of momentum equals the applied force.*

<span class="math-display">\mathbf{F} = \frac{d\mathbf{p}}{dt} = \frac{d(m\mathbf{v})}{dt}</span>

For constant mass, this becomes the fundamental equation of Newtonian mechanics:

<span class="math-display">\mathbf{F} = m\mathbf{a} = m\frac{d^2\mathbf{x}}{dt^2}</span>

This is a **second-order ODE** for the trajectory <span class="math-inline">\mathbf{x}(t) \in \mathbb{R}^3</span>. Given a force law <span class="math-inline">\mathbf{F}(\mathbf{x}, \dot{\mathbf{x}}, t)</span> and initial conditions <span class="math-inline">(\mathbf{x}_0, \mathbf{v}_0)</span>, the Picard-Lindelöf theorem guarantees a unique local solution (provided <span class="math-inline">\mathbf{F}</span> is Lipschitz continuous).

**Example: Free fall near Earth's surface**

<span class="math-display">m\ddot{y} = -mg \quad \Longrightarrow \quad \ddot{y} = -g</span>

Solution:

<span class="math-display">y(t) = y_0 + v_0 t - \frac{1}{2}g t^2</span>

**Example: One-dimensional motion in a potential**

If <span class="math-inline">F = -V'(x)</span> (force derived from a potential), the equation of motion is:

<span class="math-display">m\ddot{x} = -\frac{dV}{dx}</span>

This structure — force as the negative gradient of a potential — is the starting point for the Lagrangian formulation.

### Third Law (Action and Reaction)

*For every force that body A exerts on body B, body B exerts an equal and opposite force on body A.*

<span class="math-display">\mathbf{F}_{A \to B} = -\mathbf{F}_{B \to A}</span>

This law has an important mathematical consequence: it guarantees **conservation of total momentum** for a closed system. For two particles:

<span class="math-display">\frac{d}{dt}(\mathbf{p}_1 + \mathbf{p}_2) = \mathbf{F}_{2 \to 1} + \mathbf{F}_{1 \to 2} = 0</span>

More generally, for <span class="math-inline">N</span> particles with pairwise forces satisfying the third law, the total momentum <span class="math-inline">\mathbf{P} = \sum_{i=1}^{N} m_i \dot{\mathbf{x}}_i</span> is conserved.

---

## Systems of Particles

For <span class="math-inline">N</span> particles, Newton's second law gives a system of <span class="math-inline">3N</span> coupled second-order ODEs:

<span class="math-display">m_i \ddot{\mathbf{x}}_i = \mathbf{F}_i^{\text{ext}} + \sum_{j \neq i} \mathbf{F}_{ji}, \quad i = 1, \ldots, N</span>

The **configuration space** is <span class="math-inline">\mathbb{R}^{3N}</span>, and the state of the system at any time is a point in the **phase space** <span class="math-inline">\mathbb{R}^{6N}</span> (positions and velocities).

### Center of Mass

The center of mass <span class="math-inline">\mathbf{X} = \frac{1}{M}\sum_i m_i \mathbf{x}_i</span> (with <span class="math-inline">M = \sum_i m_i</span>) obeys:

<span class="math-display">M\ddot{\mathbf{X}} = \mathbf{F}^{\text{ext}}_{\text{total}}</span>

The internal forces cancel by Newton's third law. This reduces the problem: the center of mass moves as if it were a single particle.

---

## Forces in Newtonian Mechanics

### Gravity

Newton's law of gravitation between two masses:

<span class="math-display">\mathbf{F} = -\frac{Gm_1 m_2}{|\mathbf{x}_1 - \mathbf{x}_2|^2}\hat{\mathbf{r}}_{12}</span>

This is a **conservative force** derivable from the potential:

<span class="math-display">V(r) = -\frac{Gm_1 m_2}{r}</span>

### Spring Force (Hooke's Law)

<span class="math-display">F = -kx</span>

This leads to the harmonic oscillator — see the dedicated topic [The Harmonic Oscillator](/qft/topics/harmonic-oscillator/) for a thorough treatment.

---

## Energy Conservation

For a particle in a potential <span class="math-inline">V(\mathbf{x})</span>, define the total energy:

<span class="math-display">E = \frac{1}{2}m|\dot{\mathbf{x}}|^2 + V(\mathbf{x})</span>

Then:

<span class="math-display">\frac{dE}{dt} = m\dot{\mathbf{x}} \cdot \ddot{\mathbf{x}} + \nabla V \cdot \dot{\mathbf{x}} = \dot{\mathbf{x}} \cdot (m\ddot{\mathbf{x}} + \nabla V) = 0</span>

since <span class="math-inline">m\ddot{\mathbf{x}} = -\nabla V</span>. Energy is **conserved** for conservative forces.

---

## Limitations and Beyond

Newton's laws work extraordinarily well for everyday scales, but they have limitations:

1. **Constrained systems**: For particles on surfaces or curves, constraint forces are awkward to handle. The Lagrangian formulation handles constraints naturally via generalized coordinates.

2. **Non-inertial frames**: Fictitious forces (Coriolis, centrifugal) must be added. The Lagrangian approach treats all frames uniformly.

3. **Many degrees of freedom**: The vector equation <span class="math-inline">\mathbf{F} = m\mathbf{a}</span> becomes unwieldy. Lagrangian and Hamiltonian methods provide systematic tools.

4. **Connection to quantum mechanics**: There is no obvious path from <span class="math-inline">\mathbf{F} = m\mathbf{a}</span> to quantum mechanics. The Hamiltonian formulation leads directly to canonical quantization.

These motivations lead to the [Lagrangian and Hamiltonian Formalism](/qft/topics/lagrangian-hamiltonian-formalism/), which reformulates classical mechanics in a way that generalizes to field theory and quantum mechanics.

---

## References

- I. Newton, *Philosophiæ Naturalis Principia Mathematica* (1687)
- L. D. Landau and E. M. Lifshitz, *Mechanics*, 3rd ed. (Pergamon, 1976), Chapter 1
- V. I. Arnold, *Mathematical Methods of Classical Mechanics*, 2nd ed. (Springer, 1989), Part I
- H. Goldstein, C. Poole, and J. Safko, *Classical Mechanics*, 3rd ed. (Addison-Wesley, 2002), Chapter 1
- D. Tong, *Lectures on Classical Dynamics* — [Free online notes](http://www.damtp.cam.ac.uk/user/tong/dynamics.html)
