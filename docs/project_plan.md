# Project Plan – Furnace Temperature Control with Energy Recovery (Neural Network Integration)

## 1. Project Overview
This project develops a high-fidelity **DCU Furnace Temperature Control System** in MATLAB/Simulink with:
- Realistic furnace thermodynamic modelling.
- Heat Exchanger subsystem for feed preheating and energy recovery.
- Intelligent control using **Neural Networks** integrated with or enhancing PID control.
- Fault and disturbance simulation for robustness testing.
- Benchmarked performance against traditional PID control and industrial standards.

---

## 2. Objectives
- Achieve stable furnace outlet temperature tracking under varying loads and disturbances.
- Improve energy efficiency through exhaust heat recovery.
- Demonstrate adaptive control via a neural network model.
- Document, visualize, and present results professionally for academic evaluation and portfolio impact.

---

## 3. Deliverables
- **MATLAB/Simulink Models:**
  - Furnace model
  - Heat exchanger model
  - PID + NN controller integration
- **Dataset:** Simulation logs for training/testing the NN model.
- **Results:** Plots, performance benchmarking, comparison with PID.
- **Documentation:**
  - P&ID diagram
  - Project report
  - README.md
  - `project_plan.md` (this file)
- **GitHub Repository:** Structured with folders (`models`, `data`, `results`, `docs`, `scripts`, `resources`).

---

## 4. Scope of Neural Network Integration
- **Controller Mode:** NN-based PID autotuning (dynamic adjustment of PID gains).
- **Inputs:** Setpoint, current outlet temperature, preheated feed temp, load change signals.
- **Outputs:** Optimal PID gains (Kp, Ki, Kd) or direct fuel/air valve positions.
- **Training:** Generated from simulation runs under varied operating conditions.

---

## 5. Execution Timeline (45 Days)

**Week 1:**  
- Finalize objectives & scope.  
- Set up GitHub with folder structure (`.gitkeep` files done).  
- Prepare initial furnace + heat exchanger PID simulation.

**Weeks 2–3:**  
- Run PID controller simulations for multiple scenarios.  
- Save datasets (`.mat` files) in `/data`.  
- Start preliminary NN plant model training.

**Week 4:**  
- Implement NN-PID autotuning logic in Simulink.  
- Test in closed loop, tune for stability and performance.

**Week 5:**  
- Benchmark NN controller vs PID (settling time, overshoot, energy savings).  
- Capture plots & results in `/results`.  
- Prepare P&ID and control philosophy documents in `/docs`.

**Week 6 (Final Days):**  
- Final polish of models, results, and documentation.  
- Push final repo to GitHub.  
- Prepare presentation/demo for professor.

---

## 6. Expected Outcomes
- Improved control stability over PID.
- Adaptive behavior that adjusts to disturbances.
- Clear visual evidence of performance gains.
- Publish-ready simulation model as a portfolio highlight.

---

## 7. References
- MATLAB Neural Network Toolbox documentation.
- Industrial furnace operation manuals and energy recovery literature.
- Previous academic publications on NN-based process control.

---

**Author:** *Saravanan R*  /
**Date Created:** *14/08/2025* / 
