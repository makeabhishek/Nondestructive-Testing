# Strong Form of the Elastodynamic Equation (Expanded and Matrix Form)

## 1. Strong Form in Index Notation (Expanded Form)

The governing equation for ultrasonic wave propagation in a **linear elastic solid** is given by the **elastodynamic equation**:

$$
\rho \frac{\partial^2 u_i}{\partial t^2} = \frac{\partial \sigma_{ij}}{\partial x_j} + f_i
$$

where:
- \( u_i \) is the displacement field (\( i = x, y, z \)).
- \( \rho \) is the **material density**.
- \( \sigma_{ij} \) is the **Cauchy stress tensor**.
- \( f_i \) is the **body force per unit volume**.
- \( \nabla \cdot \sigma_{ij} \) represents the **internal force due to stress divergence**.

For an **isotropic elastic medium**, stress is related to strain through **Hooke’s Law**:

$$
\sigma_{ij} = \lambda \delta_{ij} \frac{\partial u_k}{\partial x_k} + 2\mu \varepsilon_{ij}
$$

where the **strain tensor** is:

$$
\varepsilon_{ij} = \frac{1}{2} \left( \frac{\partial u_i}{\partial x_j} + \frac{\partial u_j}{\partial x_i} \right)
$$

Substituting \( \sigma_{ij} \) into the strong form:

$$
\rho \frac{\partial^2 u_i}{\partial t^2} = \frac{\partial}{\partial x_j} \left[ \lambda \delta_{ij} \frac{\partial u_k}{\partial x_k} + 2\mu \frac{\partial u_i}{\partial x_j} \right] + f_i
$$

Expanding the derivatives:

$$
\rho \frac{\partial^2 u_i}{\partial t^2} = \lambda \frac{\partial}{\partial x_i} \left( \frac{\partial u_k}{\partial x_k} \right) + 2\mu \frac{\partial^2 u_i}{\partial x_j \partial x_j} + f_i
$$

which simplifies to:

$$
\rho \frac{\partial^2 u_i}{\partial t^2} = (\lambda + 2\mu) \frac{\partial^2 u_i}{\partial x_j \partial x_j} + \lambda \frac{\partial}{\partial x_i} \left( \frac{\partial u_k}{\partial x_k} \right) + f_i
$$

---

## 2. Strong Form in Matrix Form (3D Case)

### 2.1. Displacement Vector

The displacement field in **3D** is:

$$
\mathbf{u} =
\begin{bmatrix}
u_x \\ u_y \\ u_z
\end{bmatrix}
$$

where \( u_x, u_y, u_z \) are the displacement components in the \( x, y, z \) directions.

### 2.2. Stress Tensor

The **Cauchy stress tensor** in **3D** is:

$$
\boldsymbol{\sigma} =
\begin{bmatrix}
\sigma_{xx} & \sigma_{xy} & \sigma_{xz} \\
\sigma_{yx} & \sigma_{yy} & \sigma_{yz} \\
\sigma_{zx} & \sigma_{zy} & \sigma_{zz}
\end{bmatrix}
$$

Using Hooke’s law for an **isotropic material**:

$$
\boldsymbol{\sigma} = \lambda (\nabla \cdot \mathbf{u}) \mathbf{I} + 2\mu \boldsymbol{\varepsilon}
$$

where the **strain tensor** is:

$$
\boldsymbol{\varepsilon} =
\frac{1}{2}
\begin{bmatrix}
2\frac{\partial u_x}{\partial x} & \frac{\partial u_x}{\partial y} + \frac{\partial u_y}{\partial x} & \frac{\partial u_x}{\partial z} + \frac{\partial u_z}{\partial x} \\
\frac{\partial u_y}{\partial x} + \frac{\partial u_x}{\partial y} & 2\frac{\partial u_y}{\partial y} & \frac{\partial u_y}{\partial z} + \frac{\partial u_z}{\partial y} \\
\frac{\partial u_z}{\partial x} + \frac{\partial u_x}{\partial z} & \frac{\partial u_z}{\partial y} + \frac{\partial u_y}{\partial z} & 2\frac{\partial u_z}{\partial z}
\end{bmatrix}
$$

### 2.3. Expanded 3D Strong Form

Expanding the **elastodynamic equation** for **each component**:

$$
\rho \frac{\partial^2}{\partial t^2}
\begin{bmatrix}
u_x \\ u_y \\ u_z
\end{bmatrix}
=
\begin{bmatrix}
\frac{\partial \sigma_{xx}}{\partial x} + \frac{\partial \sigma_{xy}}{\partial y} + \frac{\partial \sigma_{xz}}{\partial z} \\
\frac{\partial \sigma_{yx}}{\partial x} + \frac{\partial \sigma_{yy}}{\partial y} + \frac{\partial \sigma_{yz}}{\partial z} \\
\frac{\partial \sigma_{zx}}{\partial x} + \frac{\partial \sigma_{zy}}{\partial y} + \frac{\partial \sigma_{zz}}{\partial z}
\end{bmatrix}
+
\begin{bmatrix}
f_x \\ f_y \\ f_z
\end{bmatrix}
$$

Substituting **Hooke’s Law**:

$$
\rho \frac{\partial^2}{\partial t^2}
\begin{bmatrix}
u_x \\ u_y \\ u_z
\end{bmatrix}
=
(\lambda + 2\mu)
\begin{bmatrix}
\frac{\partial^2 u_x}{\partial x^2} + \frac{\partial^2 u_x}{\partial y^2} + \frac{\partial^2 u_x}{\partial z^2} \\
\frac{\partial^2 u_y}{\partial x^2} + \frac{\partial^2 u_y}{\partial y^2} + \frac{\partial^2 u_y}{\partial z^2} \\
\frac{\partial^2 u_z}{\partial x^2} + \frac{\partial^2 u_z}{\partial y^2} + \frac{\partial^2 u_z}{\partial z^2}
\end{bmatrix}
+
\lambda
\begin{bmatrix}
\frac{\partial}{\partial x} (\nabla \cdot \mathbf{u}) \\
\frac{\partial}{\partial y} (\nabla \cdot \mathbf{u}) \\
\frac{\partial}{\partial z} (\nabla \cdot \mathbf{u})
\end{bmatrix}
+
\begin{bmatrix}
f_x \\ f_y \\ f_z
\end{bmatrix}
$$

### 2.4. Compact Matrix Form

Defining the **Laplacian** \( \nabla^2 \) and the **gradient of divergence**:

$$
\nabla^2 \mathbf{u} =
\begin{bmatrix}
\frac{\partial^2 u_x}{\partial x^2} + \frac{\partial^2 u_x}{\partial y^2} + \frac{\partial^2 u_x}{\partial z^2} \\
\frac{\partial^2 u_y}{\partial x^2} + \frac{\partial^2 u_y}{\partial y^2} + \frac{\partial^2 u_y}{\partial z^2} \\
\frac{\partial^2 u_z}{\partial x^2} + \frac{\partial^2 u_z}{\partial y^2} + \frac{\partial^2 u_z}{\partial z^2}
\end{bmatrix}
$$

The **final strong form in matrix notation** is:

$$
\rho \frac{\partial^2 \mathbf{u}}{\partial t^2} = (\lambda + 2\mu) \nabla^2 \mathbf{u} + \lambda \nabla (\nabla \cdot \mathbf{u}) + \mathbf{f}
$$
