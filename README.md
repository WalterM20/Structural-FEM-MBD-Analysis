# Structural FEM & Multi-Body Dynamics

## 📌 Project Overview
A comprehensive collection of simulations covering static structural analysis, modal analysis, and kinematic simulation of mechanical systems.

## 📂 Modules

### 1. Finite Element Analysis (FEM)
* **Tools:** Hypermesh, Optistruct, Hyperview.
* **Cantilever Beam:** Mesh convergence study comparing 3-node vs. 4-node shell elements.
* **Connecting Rod:** Linear static analysis of a combustion engine rod (inertia and gas pressure loads). Optimized mesh quality to analyze stress concentration at the fillets.
* **Vehicle Chassis:** 1D beam element analysis to evaluate torsional and bending stiffness of a ladder frame.

### 2. Experimental & Numerical Modal Analysis
* **Subject:** Aluminium cantilever beam.
* **Method:** Comparison between experimental data (impact hammer testing) and FEM simulation.
* **Outcome:** Tuned the FEM model (Young's Modulus and Damping) to match the first two natural frequencies found experimentally, achieving a precise Bode plot correlation.

### 3. Multi-Body Dynamics (MBD)
* **Tools:** MSC Adams, MATLAB.
* **System:** 5-DOF SCARA Robot.
* **Analysis:** Inverse dynamics to calculate required joint torques for a specific trajectory. Validated kinematic consistency between MATLAB scripts and Adams simulations.

## 💻 Tech Stack
* **CAE Tools:** Altair Hyperworks (Hypermesh/Optistruct), MSC Adams.
* **Scripting:** MATLAB for analytical validation.
