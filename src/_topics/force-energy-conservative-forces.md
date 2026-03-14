---
layout: topic
title: "Force, Energy, and Conservative Forces"
tags:
  - Classical Mechanics
  - Foundations
---

## How Force Is Modeled

In Newtonian mechanics, a **force** is a vector-valued function that tells a particle how to accelerate:

<span class="math-display">\mathbf{F} = m\mathbf{a} = m\frac{d^2\mathbf{x}}{dt^2}</span>

More precisely, a force is a map that assigns to each point in space (and possibly time and velocity) a vector:

<span class="math-display">\mathbf{F}: \mathbb{R}^3 \times \mathbb{R}^3 \times \mathbb{R} \to \mathbb{R}^3, \quad (\mathbf{x}, \dot{\mathbf{x}}, t) \mapsto \mathbf{F}(\mathbf{x}, \dot{\mathbf{x}}, t)</span>

When the force depends only on position — <span class="math-inline">\mathbf{F} = \mathbf{F}(\mathbf{x})</span> — it defines a **vector field** on <span class="math-inline">\mathbb{R}^3</span>. This is the most important case, and it is the setting in which the concept of energy becomes powerful.

---

## Work: The Bridge from Force to Energy

### Definition

The **work** done by a force <span class="math-inline">\mathbf{F}</span> along a path <span class="math-inline">\gamma</span> from point <span class="math-inline">A</span> to point <span class="math-inline">B</span> is the line integral:

<span class="math-display">W_{A \to B} = \int_\gamma \mathbf{F} \cdot d\mathbf{x} = \int_{t_A}^{t_B} \mathbf{F}(\mathbf{x}(t)) \cdot \dot{\mathbf{x}}(t) \, dt</span>

Work measures how much the force "pushes along" the direction of motion. It is a scalar — the accumulated dot product of force and displacement.

### The Work-Energy Theorem

For a particle of mass <span class="math-inline">m</span>, Newton's second law gives:

<span class="math-display">\mathbf{F} \cdot \dot{\mathbf{x}} = m\ddot{\mathbf{x}} \cdot \dot{\mathbf{x}} = \frac{d}{dt}\left(\frac{1}{2}m|\dot{\mathbf{x}}|^2\right)</span>

Integrating both sides:

<span class="math-display">W_{A \to B} = \int_{t_A}^{t_B} \frac{d}{dt}\left(\frac{1}{2}m|\dot{\mathbf{x}}|^2\right) dt = \frac{1}{2}mv_B^2 - \frac{1}{2}mv_A^2</span>

This is the **work-energy theorem**: the work done by the net force equals the change in kinetic energy.

<span class="math-display">W = \Delta T, \quad T = \frac{1}{2}m|\dot{\mathbf{x}}|^2</span>

This holds for **any** force — conservative or not. It is a direct consequence of Newton's second law.

---

## How Energy Is Modeled

### Kinetic Energy

**Kinetic energy** is the energy of motion:

<span class="math-display">T = \frac{1}{2}m|\dot{\mathbf{x}}|^2 = \frac{1}{2}m(\dot{x}_1^2 + \dot{x}_2^2 + \dot{x}_3^2)</span>

It is always non-negative and depends only on the speed, not the direction of motion. For a system of <span class="math-inline">N</span> particles:

<span class="math-display">T = \sum_{i=1}^{N} \frac{1}{2}m_i|\dot{\mathbf{x}}_i|^2</span>

### Potential Energy

**Potential energy** is energy stored in configuration — it depends on *where* a particle is, not how fast it moves. But potential energy only exists for a special class of forces: **conservative forces**.

If a force <span class="math-inline">\mathbf{F}</span> is conservative (defined precisely below), then there exists a scalar function <span class="math-inline">V: \mathbb{R}^3 \to \mathbb{R}</span> such that:

<span class="math-display">\mathbf{F}(\mathbf{x}) = -\nabla V(\mathbf{x}) = -\left(\frac{\partial V}{\partial x_1}, \frac{\partial V}{\partial x_2}, \frac{\partial V}{\partial x_3}\right)</span>

