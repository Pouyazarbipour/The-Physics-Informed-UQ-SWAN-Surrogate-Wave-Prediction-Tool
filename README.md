# The Physics Informed UQ SWAN Surrogate Wave Prediction Tool

## Overview

The **Physics-Informed SWAN Surrogate Prediction Tool** is an advanced scientific software for fast, accurate, and uncertainty-aware prediction of nearshore wave parameters.  
This tool serves as a machine-learning-based surrogate for the SWAN (Simulating WAves Nearshore) numerical model, combining deep learning, embedded wave physics, and uncertainty quantification.

The software provides spatial predictions of key wave parameters over a two-dimensional grid with a computational cost that is orders of magnitude lower than conventional SWAN simulations.

![Main Page GUI](https://github.com/Pouyazarbipour/The-Physics-Informed-UQ-SWAN-Surrogate-Wave-Prediction-Tool/blob/main/image_2025-12-19_18-22-51.png)


## Key Capabilities

- **High-Fidelity Wave Prediction**
  - Significant wave height (Hs)
  - Peak wave period (Tp)
  - Wave direction (Dir)

- **Physics-Informed Learning**
  - Linear wave dispersion consistency
  - Wave refraction constraints
  - Shoaling behavior enforcement

- **Uncertainty Quantification**
  - Aleatoric uncertainty (data-related variability)
  - Epistemic uncertainty (model uncertainty via Monte Carlo Dropout)
  - Combined total uncertainty for risk-informed analysis

- **Computational Efficiency**
  - Suitable for real-time, ensemble, and probabilistic studies

- **Standalone Software**
  - No need to run SWAN for inference once trained

## Scientific Background

The surrogate model is trained on SWAN-generated datasets and embeds governing nearshore wave physics directly into the learning process.  
This physics-informed approach improves generalization, physical realism, and robustness compared to classical data-driven surrogates.

The underlying research is based on:

> Etri, T., Jamali Rovesht, A., Nikoo, M. R., & Zarbipour, P. (2026).  
> *Hybrid PINN-UQ Surrogate for Spatial Reconstruction of SWAN Wave Parameters*.  
> Ocean Engineering (Under Review / In Preparation)

## Software Architecture

The model follows a hybrid deep learning structure:

- **MLP** for offshore and scalar forcing parameters
- **CNN Encoder** for bathymetry and spatial masks
- **CNN Decoder** for spatial reconstruction of wave fields
- Direction is modeled using **sine and cosine components** to avoid circular discontinuities


## Usage

### Running the Pretrained Model (Salalah Region)

For the predefined Salalah coastal domain, the surrogate model is already trained.

**Required Inputs**
- Offshore significant wave height
- Peak wave period
- Wave direction
- Sea level
- Wind speed
- Wind direction

The model outputs spatial predictions of Hs, Tp, and Dir along with uncertainty estimates.

### Limitations

* Valid only within the training data range
* Increased uncertainty for extreme or unseen conditions
* Fixed spatial resolution (36 × 36 grid)

Users are strongly encouraged to analyze uncertainty estimates alongside mean predictions.

## Disclaimer

This software is intended for professional and academic use.
Results should support—not replace—engineering judgment, design codes, and detailed numerical modeling where required.
The developers assume no liability for misuse or misinterpretation of the outputs.

## Authors

* Talal Etri
* Ali Jamali Rovesht
* Mohammad Reza Nikoo
* Pouya Zarbipour

Department of Civil and Architectural Engineering
Sultan Qaboos University, Muscat, Oman

## License

License information to be added.

