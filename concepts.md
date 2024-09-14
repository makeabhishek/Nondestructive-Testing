## Pressure Formula for a Single Element Ultrasonic Transducer
For a single-element ultrasonic transducer, the acoustic pressure $p(r,\theta,t)$ at a point in the field can be expressed using the _Rayleigh-Sommerfeld integral_, assuming the transducer is circular and radiating into a fluid medium. 
The formula is given by:


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