The function <span class="math-inline">V</span> is the **potential energy**. The minus sign is a convention: the force points "downhill" — in the direction of decreasing potential.

### Total Energy

The **total mechanical energy** is:

<span class="math-display">E = T + V = \frac{1}{2}m|\dot{\mathbf{x}}|^2 + V(\mathbf{x})</span>

The central question is: **when is <span class="math-inline">E</span> conserved?** The answer leads directly to the concept of conservative forces.

---

## What It Means to Be a Conservative Force

### Definition

A force <span class="math-inline">\mathbf{F}(\mathbf{x})</span> is **conservative** if the work it does depends only on the endpoints, not on the path taken between them:

<span class="math-display">\int_{\gamma_1} \mathbf{F} \cdot d\mathbf{x} = \int_{\gamma_2} \mathbf{F} \cdot d\mathbf{x}</span>

for any two paths <span class="math-inline">\gamma_1, \gamma_2</span> from <span class="math-inline">A</span> to <span class="math-inline">B</span>.

### Why "Conservative"?

The name comes from **conservation of energy**. If a force is conservative, then the total mechanical energy <span class="math-inline">E = T + V</span> is a constant of the motion:

<span class="math-display">\frac{dE}{dt} = \frac{d}{dt}\left(\frac{1}{2}m|\dot{\mathbf{x}}|^2 + V(\mathbf{x})\right) = m\ddot{\mathbf{x}} \cdot \dot{\mathbf{x}} + \nabla V \cdot \dot{\mathbf{x}} = (\mathbf{F} + \nabla V) \cdot \dot{\mathbf{x}} = 0</span>

since <span class="math-inline">\mathbf{F} = -\nabla V</span>. Energy is **conserved** — it is neither created nor destroyed, only converted between kinetic and potential forms.

For a non-conservative force like friction, energy is **not** conserved. Kinetic energy is converted to heat, which is not captured by <span class="math-inline">V(\mathbf{x})</span>. The name "conservative" literally means: this force conserves mechanical energy.

### Four Equivalent Characterizations

For a force field <span class="math-inline">\mathbf{F}: \mathbb{R}^3 \to \mathbb{R}^3</span> (smooth, defined on a simply connected domain), the following are equivalent:

**(1) Path independence.** The work <span class="math-inline">\int_\gamma \mathbf{F} \cdot d\mathbf{x}</span> depends only on the endpoints.

**(2) Vanishing loop integral.** For any closed curve <span class="math-inline">\gamma</span>:

<span class="math-display">\oint_\gamma \mathbf{F} \cdot d\mathbf{x} = 0</span>

**(3) Gradient field.** There exists a potential <span class="math-inline">V</span> such that <span class="math-inline">\mathbf{F} = -\nabla V</span>.

**(4) Curl-free.** The curl of <span class="math-inline">\mathbf{F}</span> vanishes everywhere:

<span class="math-display">\nabla \times \mathbf{F} = \mathbf{0}</span>

