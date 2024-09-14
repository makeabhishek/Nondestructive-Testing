## Acoustic and Elastic Waves:
### Acoustic Waves:
- Acoustic waves are mechanical vibrations that propagate through a medium (such as air, water, or solids) as pressure variations. These waves travel via compression and rarefaction (longitudinal waves), where particles of the medium move in the direction of wave propagation.
- Acoustic waves typically refer to waves that propagate in fluids (like air or water), though they can also travel in solids as longitudinal waves.
- The wave motion in acoustic waves can be described by the acoustic wave equation, which is derived from Newton’s second law and the continuity equation.

#### Key characteristics:
- __Wave type:__ Longitudinal (particles oscillate in the direction of wave propagation).
- __Propagation medium:__ Fluids or gases, but can also be in solids.
- __Velocity:__ Acoustic velocity depends on the medium's properties (e.g., density and bulk modulus).

### Elastic Waves:
- Elastic waves are a type of mechanical wave that propagate in solid materials through the interaction of stress and strain. These waves can exist in both longitudinal and transverse (shear) forms.
- In solids, there are two primary types of elastic waves:
  - __Longitudinal waves (P-waves):__ Similar to acoustic waves, where particle motion is in the same direction as wave propagation.
  - __Transverse waves (S-waves):__ Also known as shear waves, where particle motion is perpendicular to the direction of wave propagation.
- Elastic waves are governed by the elastic wave equation, which incorporates stress-strain relationships in solid media.

#### Key characteristics:
- __Wave type:__ Both longitudinal and shear.
- __Propagation medium:__ Solids (can travel through any material that supports stress and strain).
- __Velocity:__ Depends on the elastic properties of the material (Young’s modulus, Poisson’s ratio, etc.).

## Relevance to Ultrasonic Non-Destructive Testing (NDT):
Ultrasonic Non-Destructive Testing (NDT) uses both acoustic and elastic waves to detect flaws, measure material properties, and assess structural integrity without damaging the object being tested. Here's why these waves are relevant:

### 1. Penetration in Materials:
- __Acoustic and elastic waves__ can penetrate materials like metals, ceramics, and composites. This allows ultrasonic NDT to inspect components for internal defects, such as cracks, voids, or inclusions.

### 2. Different Modes of Propagation:
- __Elastic waves__ in solids, especially the use of longitudinal (P-waves) and shear (S-waves), enable the detection of different types of flaws. P-waves are useful for detecting cracks parallel to the wave propagation, while S-waves can detect cracks perpendicular to the wave. (Description below?)
- __Guided waves__ (a type of elastic wave) are useful for inspecting long-range structures such as pipes or plates.

### 3. High Sensitivity:

Ultrasonic waves (both acoustic and elastic) are highly sensitive to changes in material properties, geometry, and the presence of defects. They can detect very small discontinuities in a material's structure, making them ideal for early-stage damage detection.

### 4. Versatility:
- Acoustic waves can be used for the __characterization of fluid materials__, while __elastic waves__ are used to inspect solid structures. This versatility makes ultrasonic NDT applicable across a wide range of industries, including aerospace, oil and gas, automotive, and manufacturing.

### 5. Frequency and Wavelength Control:
- By varying the frequency of the ultrasonic waves, the resolution and depth of inspection can be controlled. Higher frequencies (shorter wavelengths) allow for finer detection of small flaws near the surface, while lower frequencies (longer wavelengths) are used for inspecting deeper within the material.

### 6. Reflection and Transmission:
- When acoustic or elastic waves encounter a boundary between different materials (e.g., a crack or interface), they reflect or refract, allowing defects to be detected based on changes in the received wave signal.
- __Reflection__ of elastic waves from cracks, inclusions, or other flaws is one of the primary mechanisms for flaw detection in ultrasonic testing.

### 7. Material Characterization:
Ultrasonic waves are used to measure material properties like thickness, elastic moduli, and density. These properties are important for evaluating the mechanical integrity and performance of materials in service conditions.

### Conclusion:
Acoustic and elastic waves form the basis of ultrasonic NDT, where their ability to propagate through materials, reflect from boundaries, and interact with flaws allows for comprehensive, non-invasive evaluation of the integrity of industrial components. This ensures safety, performance, and reliability in critical applications without causing any damage to the materials under inspection.

