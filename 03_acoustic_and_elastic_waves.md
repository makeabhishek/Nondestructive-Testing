## Acoustic wave equation
We derive the acoustic wave equation from the stress-strain relationship in tensorial form, we'll start by considering the __fundamental equations of motion__, the __stress-strain relationship__, and the __constitutive relations__ for a linear elastic medium. Here's a step-by-step derivation:

### 1. __Stress-Strain Relationship and Hooke's Law__
For a linear elastic material, the stress tensor $\sigma_{ij}$ is related to the strain tensor $\epsilon_{ij}$ through __Hooke's law__:

$\sigma_{ij} = 𝐶_{ijkl} \ \epsilon_{kl}$ 

Where:
- $\sigma_{ij}$ is the stress tensor.
- $\epsilon_{ij}$ is the strain tensor.
- $𝐶_{ijkl}$ is the fourth-order stiffness tensor that relates stress and strain.

For an isotropic material, Hooke's law simplifies to:

$\sigma_{ij} = \lambda \delta_{ij} \ \epsilon_{kk} + 2\mu \ \epsilon_{ij}$

Where:
- $\lambda$ and $\mu$ are the Lamé constants.
- $\delta_{ij}$ is the Kronecker delta.
- $\epsilon_{kk}$ is the trace of the strain tensor (sum of the diagonal components), which is the volumetric strain.

### 2. Strain-Displacement Relationship
The strain tensor $\epsilon_{ij}$ is related to the displacement vector $u_{i}$ by the strain-displacement relationship:

$\epsilon_{ij} = \frac{1}{2}\bigg(\frac{\partial u_i}{\partial x_j} + \frac{\partial u_j}{\partial x_i}\bigg)$ 

where, 
- $u_{i}$ is the displacement component in the $i$-th direction.
- $x_{j}$ ​is the position coordinate in the $j$-th direction.

### 3. Equation of Motion
Newton's second law $(F=ma)$ for a continuous medium gives us the equation of motion, which relates the stress tensor to the acceleration of the displacement:

$\rho \frac{\partial^2 u_i}{\partial t^2} = \frac{\partial \sigma_{ij}}{\partial x_j}$

where,
- $\rho$ is the density of the medium.
- $\frac{\partial^2 u_i}{\partial t^2}$ is the acceleration  in the i-th direction.

### 4. Substitute Stress-Strain Relationship into the Equation of Motion
Substituting the stress-strain relationship $\sigma_{ij} = 𝐶_{ijkl} \epsilon_{kl}$ into the equation of motion gives:

$\rho \frac{\partial^2 u_i}{\partial t^2} = \frac{\partial}{\partial x_j} (C_{ijkl} \epsilon_{kl})$

### 5. Substitute Strain-Displacement Relationship
Substituting the strain-displacement relationship $\epsilon_{ij} = \frac{1}{2}\bigg(\frac{\partial u_i}{\partial x_j} + \frac{\partial u_j}{\partial x_i}\bigg)$ into the equation:

$\rho \frac{\partial^2 u_i}{\partial t^2} = \frac{\partial}{\partial x_j} \bigg(C_{ijkl} \quad \frac{1}{2}\bigg(\frac{\partial u_i}{\partial x_j} + \frac{\partial u_j}{\partial x_i}\bigg)\bigg)$

