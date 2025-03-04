# Numerical Modeling of Ultrasonic Wave Propagation Using Explicit FEM in ABAQUS

## 1. Governing Equations of Wave Propagation
The propagation of ultrasonic waves in a solid medium follows the **elastodynamic equation**, derived from **Newton’s Second Law** and **Hooke’s Law** for elastic materials.

### 1.1. Equation of Motion (Elastodynamic Equation)
$$
\rho \frac{\partial^2 u_i}{\partial t^2} = \nabla \cdot \sigma_{ij} + f_i
$$

where:
- $u_i$ is the displacement field $( i = x, y, z $)
- $\rho$ is the material density
- $\sigma_{ij}$ is the Cauchy stress tensor
- $f_i$ is the body force per unit volume (e.g., external loading)
- $\nabla \cdot \sigma_{ij}$ is the divergence of the stress tensor

For an **isotropic elastic medium**, the stress-strain relationship is given by **Hooke’s Law**:

$$
\sigma_{ij} = \lambda \delta_{ij} (\nabla \cdot \mathbf{u}) + 2\mu \varepsilon_{ij}
$$

where:
- $\lambda$ and $\mu$ are **Lamé’s constants**
- $\varepsilon_{ij}$ is the **strain tensor**, given by:

$$
\varepsilon_{ij} = \frac{1}{2} \left( \frac{\partial u_i}{\partial x_j} + \frac{\partial u_j}{\partial x_i} \right)
$$

This equation describes how ultrasonic waves propagate through the material.

---

## 2. Discretization Using the Finite Element Method (FEM)
FEM is used to discretize the problem spatially. The domain is divided into small **finite elements**, typically tetrahedral or hexahedral elements.

### 2.1. Discretization of Displacement Field
The displacement field is approximated using **nodal basis functions**:

$$
u_i(x,t) \approx \sum_{j} N_j(x) u_i^j(t)
$$

where:
- $ N_j(x) $ are shape functions (Lagrange basis functions)
- $ u_i^j(t) $ are the displacement values at the **nodes**

Using the Galerkin method, we obtain the **semi-discrete equation of motion**:

$$
M \ddot{U} + C \dot{U} + K U = F
$$

where:
- $M$ is the **mass matrix**
- $C$ is the **damping matrix**
- $K$ is the **stiffness matrix**
- $U$ is the **displacement vector**
- $F$ is the **external force vector**
- $\ddot{U} $ and $ \dot{U}$ are acceleration and velocity vectors

For **explicit FEM**, the damping matrix **$C$** is usually neglected, and the **mass matrix is lumped** (diagonalized) to simplify computations.

---

## 3. Time Integration Using the Explicit Method
In **explicit FEM**, the **Central Difference Method** is used for time integration.

### 3.1. Central Difference Scheme
The second-order time derivative is discretized as:

$$
\ddot{U}^{n} \approx \frac{U^{n+1} - 2U^n + U^{n-1}}{\Delta t^2}
$$

Solving for $ U^{n+1} $:

$$
U^{n+1} = 2U^n - U^{n-1} + \Delta t^2 M^{-1} (F^n - K U^n)
$$

where:
- $n$ refers to the current time step
- $\Delta t$ is the time step size
- $M^{-1}$ is the inverse of the mass matrix (easy to compute if **lumped**)

### 3.2. Stability Condition (Courant Condition)
For explicit FEM to remain stable, the **time step size** must satisfy the **Courant–Friedrichs–Lewy (CFL) condition**:

$$
\Delta t \leq \frac{L}{c}
$$

where:
- $L$ is the **smallest element length**
- $c$ is the **wave speed** in the material

For an isotropic elastic medium:

$$
c = \sqrt{\frac{E}{\rho (1 - \nu^2)}}
$$

where:
- $E$ is the Young’s modulus
- $\nu$ is the Poisson’s ratio

---

## 4. Implementation in ABAQUS Explicit
ABAQUS/Explicit uses the above **explicit time-stepping scheme** to solve ultrasonic wave propagation problems. The steps in implementation are:

### 4.1. Model Setup
- Define the **geometry** (solid domain)
- Mesh the domain using **small elements** (high-resolution for accuracy)
- Assign **material properties** ($\rho, E, \nu$)

### 4.2. Apply Initial and Boundary Conditions
- Define **initial displacement/velocity** (e.g., ultrasonic pulse)
- Apply **absorbing boundary conditions** (to prevent reflections)

### 4.3. Solving Using Explicit Dynamics
- Set the **time step size** using CFL condition
- Solve the **explicit FEM equations** using central difference integration
- Post-process **wave propagation results** (e.g., displacement, stress fields)

---

## 5. Interpretation of Results
- **Wavefront Visualization**: Study how ultrasonic waves propagate through the structure.
- **Mode Conversion**: Analyze how waves reflect, refract, and mode convert.
- **Defect Detection**: Use wave scattering to identify material defects.

---

## Summary
1. The **elastodynamic wave equation** governs ultrasonic wave propagation.
2. FEM discretizes the domain, leading to a **matrix equation of motion**.
3. The **explicit central difference method** is used for time integration.
4. Stability is maintained by choosing a **small time step** $\Delta t$).
5. ABAQUS/Explicit follows these steps automatically, allowing visualization of **wave propagation**.

---
# Weak Form Formulation of the Elastodynamic Equation

## 1. Strong Form (Differential Equation)
The governing equation for ultrasonic wave propagation in a **linear elastic solid** is given by the **elastodynamic equation**:

 $$
\rho \frac{\partial^2 u_i}{\partial t^2} = \nabla \cdot \sigma_{ij} + f_i
 $$

