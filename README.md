# Basic Engineering Mechanics: Symbolic Analysis of Stress, Strain, and Axial Loading

An analytical mechanics workbook implementing closed-form symbolic solutions for foundational solid mechanics and strength of materials problems using Python and `SymPy`.

## Overview

This project models classical first-year deformable body mechanics without numerical approximations. It utilizes symbolic algebra to solve equilibrium equations, evaluate compatibility conditions, and derive relationships between mechanical properties.

The workbook covers four foundational modules:

1. **Uniaxial Stress, Elongation, and Modulus of Resilience**
   * Computes normal stress ($\sigma = \frac{P}{A}$) and axial elongation ($\delta = \frac{PL}{AE}$).
   * Uses symbolic integration over the elastic domain to derive the Modulus of Resilience ($u_r = \int_0^{\epsilon_y} E\epsilon \, d\epsilon = \frac{\sigma_y^2}{2E}$).

2. **Interrelations of Isotropic Elastic Constants**
   * Sets up generalized Hooke's Law relations ($E = 2G(1 + \nu)$ and $E = 3K(1 - 2\nu)$).
   * Solves simultaneous equations to express Young's Modulus ($E$) and Poisson's Ratio ($\nu$) purely in terms of Bulk Modulus ($K$) and Shear Modulus ($G$).

3. **Statically Indeterminate Axially Loaded Stepped Bar**
   * Analyzes a dual-segment stepped cylindrical bar fixed between two immovable boundaries.
   * Couples statics ($\sum F_x = 0$) with geometric compatibility ($\delta_1 + \delta_2 = 0$) using `sym.linsolve` to determine reaction forces ($R_A, R_C$).

4. **Direct Shear Stress and Factor of Safety (FOS)**
   * Formulates double-shear load distribution across cylindrical fasteners ($A_v = \frac{\pi d^2}{2}$).
   * Evaluates allowable safe working loads ($P_{\text{allowable}}$) based on material ultimate shear strength ($\tau_{\text{ult}}$) and design safety factors.

## Mathematical Formulations

* **Strain Energy Density (Resilience):**
  $$u_r = \int_0^{\epsilon_y} \sigma(\epsilon) \, d\epsilon = \frac{\sigma_y^2}{2E}$$

* **Coupled Elastic Moduli:**
  $$E = \frac{9KG}{3K + G}, \quad \nu = \frac{3K - 2G}{6K + 2G}$$

* **Indeterminate Compatibility:**
  $$\frac{R_A L_1}{A_1 E} - \frac{R_C L_2}{A_2 E} = 0 \quad \text{subject to} \quad R_A + R_C = P$$

## Prerequisites & Installation

To run the notebook locally, ensure Python 3.8+ is installed along with the required scientific computing libraries:

```bash
pip install sympy ipython jupyter