### 6. Simplify the Equation
Assuming isotropic materials where the stiffness tensor simplifies (Lamé's constants $\lambda$ and $\mu$), we get:

$\sigma_{ij} =  \lambda \delta_{ij} \sum_{k} \frac{\partial u_k}{\partial x_k} + 2 \mu \epsilon_{ij}$

Substituting this into the equation of motion:

$\rho \frac{\partial^2 u_i}{\partial t^2} = \frac{\partial}{\partial x_j} \bigg(\lambda \delta_{ij} \sum_{k} \frac{\partial u_k}{\partial x_k} + 2 \mu \epsilon_{ij} \bigg)$

This simplifies to:

$\rho \frac{\partial^2 u_i}{\partial t^2} = (\lambda + 2\mu) \frac{\partial}{\partial x_i} \sum_{k} \frac{\partial u_k}{\partial x_k} + \mu \nabla^2 u_{i}$

### 7. Wave Equation for Displacement
If we take the divergence of the displacement field $\nabla \cdot u$ and substitute it into the above equation, the __acoustic wave equation__ in an isotropic medium is:

$\rho \frac{\partial^2 u_i}{\partial t^2} = (\lambda + 2\mu) \nabla (\nabla \cdot \textbf{u}) + \mu \nabla^2 \textbf{u}$

In the special case where the medium is homogeneous and isotropic (same properties in all directions), and assuming small perturbations, this reduces to:

$\boxed{\nabla^2 u - \frac{1}{c^2} \frac{\partial^2 u}{\partial t^2} = 0}$

where $c$ is the speed of sound in the medium, given by $c = \sqrt{\frac{(\lambda + 2\mu)}{\rho}}$

This is the acoustic wave equation for the displacement field $u$ in a homogeneous, isotropic, and linear elastic medium.

## Elastic wave equation
To derive the elastic wave equation for an elastic medium, we'll follow a similar process to the _acoustic wave equation_ derivation but consider the vector nature of displacements in an elastic solid. The elastic wave equation describes how mechanical waves propagate through a solid medium and accounts for both longitudinal (compressional) and shear (transverse) waves.

Steps 1 to 3 are the same, also we follow the same procedure. Let's start from step no. 4

### 4. Substitute Stress-Strain Relationship into the Equation of Motion
Substituting the stress-strain relationship $\sigma_{ij} = \lambda \delta_{ij} \ \epsilon_{kk} + 2\mu \ \epsilon_{ij}$ into the equation of motion gives:

$\rho \frac{\partial^2 u_i}{\partial t^2} = \frac{\partial}{\partial x_j} (\lambda \delta_{ij} \ \epsilon_{kk} + 2\mu \ \epsilon_{ij})$

### 5. Substitute Strain-Displacement Relationship
Substituting the strain-displacement relationship $\epsilon_{ij} = \frac{1}{2}\bigg(\frac{\partial u_i}{\partial x_j} + \frac{\partial u_j}{\partial x_i}\bigg)$ into the equation:

$\rho \frac{\partial^2 u_i}{\partial t^2} = \frac{\partial}{\partial x_j} \bigg(\lambda \delta_{ij}\frac{\partial u_k}{\partial x_j} + \mu \quad \bigg(\frac{\partial u_i}{\partial x_j} + \frac{\partial u_j}{\partial x_i}\bigg)\bigg)$

Expanding this equation:

$\rho \frac{\partial^2 u_i}{\partial t^2} = \lambda \frac{\partial}{\partial x_i} \bigg(\frac{\partial u_k}{\partial x_k} \bigg) + \mu \frac{\partial^2 u_i}{\partial x^2_j} + \mu \frac{\partial^2 u_{j}}{\partial x_{i} \partial x_{j}} $

### 6. Simplify the Equation
Rearranging and simplifying, the equation becomes:

$\rho \frac{\partial^2 u_i}{\partial t^2} = (\lambda + \mu) \frac{\partial^2 u_{k}}{\partial x_{i} \partial x_{k}} + \mu \nabla^2 u_i $

where, $\nabla^2 u_i$ is the Laplacian of the displacement field $u_i$, given by $\nabla^2 u_i = \frac{\partial^2 u_i}{\partail x_j \partial x_j}$

### 7. Vector Form of the Elastic Wave Equation
The above equation can be written more compactly in vector form ($u$ is a vector in bold):

$\rho \frac{\partial^2 u}{\partial t^2} = (\lambda + \mu) \nabla(\nabla \cdot u) + \mu \nabla^2 u$

This is the __elastic wave equation__ in an isotropic medium.

### 8. Interpreting the Elastic Wave Equation
- The term $(\lambda + \mu) \nabla(\nabla \cdot u)$ corresponds to the propagation of compressional (longitudinal) waves, also known as P-waves.
- The term $\mu \nabla^2 u$ corresponds to the propagation of shear (transverse) waves, also known as S-waves.

The elastic wave equation describes how these two types of waves propagate through a solid medium. The P-wave speed $(c_p)$ and S-wave speed $(c_s)$ are given by:

$c_p = \sqrt{\frac{\lambda + 2\mu}{\rho}}$ and $c_s = \sqrt{\frac{\mu}{\rho}}$

These wave speeds determine how fast the respective wave types travel through the medium.

Hence, the __Elastic Wave Equation in Time Domain__ in vector form for a linear, isotropic, and homogeneous medium is:

$\rho \frac{\partial^2 u}{\partial t^2} = (\lambda + \mu) \nabla(\nabla \cdot u) + \mu \nabla^2 u$

where,
- $u(x,t)$ is the displacement vector field.
- $\rho$ is the density of the medium.
- $\lambda$  and $\mu$ are the Lamé constants.
- $t$ is time.
- $\nabla$ is the gradient operator.
- $\nabla^2$ is the Laplacian operator.

## Frequency Domain of elastic wave equation
To convert the elastic wave equation from the time domain to the frequency domain, we need to perform a Fourier transform on the equation. The Fourier transform allows us to analyze the wave equation in terms of frequency components, which can be particularly useful for solving problems where time-harmonic solutions are desired.

### 1. Time Domain Elastic Wave Equation

$\rho \frac{\partial^2 u}{\partial t^2} = (\lambda + \mu) \nabla(\nabla \cdot u) + \mu \nabla^2 u$

### 2. Fourier Transform of the Displacement Field
To convert the equation to the frequency domain, we apply the Fourier transform to the displacement vector $u(x,t)$

$u(x,t) = \int_{- \infty}^{\infty} U(X,\omega) e^{-i\omega t} d\omega$

Where, 
- $U(X,\omega)$ is the Fourier transform of the displacement vector, depending on spatial coordinates $x$ and angular frequency $\omega$.
- $i$ is the imaginary unit.
- $\omega$ is the angular frequency.

The inverse Fourier transform is: 

$U(X,\omega)  = \frac{1}{2\pi} \int_{- \infty}^{\infty} u(x,t)e^{i\omega t} dt$

### 3. Applying Fourier Transform to the Elastic Wave Equation
We apply the Fourier transform to each term in the elastic wave equation.

#### a. Time Derivative Term
The second time derivative of the displacement field transforms as:

$\frac{\partial^2 u}{\partial t^2} \rightarraow - \omega^2 U(X,\omega)$

Thus, the left-hand side of the wave equation becomes:

$\rho \frac{\partial^2 u}{\partial t^2} \rightarraow -\rho \omega^2 U(X,\omega)$

#### b. Gradient and Divergence Terms
The spatial derivatives do not change when we perform the Fourier transform with respect to time, so:

$\nabla(\nabla \cdot u) \rightarrow \nabla(\nabla\cdot U(X,\omega))$

$\nabla^2 u \rightarrow \nabla^2 U(X,\omega)$

### 4. Elastic Wave Equation in Frequency Domain
Substituting the Fourier-transformed components into the original elastic wave equation, we obtain:

$-\rho \omega^2 U(X,\omega)$

### 5. Simplifying the Equation
We can further simplify the frequency-domain elastic wave equation by considering the vector wave components:
- The term
- The term 