where:
- $u_i$ is the displacement field $( i = x, y, z $).
- $\rho$ is the **material density**.
- $\sigma_{ij}$ is the **Cauchy stress tensor**.
- $f_i$ is the **body force per unit volume**.
- $\nabla \cdot \sigma_{ij}$ represents the **internal force due to stress divergence**.

For an **isotropic elastic medium**, the stress-strain relationship follows **Hooke’s Law**:

 $$
\sigma_{ij} = \lambda \delta_{ij} (\nabla \cdot \mathbf{u}) + 2\mu \varepsilon_{ij}
 $$

where:
- $\lambda$ and $\mu$ are **Lamé’s constants**.
- The **strain tensor** is defined as:

 $$
\varepsilon_{ij} = \frac{1}{2} \left( \frac{\partial u_i}{\partial x_j} + \frac{\partial u_j}{\partial x_i} \right)
 $$

### Boundary Conditions
The strong form is subjected to **boundary conditions**:

1. **Dirichlet (Essential) Boundary Condition** - Prescribed displacement on **$\Gamma_u$**:
  $$
   u_i = \bar{u}_i \quad \text{on } \Gamma_u
  $$
2. **Neumann (Natural) Boundary Condition** - Prescribed traction on **$\Gamma_t$**:
 $$
   \sigma_{ij} n_j = t_i \quad \text{on } \Gamma_t
 $$
where:
- $\Gamma_u$ and $\Gamma_t$ are parts of the boundary.
- $t_i$ is the **applied traction**.
- $n_j$ is the **unit outward normal**.

---

## 2. Weak Form Formulation

The weak form is obtained by multiplying the **strong form equation** by a **test function** $v_i$ (arbitrary virtual displacement) and integrating over the domain $\Omega$:

 $$
\int_{\Omega} \rho \frac{\partial^2 u_i}{\partial t^2} v_i \, d\Omega = \int_{\Omega} (\nabla \cdot \sigma_{ij} + f_i) v_i \, d\Omega
 $$

### 2.1. Applying Integration by Parts (Divergence Theorem)

Using **Gauss' divergence theorem**, the term \( \nabla \cdot \sigma_{ij} \) is transformed as:

 $$
\int_{\Omega} (\nabla \cdot \sigma_{ij}) v_i \, d\Omega = \int_{\Gamma} v_i \sigma_{ij} n_j \, d\Gamma - \int_{\Omega} \sigma_{ij} \frac{\partial v_i}{\partial x_j} \, d\Omega
 $$

Substituting this into the weak form equation:

 $$
\int_{\Omega} \rho \frac{\partial^2 u_i}{\partial t^2} v_i \, d\Omega + \int_{\Omega} \sigma_{ij} \frac{\partial v_i}{\partial x_j} \, d\Omega = \int_{\Omega} f_i v_i \, d\Omega + \int_{\Gamma_t} t_i v_i \, d\Gamma
 $$

This is the **weak form of the elastodynamic equation**.

---

## 3. Finite Element Approximation

To solve numerically, we approximate the displacement field $u_i$ and test function $v_i$ using **finite element basis functions**:

 $$
u_i(x,t) \approx \sum_{j} N_j(x) u_i^j(t), \quad v_i(x) \approx \sum_{j} N_j(x) v_i^j
 $$

where:
- $N_j(x)$ are the **finite element shape functions**.
- $u_i^j(t)$ and $v_i^j$ are **nodal displacements** and **test function values**.

### 3.1. Discretized Matrix Form

Substituting into the weak form equation and simplifying, we obtain the **semi-discrete system**:

 $$
M \ddot{U} + K U = F
 $$

where:

- **Mass matrix**:

   $$
  M_{ij} = \int_{\Omega} \rho N_i N_j \, d\Omega
  $$

- **Stiffness matrix**:

 $$
  K_{ij} = \int_{\Omega} C_{ijkl} \frac{\partial N_i}{\partial x_j} \frac{\partial N_k}{\partial x_l} \, d\Omega
 $$

- **Force vector**:

 $$
  F_i = \int_{\Omega} f_i N_i \, d\Omega + \int_{\Gamma_t} t_i N_i \, d\Gamma
 $$

---

## 4. Summary of Weak Form Derivation

1. **Start with the strong form** of the elastodynamic equation:

    $$
   \rho \frac{\partial^2 u_i}{\partial t^2} = \nabla \cdot \sigma_{ij} + f_i
    $$

2. **Multiply by a test function** $v_i$ and integrate over the domain:

    $$
   \int_{\Omega} \rho \frac{\partial^2 u_i}{\partial t^2} v_i \, d\Omega = \int_{\Omega} (\nabla \cdot \sigma_{ij} + f_i) v_i \, d\Omega
   $$

3. **Apply integration by parts** (divergence theorem) to reduce differentiation order:

   $$
   \int_{\Omega} \rho \frac{\partial^2 u_i}{\partial t^2} v_i \, d\Omega + \int_{\Omega} \sigma_{ij} \frac{\partial v_i}{\partial x_j} \, d\Omega = \int_{\Omega} f_i v_i \, d\Omega + \int_{\Gamma_t} t_i v_i \, d\Gamma
   $$

4. **Use finite element approximation** to discretize the equation:

  $$
   u_i(x,t) \approx \sum_{j} N_j(x) u_i^j(t), \quad v_i(x) \approx \sum_{j} N_j(x) v_i^j
  $$

5. **Obtain the matrix form** for numerical implementation:

    $$
   M \ddot{U} + K U = F
    $$

This **weak form is the basis** for numerical solutions of ultrasonic wave propagation using **explicit FEM (Finite Element Method) in ABAQUS**.