These equivalences are deep results from vector calculus (the gradient theorem and Stokes' theorem). They give physicists multiple ways to check whether a force is conservative.

### Why the equivalences hold (sketch)

- **(1) ⟺ (2):** If the integral over any closed loop is zero, then two paths between the same endpoints give the same result (subtract them to get a loop).
- **(3) ⟹ (1):** If <span class="math-inline">\mathbf{F} = -\nabla V</span>, then by the gradient theorem: <span class="math-inline">\int_\gamma \mathbf{F} \cdot d\mathbf{x} = V(A) - V(B)</span>, which depends only on endpoints.
- **(1) ⟹ (3):** Define <span class="math-inline">V(\mathbf{x}) = -\int_{A}^{\mathbf{x}} \mathbf{F} \cdot d\mathbf{x}</span>. Path independence guarantees this is well-defined.
- **(3) ⟺ (4):** <span class="math-inline">\nabla \times (\nabla V) = \mathbf{0}</span> always (a vector calculus identity). Conversely, on a simply connected domain, curl-free implies gradient (Poincaré lemma).

---

## Examples

### Conservative Forces

**Gravity (uniform field):**

<span class="math-display">\mathbf{F} = -mg\hat{\mathbf{z}}, \quad V = mgz</span>

Check: <span class="math-inline">\nabla \times \mathbf{F} = \mathbf{0}</span>. The work done lifting a mass from height <span class="math-inline">z_1</span> to <span class="math-inline">z_2</span> is <span class="math-inline">mg(z_2 - z_1)</span>, regardless of the path — whether you go straight up, along a ramp, or in spirals.

**Gravity (Newtonian, central):**

<span class="math-display">\mathbf{F} = -\frac{GMm}{r^2}\hat{\mathbf{r}}, \quad V = -\frac{GMm}{r}</span>

The potential depends only on the distance <span class="math-inline">r</span> from the source. All central forces <span class="math-inline">\mathbf{F} = f(r)\hat{\mathbf{r}}</span> are conservative.

**Spring force (Hooke's law):**

<span class="math-display">F = -kx, \quad V = \frac{1}{2}kx^2</span>

The potential is a parabola — the harmonic oscillator potential. See [The Harmonic Oscillator](/physics/topics/harmonic-oscillator/) for a full treatment.

**Electrostatic force (Coulomb):**

<span class="math-display">\mathbf{F} = \frac{1}{4\pi\varepsilon_0}\frac{q_1 q_2}{r^2}\hat{\mathbf{r}}, \quad V = \frac{1}{4\pi\varepsilon_0}\frac{q_1 q_2}{r}</span>

Mathematically identical in structure to Newtonian gravity, but can be repulsive (same-sign charges).

### Non-Conservative Forces

**Kinetic friction:**

<span class="math-display">\mathbf{F}_{\text{friction}} = -\mu_k N \hat{\mathbf{v}}</span>

Friction always opposes the direction of motion. Sliding a book from <span class="math-inline">A</span> to <span class="math-inline">B</span> and back to <span class="math-inline">A</span> does **not** return zero work — friction dissipates energy on each leg. The loop integral is negative, so friction is not conservative.

**Air resistance (drag):**

<span class="math-display">\mathbf{F}_{\text{drag}} = -b\dot{\mathbf{x}} \quad \text{(linear)} \quad \text{or} \quad \mathbf{F}_{\text{drag}} = -c|\dot{\mathbf{x}}|\dot{\mathbf{x}} \quad \text{(quadratic)}</span>

Drag depends on **velocity**, not just position. It cannot be written as <span class="math-inline">-\nabla V(\mathbf{x})</span> and always removes kinetic energy from the system.

**Magnetic force (Lorentz):**

<span class="math-display">\mathbf{F} = q\dot{\mathbf{x}} \times \mathbf{B}</span>

This force is always perpendicular to the velocity, so it does **no work** (<span class="math-inline">\mathbf{F} \cdot \dot{\mathbf{x}} = 0</span>). It is not conservative in the usual sense (it depends on velocity), but it does not change the energy — a special case.

---

## Energy Diagrams: Visualizing Conservative Forces

For one-dimensional conservative systems, the potential <span class="math-inline">V(x)</span> contains all the information about the motion. Since <span class="math-inline">E = \frac{1}{2}m\dot{x}^2 + V(x)</span> is constant:

<span class="math-display">\frac{1}{2}m\dot{x}^2 = E - V(x) \geq 0</span>

The particle can only exist where <span class="math-inline">V(x) \leq E</span>. The points where <span class="math-inline">V(x) = E</span> are the **turning points** — the particle stops and reverses direction.

**Reading an energy diagram:**

- **Local minima** of <span class="math-inline">V(x)</span> are **stable equilibria** — small displacements lead to oscillation (harmonic oscillator near the minimum)
- **Local maxima** of <span class="math-inline">V(x)</span> are **unstable equilibria** — small displacements lead to runaway
- **The force** at any point is the negative slope: <span class="math-inline">F = -dV/dx</span>
- The **kinetic energy** at any point is the vertical gap between <span class="math-inline">E</span> and <span class="math-inline">V(x)</span>

This graphical method allows you to understand the qualitative motion of a particle without solving the differential equation.

---

## Connection to the Lagrangian Formulation

In the Lagrangian formulation, the distinction between conservative and non-conservative forces becomes structural.

The **Lagrangian** for a conservative system is:

<span class="math-display">L = T - V</span>

and the equations of motion follow from the Euler-Lagrange equation:

<span class="math-display">\frac{d}{dt}\frac{\partial L}{\partial \dot{q}_i} - \frac{\partial L}{\partial q_i} = 0</span>

Non-conservative forces (friction, drag) cannot be derived from a potential and must be added by hand:

<span class="math-display">\frac{d}{dt}\frac{\partial L}{\partial \dot{q}_i} - \frac{\partial L}{\partial q_i} = Q_i^{\text{non-cons}}</span>

This is one reason the Lagrangian framework is so powerful for conservative systems: all forces are encoded in a single scalar function <span class="math-inline">L</span>, and energy conservation follows automatically from the structure. See [What is a Lagrangian?](/physics/topics/what-is-a-lagrangian/) and [Lagrangian and Hamiltonian Formalism](/physics/topics/lagrangian-hamiltonian-formalism/) for details.

---

## Connection to Symmetry

Energy conservation is not an accident — it is a consequence of **time-translation symmetry** via Noether's theorem.

If the Lagrangian does not depend explicitly on time (<span class="math-inline">\partial L / \partial t = 0</span>), then the **Hamiltonian**:

<span class="math-display">H = \sum_i \dot{q}_i \frac{\partial L}{\partial \dot{q}_i} - L</span>

is conserved. For standard systems where <span class="math-inline">T</span> is quadratic in velocities and <span class="math-inline">V</span> depends only on positions, <span class="math-inline">H = T + V = E</span>.

**Conservative force** → potential energy exists → Lagrangian has no explicit time dependence → Noether's theorem → energy conservation.

This chain of reasoning connects the elementary concept of a conservative force to one of the deepest principles in physics.

---

## Summary

| Concept | Mathematical Object | Key Property |
|---------|-------------------|--------------|
| Force | Vector field <span class="math-inline">\mathbf{F}(\mathbf{x})</span> | Determines acceleration |
| Work | Line integral <span class="math-inline">\int \mathbf{F} \cdot d\mathbf{x}</span> | Equals change in kinetic energy |
| Conservative force | Curl-free / gradient field | Work is path-independent |
| Potential energy | Scalar field <span class="math-inline">V(\mathbf{x})</span> | <span class="math-inline">\mathbf{F} = -\nabla V</span> |
| Total energy | <span class="math-inline">E = T + V</span> | Conserved for conservative forces |

**The key insight:** A conservative force is one for which a potential energy function exists. This means mechanical energy is conserved, the force does no net work around closed loops, and the physics can be encoded in a single scalar function rather than a vector field. This simplification — from vectors to scalars — is what makes the concept so powerful, and it is the doorway to the Lagrangian and Hamiltonian formulations that underpin all of modern physics.

---

## References

- D. J. Griffiths, *Introduction to Electrodynamics*, 4th ed. (Cambridge University Press, 2017), Chapter 2 — Clear treatment of conservative fields and potentials
- H. Goldstein, C. Poole, and J. Safko, *Classical Mechanics*, 3rd ed. (Addison-Wesley, 2002), Chapter 1 — Forces, constraints, and the work-energy theorem
- V. I. Arnold, *Mathematical Methods of Classical Mechanics*, 2nd ed. (Springer, 1989) — Rigorous geometric perspective on conservative systems
- R. P. Feynman, R. B. Leighton, and M. Sands, *The Feynman Lectures on Physics*, Vol. I (Basic Books, 2011), Chapters 13–14 — Intuitive introduction to work and energy
- L. D. Landau and E. M. Lifshitz, *Mechanics*, 3rd ed. (Butterworth-Heinemann, 1976), §5–6 — Energy conservation from the Lagrangian perspective