## Question: Why P-waves are useful for detecting cracks parallel to the wave propagation, while S-waves can detect cracks perpendicular to the wave. ?
The ability of P-waves (longitudinal waves) and S-waves (shear waves) to detect cracks depends on their distinct particle motion and interaction with material discontinuities like cracks. 

### 1. P-Waves (Longitudinal Waves) and Cracks Parallel to Wave Propagation
Particle motion: In P-waves, the particles in the material oscillate in the same direction as the wave propagates. This means the wave energy moves in a compressive and rarefactive manner along the direction of wave travel.

- __Crack detection:__
  - When a P-wave encounters a crack that is parallel to the wave propagation direction, the displacement and stress caused by the P-wave can more easily interact with the crack faces. As the wave tries to compress and expand the material, the crack impedes this process, leading to a noticeable reflection or scattering of the wave.
  - Since the crack faces are aligned with the direction of the particle motion, the P-wave can reflect strongly off the crack and produce a clear signal, making it useful for detecting cracks aligned with its propagation direction.

- __Effect on wave:__
  - The compressional stress caused by the P-wave interacts directly with the crack, which creates a difference in wave impedance at the crack surface. This impedance contrast produces significant reflections that indicate the presence of the crack.

### 2. S-Waves (Shear Waves) and Cracks Perpendicular to Wave Propagation
Particle motion: In S-waves, the particles in the material oscillate perpendicular to the direction of wave propagation. This means that while the wave propagates in one direction, the particle motion is side-to-side (in shear).
- __Crack detection:__
  - When an S-wave encounters a crack that is perpendicular to the wave propagation direction, the particle motion (shearing back and forth) interacts strongly with the crack. Since the S-wave causes shear stress in the material, and a crack is a region of weakness where shear stress cannot be transmitted effectively, this creates a noticeable reflection.
  - Cracks that are perpendicular to the wave propagation direction will experience the full effect of the shear motion, making S-waves sensitive to detecting these cracks.

- __Effect on wave:__
  - The shear stress created by S-waves interacts directly with the perpendicular crack faces. Because the crack impedes the transmission of shear motion, there is a strong reflection or scattering of the S-wave at the crack interface.
  - This results in a significant loss or alteration of the wave energy, making it easier to identify cracks that are perpendicular to the wave propagation direction.

### Summary of the Differences:
Wave Type	| Particle Motion Direction	| Crack Orientation Detected |
| -------- | ------- | ------- | 
__P-waves__| Parallel to wave direction	| Cracks __parallel__ to wave propagation, because the compressive stress interacts directly with the crack faces. |
__S-waves__ |	Perpendicular to wave direction	| Cracks __perpendicular__ to wave propagation, because the shear stress interacts strongly with the crack surfaces, causing strong reflection or scattering. |

## Pressure Formula for a Single Element Ultrasonic Transducer
For a single-element ultrasonic transducer, the acoustic pressure $p(r,\theta,t)$ at a point in the field can be expressed using the _Rayleigh-Sommerfeld integral_, assuming the transducer is circular and radiating into a fluid medium. 

The formula is given by: \
$p(r,\theta,t) = \frac{\rho_0 c_0 v_0 a^2}{r} cos(\theta) \frac{sin(k a sin(\theta))}{ks sin(\theta)} cos(\omega t - kr)$

Where: 
- $r$ is the distance from the center of the transducer to the observation point.
- $\theta$ is the angle between the transducer's axis and the observation point.
- $\rho_0$ is the density of the medium.
- $c_0$ is the speed of sound in the medium.
- $v_0$ is the surface velocity amplitude of the transducer.
- $a$ is the radius of the transducer.
- $k=\frac{2\pi}{\lambda}$ is the wave number, where 
- ${\lambda}$ is the wavelength.
- ${\omega}$  is the angular frequency of the excitation.
- ${t}$ is the time.

## Pressure Formula for a Phased Array Transducer
For a phased array transducer, the total pressure at a point is the superposition of the pressures from each individual element. If there are 16 elements, the pressure at a point 
$p(r,\theta,t)$ can be expressed as:

