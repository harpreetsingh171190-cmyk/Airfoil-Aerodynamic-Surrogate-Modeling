# Airfoil Aerodynamic Performance Prediction & Shape Optimization (CFD Surrogate Modeling)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com)
[![nbviewer](https://raw.githubusercontent.com/jupyter/design/master/logos/Badges/nbviewer_badge.svg)](https://nbviewer.org/github/harpreet/Airfoil-Aerodynamic-Surrogate-Modeling/blob/main/Airfoil_Aerodynamic_Surrogate_Modeling.ipynb)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)

---

## 📌 Project Overview
This repository implements an end-to-end Machine Learning surrogate modeling framework designed to accelerate Computational Fluid Dynamics (CFD) aerodynamic workflows. Traditional Reynolds-Averaged Navier–Stokes (RANS) numerical simulations can take hours to converge for fine boundary-layer meshes. This project trains deep feed-forward neural regressors (FFBPNN) to predict the Lift Coefficient ($C_L$) and Drag Coefficient ($C_D$) across pre-stall and stall envelopes in milliseconds, combined with potential-flow velocity field modeling and AI-driven inverse aerodynamic design.

> 🌐 **Interactive 3D Notice:** To view the dynamically rotatable Plotly 3D Pressure surfaces and responsive web widgets without execution, open the notebook via the **nbviewer** badge above.

---

## 📸 Simulation & Visualizations

| Potential Flow Streamlines & Velocity Field | 3D Pressure Distribution ($C_p$) Surface |
| :---: | :---: |
| ![Aerodynamic Streamlines](streamlines.png) | ![3D Pressure Contours](3d_pressure.png) |
| *Flow field simulation over symmetrical NACA 00xx profile* | *Surrogate ML prediction of surface pressure coefficient* |

| Model Benchmark: Lift Curve ($C_L$ vs AoA) | Drag Polar Prediction ($C_L$ vs $C_D$) |
| :---: | :---: |
| ![Lift Curve](lift_curve.png) | ![Drag Polar](drag_polar.png) |
| *RANS emulation vs FFBPNN regressor* | *Surrogate aerodynamic efficiency polar envelope* |

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

## ⚙️ Engineering Pipeline

* **Dataset Synthesis:** Generates over 3,000 synthetic aerodynamic data points calibrated against empirical NACA formulations ($\alpha \in [-4^\circ, 18^\circ]$, $\text{Re} \in [5 \times 10^5, 5 \times 10^6]$, $\text{Ma} \in [0.1, 0.6]$).
* **Multi-Model Benchmarking:** Directly evaluates Multiple Linear Regression (MLR), Support Vector Machines (SVM), and Multi-Layer Feed-Forward Neural Networks (FFBPNN).
* **Potential Flow Field Simulation:** Real-time superposition of uniform freestream vectors and bound vortex circulation (Kutta-Joukowski lifting theory) across NACA 4-digit profiles.
* **Inverse Shape Optimization:** Employs SciPy SLSQP non-linear optimization to identify cruise geometry maximizing $L/D$.
* **Deployment Artifacts:** Serialized `.pkl` models and scalers ready for inference pipelines.

---

## 🛠️ Tech Stack

* **Core Programming:** Python 3
* **Scientific Computing & Aerodynamics:** NumPy, SciPy
* **Predictive Modeling:** Scikit-Learn (MLPRegressor, SVR, LinearRegression)
* **Visualization:** Plotly, Matplotlib
* **Serialization:** Joblib

---

## 🚀 Quickstart (Run Online)

No local installation or high-end computer required. You can run and inspect this entire project directly in the cloud from your mobile phone or browser:

1. **Launch in Cloud Runtime:**
   Click the **Open In Colab** badge at the top or upload the `.ipynb` file to Deepnote. All dependencies (`numpy`, `scipy`, `scikit-learn`, `plotly`, `matplotlib`) run directly on cloud servers.
2. **Execute Full Pipeline:**
   Select **Runtime** > **Run all** to execute the flow calculations, train the surrogate neural networks, and render the aerodynamic visual contours.
3. **Interactive Inspection:**
   To interact with the rotatable 3D pressure surfaces and streamline field without executing any code cells, launch the notebook via the **nbviewer** badge above.
