 # Numerical Modelling & Simulation (FEM / MBD)

## 📌 Project Overview
This repository contains advanced simulation projects developed for the **Numerical Modelling and Simulation** course. The work is divided into two main modules: **Multi-Body Dynamics (MBD)** applied to robotic systems and **Finite Element Method (FEM)** applied to automotive components.

---

## 📂 Module 1: Multi-Body Dynamics & Simulation
**Subjects:** Rigid Body Transformations, SCARA Robot, 5-DOF Serial Manipulator.
**Tools:** MSC Adams, MATLAB.

This module explores the complete Multi-Body Dynamics (MBD) workflow, starting from theoretical foundations up to complex inverse dynamics simulations validated against commercial software.

### 1.1 Fundamentals: Rigid Body Transformations
* **Goal:** Practical implementation of spatial rotations and coordinate system transformations.
* **Analysis:**
    * Computation of **Homogeneous Transformation Matrices** (${}^{0}A_{1}$).
    * Execution of sequential rotations (Euler-like angles) on a rigid body (Triangle) about fixed ($x_0$) and mobile axes ($y_1, x_2$).
    * **Visualization:** Developed MATLAB scripts to plot unit vectors and vertex trajectories during rotation.

### 1.2 Kinematics of a SCARA Robot (R-R-P)
* **System:** 3-Link SCARA robot with two rotary joints and one prismatic joint.
* **Kinematic Modeling:**
    * Applied **Denavit-Hartenberg (DH)** convention to define reference frames for links 0 to 3.
    * Computed Forward Kinematics matrices to define the robot's wire-frame structure.
* **Trajectory Tracking:** Simulated the motion of the End-Effector (EE) and plotted the full wire-frame configuration in initial and final states.

### 1.3 Dynamics of a 5-DOF Serial Manipulator
* **System:** 5-Axis robot consisting of an articulated arm (3 DOF) and a wrist (2 DOF).
* **MBD Modeling (MSC Adams):**
    * Created a full multi-body model using **Data Splines** for joint trajectories and **Akima Fitting** for smooth motion profiles (displacement, velocity, acceleration).
* **Inverse Dynamics (MATLAB):**
    * Implemented a **Recursive Newton-Euler Algorithm (RNEA)** script (`dynam_en02.m`) to propagate forces and moments from the end-effector to the base.
    * **Inertia Tensor:** Calculated inertia matrices ($I_G$) for all 5 bodies approximating them as parallelepipeds and cylinders.
* **Validation:** Verified that the **Actuator Torques** ($\tau_1 - \tau_5$) and base reaction forces calculated in MATLAB perfectly matched the MSC Adams simulation results.

---

## 📂 Module 2: Finite Element Analysis (FEM)
**Subject:** Structural, Thermal, and Modal Analysis
**Tools:** Altair Hypermesh (Pre-processing), Optistruct (Solver), Hyperview (Post-processing)

### 2.1 Cantilever Beam: Mesh Convergence Study
* **Goal:** Validate numerical convergence against analytical **De Saint-Venant theory**.
* **Methodology:**
    * Modeled a $100 \times 20 \times 5$ mm beam.
    * Compared **CQUAD4** (4-node shell) vs. **CTRIA3** (3-node shell) elements.
    * Analyzed the impact of mesh density on result accuracy (Displacement, Von Mises Stress).
* **Result:** Demonstrated that Quad elements provide superior convergence rates and stress accuracy compared to Triangular elements for bending problems.

### 2.2 Connecting Rod: Linear Static Analysis
* **Goal:** Stress analysis of a combustion engine connecting rod under critical cycle loads.
* **Load Cases:**
    1.  **Tensile Load:** Simulating Inertia forces at Top Dead Center (TDC) exhaust.
    2.  **Compressive Load:** Simulating Peak Gas Pressure.
* **Modeling:**
    * Applied **RBE2/RBE3** rigid elements to distribute loads on the pin/crank eyes.
    * Refined mesh at fillets to capture Stress Concentration Factors ($K_t$).

### 2.3 Vehicle Chassis: Stiffness Evaluation
* **Goal:** Evaluate the torsional and bending stiffness of a Ladder Frame chassis.
* **Modeling:** Used **1D Beam Elements** (CBEAM) with defined cross-sections (Box, C-Shape).
* **Analysis:**
    * **Torsional Stiffness:** Applied opposite vertical loads at the suspension mounting points.
    * **Bending Stiffness:** Applied vertical loads at the center of the wheelbase.

### 2.4 Experimental Modal Analysis (Model Updating)
* **Goal:** Correlate a FEM model with experimental vibration data (Impact Hammer Test).
* **Process:**
    1.  Performed experimental modal analysis on an aluminium beam to extract Natural Frequencies and Mode Shapes.
    2.  Built a FEM model and tuned material parameters (**Young's Modulus $E$, Density $\rho$**) to match the experimental FRF (Frequency Response Function).
* **Result:** Achieved a frequency correlation error $< 2\%$ for the first two bending modes.




