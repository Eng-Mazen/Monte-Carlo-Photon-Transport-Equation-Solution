# Monte-Carlo-Photon-Transport-Equation-Solution
Simple MATLAB code to simulate photon transport using a Monte Carlo method to approximate the Radiative Transfer Equation:

```math
\frac{1}{c}\frac{\partial I(\mathbf{r}, \mathbf{\Omega}, E, t)}{\partial t} + \mathbf{\Omega} \cdot \nabla I(\mathbf{r}, \mathbf{\Omega}, E, t) + \mu_t I(\mathbf{r}, \mathbf{\Omega}, E, t) = \int \mu_s(E' \to E, \mathbf{\Omega'} \to \mathbf{\Omega}) I(\mathbf{r}, \mathbf{\Omega'}, E', t) \, d\mathbf{\Omega'} dE' + S(\mathbf{r}, \mathbf{\Omega}, E, t)
```
To solve the Radiative Transfer Equation using the Monte Carlo method, the following physical assumptions are made:
*   **Particle Nature of Light**: Photons are treated as discrete particles (photon packets) rather than waves; therefore, interference, diffraction, and polarization effects are typically neglected.
*   **Elastic Scattering**: Energy loss during a scattering event is assumed to be zero (i.e., the wavelength remains constant), unless specifically modeling inelastic processes like Raman scattering or Fluorescence.
*   **Independent Scattering**: Scattering centers (cells, molecules, particles) are distributed randomly and are far enough apart that they scatter light independently.
*   **Homogeneous Stepping**: Within a single defined medium, the interaction coefficients ($\mu_a$ and $\mu_s$) are assumed to be constant along the path of the photon step.
*   **Steady State**: Most implementations assume a continuous wave (CW) light source where the photon distribution has reached a statistical equilibrium, unless time-resolved tracking is explicitly enabled.
*   **Continuum Medium**: The medium is treated as a macroscopic continuum where the probability of interaction is governed by bulk coefficients rather than individual atomic coordinates.  
  After applying asumptions the equation becomes:
``` math
\mathbf{\Omega} \cdot \nabla I(\mathbf{r}, \mathbf{\Omega}) + \mu_t I(\mathbf{r}, \mathbf{\Omega}) = \mu_s \int_{4\pi} p(\mathbf{\Omega'} \cdot \mathbf{\Omega}) I(\mathbf{r}, \mathbf{\Omega'}) \, d\mathbf{\Omega'} + S(\mathbf{r}, \mathbf{\Omega})
```
