# Airfoil Aerodynamic Performance Prediction & Shape Optimization (CFD Surrogate Modeling)

## Overview
This repository contains a high-fidelity machine learning pipeline and CFD surrogate modeling framework designed to predict aerodynamic lift ($C_L$) and drag ($C_D$) coefficients for NACA airfoil profiles. By replacing computationally expensive numerical solvers (e.g., RANS CFD using ANSYS Fluent/OpenFOAM) with deep learning regressors (FFBPNN), this tool reduces aerodynamic evaluation time from hours to milliseconds while maintaining physical fidelity across pre-stall and stall envelopes.

---

## Nomenclature & Abbreviations
* **FFBPNN**: Feed-Forward Back-Propagation Neural Network
* **$C_L$**: Coefficient of Lift
* **$C_D$**: Coefficient of Drag
* **$C_p$**: Pressure Coefficient
* **$L/D$**: Lift-to-Drag Aerodynamic Efficiency Ratio
* **AoA ($\alpha$)**: Angle of Attack
* **Re**: Reynolds Number
* **Ma**: Mach Number
* **$c$**: Chord Length
* **$t/c$**: Maximum Thickness Ratio
* **NACA**: National Advisory Committee for Aeronautics
* **RANS**: Reynolds-Averaged Navier–Stokes
* **CFD**: Computational Fluid Dynamics
* **SST**: Shear Stress Transport
* **MLR**: Multiple Linear Regression
* **SVM**: Support Vector Machine
* **RMSE**: Root Mean Squared Error
* **MAE**: Mean Absolute Error
* **$R$**: Pearson Correlation Coefficient
* **$R^2$**: Coefficient of Determination

---

## Technical Methodology & Pipeline
1. **Synthetic Aerodynamic Dataset Generation:**
   - Evaluated over 3,000 distinct flight conditions spanning pre-stall to flow-separation regimes ($\alpha \in [-4^\circ, 18^\circ]$, $\text{Re} \in [5 \times 10^5, 5 \times 10^6]$, $\text{Ma} \in [0.1, 0.6]$).
2. **Surrogate Model Benchmarking:**
   - Multi-model evaluation comparing Multiple Linear Regression (MLR), Support Vector Machines (SVM), and Multi-Layer Feed-Forward Neural Networks (FFBPNN).
3. **Interactive Vector Field & Streamline Simulator:**
   - Dynamic 2D potential flow superposition simulating bound circulation (vortex panel theory) around NACA 00xx geometries.
4. **Inverse Design & Shape Optimization:**
   - SciPy constrained optimization (Sequential Least Squares Programming - SLSQP) to determine optimal profile parameters maximizing cruise glide ratio ($L/D$).
5. **Artifact Deployment:**
   - Fully serialized model pipelines and scalers exported for real-time web deployment.

---

## Tech Stack
* **Language:** Python 3
* **Scientific Computing & Aerodynamics:** NumPy, SciPy
* **Machine Learning & Neural Networks:** Scikit-Learn (MLPRegressor, SVR, LinearRegression)
* **Visualization & Dashboards:** Plotly, Matplotlib, IPyWidgets
* **Model Serialization:** Joblib
