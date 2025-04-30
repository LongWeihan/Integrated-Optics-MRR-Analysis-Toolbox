# Integrated Optical Microring Resonator Simulation Tool

This repository contains a MATLAB program designed for simulating and analyzing the transmission characteristics of integrated optical microring resonators. The tool allows users to explore the fundamental principles of waveguide theory, directional couplers, and microring resonators, and to predict their spectral responses based on various design parameters.

## Features

* **Waveguide Mode Analysis:** Analyze the mode characteristics of optical waveguides using the Marcatili method, including the determination of effective refractive index and single-mode operation range based on waveguide geometry and material properties.
* **Directional Coupler Analysis:** Investigate the relationship between the mode coupling coefficient ($\kappa$) and the spacing ($D$) between waveguides, demonstrating the exponential decay of coupling strength with increasing gap.
* **Coupler Design for Specific Coupling:** Determine the required waveguide spacing for a given directional coupler length to achieve a specific power transfer ratio, such as achieving nearly complete power transfer (P4 $\approx$ 1).
* **Bent Directional Coupler Modeling:** Approximate the transmission matrix of bent or non-uniform directional couplers using a differential method and matrix cascade approach to account for varying coupling strength along the interaction length.
* **Microring Resonator Transmission Spectrum Calculation:** Calculate the transmission spectrum of an all-pass microring resonator by combining the characteristics of the directional coupler (coupling strength), the microring geometry (radius), waveguide effective refractive index, and round-trip loss in the ring.

## Theoretical Basis

The simulations are based on fundamental principles of integrated optics, including:

* **Optical Waveguide Mode Theory:** Analyzing how light propagates in the waveguide by determining guided modes, effective refractive index ($n_{eff}$), and mode field distribution. The Marcatili method is used for approximating mode solutions in rectangular waveguides.
* **Coupled Mode Theory (CMT):** Describing the interaction and energy transfer between adjacent waveguides in the directional coupler. This theory relates the coupling strength to the overlap of mode fields.
* **Transfer Matrix Method:** Modeling the cumulative effect of light propagation through cascaded sections, particularly useful for analyzing non-uniform structures like bent directional couplers by dividing them into small, approximately uniform segments.
* **Microring Resonator Theory:** Analyzing the resonant behavior of the ring structure due to constructive interference for specific wavelengths that satisfy the resonance condition ($n_{eff} \cdot L_{ring} = m \cdot \lambda$, where $m$ is an integer). The transmission function of the all-pass filter is derived based on coupling and round-trip propagation in the ring.

## Getting Started

To use this simulation tool, clone this repository to your local machine:

```bash
git clone [repository_url]
```

Navigate to the cloned directory. Ensure you have MATLAB installed.

## How to Use

The repository contains several MATLAB scripts, each focusing on a specific aspect of the integrated optical device analysis. You can run each script individually to perform the corresponding simulation.

1.  **Open the desired script in MATLAB:** Use the MATLAB editor to open files like `MarcatiliModeSolver.m`, `CouplingVsDistance.m`, etc.
2.  **Modify parameters:** At the beginning of each script, you will find defined physical and geometrical parameters (e.g., refractive indices `n1`, `n2`, waveguide half-width `a`, wavelength `lambda`, coupler length `L_coupler`, ring radius `R_ring`, etc.). Adjust these values according to the specific device you wish to simulate.
3.  **Run the script:** Execute the script using the "Run" button in the MATLAB editor or by typing the script name in the MATLAB Command Window.
4.  **Interpret results:** The scripts will typically output numerical results to the Command Window and generate plots visualizing the simulated characteristics (e.g., $n_{eff}$ vs. `a`, $\kappa$ vs. $D$, transmission spectrum). Analyze these outputs to understand the device behavior.

For the microring resonator transmission spectrum simulation (`MRR_TransmissionSpectrum.m`), ensure you have appropriate values for the coupling parameters (`D_coupler`, `L_coupler`) and ring loss (`alpha_ring`), potentially informed by the results from the coupler analysis scripts.

## Program Structure

The repository includes the following MATLAB scripts:

* `MarcatiliModeSolver.m`: Solves the Marcatili characteristic equations to find the mode parameters (like effective refractive index) for a given rectangular waveguide and determines the approximate single-mode operating range.
* `CouplingVsDistance.m`: Calculates and plots the mode coupling coefficient ($\kappa$) as a function of the center-to-center distance ($D$) between two parallel straight waveguides of a specified geometry.
* `CouplerSpacingSweep.m`: Analyzes the power transfer between the straight and cross ports of a fixed-length directional coupler by sweeping the waveguide center-to-center spacing, useful for finding the spacing needed for a desired coupling ratio (e.g., P4=1).
* `SegmentedCouplerAnalysis.m`: Implements the differential method and matrix cascade technique to model the transmission properties of a bent or non-uniform directional coupler by dividing it into multiple segments.
* `MRR_TransmissionSpectrum.m`: Calculates and plots the transmission spectrum of an all-pass microring resonator, taking into account the coupling parameters from the directional coupler, the ring geometry, waveguide effective index, and ring loss.

This tool serves as a valuable resource for researchers and engineers working on the design and analysis of integrated optical circuits, offering a hands-on approach to understanding the behavior of microring resonators and their components.