$p(r,\theta,t) = \sum_{n=1}^{noEl} \frac{\rho_0 c_0 v_0 a^2}{r_n} cos(\theta) \frac{sin(k a sin(\theta_n))}{ks sin(\theta_n)} cos(\omega t - kr_n + \phi_n)$

Where: 
- $r_n$ is the distance from the n-th element to the observation point.
- $\theta_n$ is the angle between the axis of the n-th element and the observation point. 
- $\phi_n$ is the phase delay applied to the n-th element to achieve focusing or steering of the beam.

This expression accounts for the contribution of each element in the phased array, considering the geometric delays and phase shifts applied to each element to control the direction and focus of the beam.

If the array is designed to focus at a particular point $(r_n, \theta_f)$, the phase delay $$\phi_n $ for each element can be adjusted to focus the beam at that point, typically using the following relation:

$\phi_n = k \cdot (r_n - r_f)$

The overall pressure field will depend on the configuration of the elements, the focusing or steering applied, and the distance and angle to the observation point.

## What are Guided Waves?
Guided waves are types of elastic waves that are confined to propagate along specific geometrical boundaries or structures, such as plates, pipes, or rods. These waves are __“guided”__ by the geometry of the medium, meaning that they are not free to propagate in all directions, as in the case of bulk waves. Instead, the material boundaries (such as surfaces or interfaces) cause the wave energy to remain within or near the structure, allowing for efficient propagation over long distances.

Common types of guided waves include:

- Lamb waves (in thin plates),
- Rayleigh waves (on surfaces),
- Shear Horizontal (SH) waves (in plates),
- Torsional waves (in cylindrical structures like pipes).

## Difference Between Bulk Wave and Guided Wave
| Aspect | Bulk Waves	| Guided Waves |
| -------- | ------- | ------- | 
Propagation	| Propagate through the entire medium without restriction. | Confined to specific geometries (surfaces, plates, pipes). |
Types	| Longitudinal (P-waves) and Shear (S-waves).| Lamb waves, Rayleigh waves, SH waves, etc. |
Energy Distribution	| Disperse throughout the volume of the material.| Energy is confined along boundaries or interfaces. |
Applications	| Used for flaw detection in bulk materials.| Used for inspecting long structures like plates, pipelines, and cables. |
Attenuation	| Typically higher due to energy dissipation in all directions.	| Lower attenuation, allowing longer propagation along the structure. |

## What is Dispersion in Ultrasonic Guided Waves?
Dispersion in ultrasonic guided waves refers to the phenomenon where different frequency components of the wave travel at different phase velocities. This occurs because the velocity of guided waves depends on both the frequency of the wave and the geometric properties of the structure (such as thickness or diameter). As a result, different modes (Lamb wave modes, for example) exhibit different phase velocities at different frequencies, causing the wave packet to spread out over time.

Dispersion makes guided wave analysis more complex because the velocity of the wave is not constant and varies with frequency, which can affect the accuracy of signal interpretation in applications like non-destructive testing.

## Dispersion Formula for Guided Waves
For a specific case of Lamb waves (guided waves in a plate), the dispersion relations are derived from the boundary conditions of stress and displacement continuity at the free surfaces. The Lamb wave modes (symmetric $S_n$ and antisymmetric $A_n$) are governed by the following transcendental equations:

###  Symmetric Modes (S) Dispersion Relation:
$tan(qh) = \frac{4k^2 p q}{(k^2 - q^2)^2}$

###  Antisymmetric Modes (A) Dispersion Relation:
$tan(qh) = - \frac{(k^2 - q^2)^2}{4k^2 p q}$

Where:

- $k$ is the wavenumber $(k=\frac{\omega}{v})$
- $q = \sqrt{\frac{\omega^2}{v_L^2}-k^2}$ (related to longitudinal wave speed $v_L$
- $p = \sqrt{k^2 - \frac{\omega^2}{v_S^2}}$(related to shear wave speed $v_S$ 
- h is the half-thickness of the plate,
- $\omega$ is the angular frequency,
- $v$ is the phase velocity,  and 
- $v_L$ and $v_S$ are the bulk longitudinal and shear velocities in the material, respectively.

These equations relate the frequency, thickness, and material properties to the phase velocity of the Lamb waves. Solving these transcendental equations for each mode yields the phase velocity as a function of frequency, known as the dispersion curve.

