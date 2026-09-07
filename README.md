# Airfoil Aerodynamic Performance Prediction & Shape Optimization (CFD Surrogate Modeling)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/harpreetsingh171190-cmyk/Airfoil-Aerodynamic-Surrogate-Modeling/blob/main/Airfoil_Aerodynamic_Surrogate_Modeling.ipynb)
[![nbviewer](https://raw.githubusercontent.com/jupyter/design/master/logos/Badges/nbviewer_badge.svg)](https://nbviewer.org/github/harpreetsingh171190-cmyk/Airfoil-Aerodynamic-Surrogate-Modeling/blob/main/Airfoil_Aerodynamic_Surrogate_Modeling.ipynb)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)

---

## 📌 Project Overview
This repository delivers an end-to-end Machine Learning surrogate modeling pipeline designed to accelerate Computational Fluid Dynamics (CFD) aerodynamic workflows. High-fidelity Reynolds-Averaged Navier–Stokes (RANS) numerical simulations demand extensive compute time for viscous boundary-layer convergence. This project trains deep feed-forward back-propagation neural networks (FFBPNN) to predict the Lift Coefficient ($C_L$) and Drag Coefficient ($C_D$) across pre-stall and stall envelopes within milliseconds, coupled with 2D potential-flow streamline modeling and constrained inverse aerodynamic design.

> 🌐 **Interactive Inspection:** Dynamic 3D Pressure surfaces ($C_p$) and rotatable WebGL plots are fully rendered in the cloud via the **nbviewer** badge above.

---

## 📑 Nomenclature & Abbreviations
* **FFBPNN:** Feed-Forward Back-Propagation Neural Network
* **$C_L$:** Coefficient of Lift
* **$C_D$:** Coefficient of Drag
* **$C_p$:** Pressure Coefficient
* **$L/D$:** Aerodynamic Efficiency / Glide Ratio
* **AoA ($\alpha$):** Angle of Attack
* **Re:** Reynolds Number
* **Ma:** Mach Number
* **$c$:** Chord Length
* **$t/c$:** Airfoil Thickness Ratio
* **NACA:** National Advisory Committee for Aeronautics
* **RANS:** Reynolds-Averaged Navier–Stokes
* **CFD:** Computational Fluid Dynamics
* **SST:** Shear Stress Transport
* **MLR:** Multiple Linear Regression
* **SVM:** Support Vector Machine
* **RMSE:** Root Mean Squared Error
* **MAE:** Mean Absolute Error
* **$R$:** Pearson Correlation Coefficient
* **$R^2$:** Coefficient of Determination

---

## ⚙️ Key Engineering Modules

* **Physics-Based Aerodynamic Data Synthesis:** Generated over 3,000 synthetic flight points capturing non-linear stall roll-off and wave/parasitic drag across $\alpha \in [-4^\circ, 18^\circ]$, $\text{Re} \in [5 \times 10^5, 5 \times 10^6]$, and $\text{Ma} \in [0.1, 0.6]$.
* **Surrogate Model Benchmarking:** Direct comparative performance validation between Multiple Linear Regression (MLR), Support Vector Machines (SVM), and Multi-Layer Feed-Forward Neural Networks (FFBPNN).
* **Potential Flow Field & Streamline Simulator:** Analytical vector field superposition combining uniform freestream flow and bound circulation (vortex panel method) over NACA 4-digit profiles.
* **AI Inverse Design Optimization:** Constrained Sequential Least Squares Programming (SLSQP via SciPy) to isolate optimum angle of attack and profile thickness that maximize cruise glide ratio ($L/D$).
* **Model Serialization:** Automated pipeline to export `.pkl` weights and standard scalers for production inference.

---

## 🛠️ Tech Stack
* **Language:** Python 3
* **Scientific Computing & Aerodynamics:** NumPy, SciPy
* **Machine Learning & Regressors:** Scikit-Learn (MLPRegressor, SVR, LinearRegression)
* **Visualization:** Matplotlib, Plotly
* **Deployment & Storage:** Joblib

---

## 🚀 Cloud Execution

1. **Launch in Google Colab:** Click the **Open In Colab** badge at the top to access the cloud runtime.
2. **Execute Full Pipeline:** Navigate to **Runtime** > **Run all** to generate the aerodynamic flow fields and train surrogate networks.
3. **Inspect Interactive Outputs:** Open via **nbviewer** to view pre-rendered figures, 3D pressure distribution grids, and telemetry logs directly in your browser.
