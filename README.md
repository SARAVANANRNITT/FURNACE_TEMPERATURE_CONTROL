# Advanced Furnace Control & Energy Recovery: A High-Fidelity Simulink Project

![Project Status](https://img.shields.io/badge/status-in%20progress-yellow)
![MATLAB](https://img.shields.io/badge/MATLAB-R2022a%2B-blue)
![Simulink](https://img.shields.io/badge/Simulink-Required-orange)
![License](https://img.shields.io/badge/License-MIT-green)

## 📌 Executive Summary

This repository presents a world-class MATLAB/Simulink simulation of an industrial furnace control system, grounded in a real-world industrial challenge from an internship at **Chennai Petroleum Corporation Limited (CPCL)**. The project focuses on stabilizing the outlet temperature of a **Delayed Coker Unit (DCU) furnace**, a critical process in petroleum refining.

Beyond standard PID control, this model incorporates an **energy recovery heat exchanger** and serves as a digital testbed for developing and benchmarking **advanced intelligent controllers**, including a **Neural Network-based adaptive PID tuner**.

This repository showcases:
*   **High-Fidelity Process Modeling:** A modular, subsystem-based approach to simulating complex industrial dynamics.
*   **Real-World Problem Solving:** A solution directly addressing documented process instabilities (`±50°C` temperature swings).
*   **Energy Efficiency:** A functional model of a heat exchanger for feed preheating, demonstrating significant energy savings.
*   **Intelligent Control Integration:** A clear roadmap and foundational work for applying AI/ML (Neural Networks) to legacy control problems.

---

## 🎯 The Industrial Challenge: A Case Study from CPCL

In a modern refinery, process stability is paramount. This project is based on a significant operational challenge observed at a DCU furnace, which exhibited persistent temperature fluctuations of approximately **±50°C** around the critical process target of **580°C**.

This instability is not a minor issue; it has severe consequences:

*   🔥 **Inefficient Thermal Cracking:** Inconsistent temperatures lead to suboptimal breakdown of heavy hydrocarbons, reducing the yield and quality of valuable products like naphtha and diesel.
*   ⛽ **Wasted Energy & Increased Costs:** The control system consumes excess fuel in an attempt to correct deviations, leading to higher operational costs and emissions.
*   ⚙️ **Equipment Stress & Safety Risks:** Large temperature swings cause thermal stress on the furnace tubes, increasing the risk of coking, tube rupture, and costly unscheduled shutdowns.

## 💡 The Solution: A Modular, High-Fidelity Simulink Model

To address this challenge, a dynamic, closed-loop simulation was architected in Simulink. The model's philosophy is rooted in a **modular, subsystem-based design**, where each block represents a distinct physical or logical component of the real-world system. This approach allows for isolated testing, clear visualization of signal flow, and easy expansion.

### Detailed Subsystem Breakdown

*   **`Feed_System`**: Simulates the flow, pressure, and temperature of the heavy residual oil feedstock. It includes models for actuator dynamics (control valves) and is designed to accept process disturbances (e.g., changes in feed temperature) to test controller robustness.

*   **`Fuel_System` & `Air_System`**: These subsystems model the delivery of fuel and combustion air to the furnace burners. The air-to-fuel ratio is critical for complete and efficient combustion. These flows are the primary manipulated variables for the control loops.

*   **`Furnace Thermal Block`**: This is the heart of the simulation. It is a mathematical representation of the furnace's complex heat transfer dynamics. It receives energy inputs from the combustion process and calculates the resulting **Furnace Outlet Temperature** and internal **Furnace Pressure**.

*   **`Heat Exchanger`**: A critical component for energy efficiency. This subsystem models a heat exchanger that recovers energy from the hot furnace outlet stream to preheat the cold incoming feed. This reduces the overall energy demand on the furnace burners.

*   **`Sensors`**: To ensure the simulation is realistic, this subsystem mimics the behavior of industrial sensors (transmitters). It introduces **time lags** and **process noise**, forcing the controller to operate with the same imperfect information it would have in a real plant.

*   **`Controllers`**: The "brain" of the simulation. This subsystem contains both a baseline **industrial PID controller** and the framework for advanced controllers. It receives measured signals from the `Sensors` block, compares them to setpoints, and sends corrective signals to the `Fuel_System` and `Air_System`.

### Visualizing the Model Architecture
*(I will replace this with a screenshot of my top-level Simulink model)*
![Simulink Model Diagram](https://i.imgur.com/your-image-link.png)
*Caption: Top-level view of the modular furnace control simulation in Simulink.*

---

## 📊 Performance & Key Results

The baseline PID control strategy, when properly tuned using this model, successfully mitigates the initial instability. Key performance indicators achieved in the simulation include:

*   **Temperature Stabilization:** The furnace outlet temperature is held stable at the **580°C** setpoint with minimal deviation.
*   **Pressure Control:** The internal furnace pressure is maintained at a slight positive pressure (**~1.2 bar**) to ensure stable combustion and prevent air ingress.
*   **Combustion Efficiency:** The flue gas oxygen content is controlled within the optimal **2-5%** range, indicating efficient and complete combustion.

*(This section is a placeholder. Add your own simulation graphs for maximum impact!)*

| ![Furnace Outlet Temperature](https://i.imgur.com/graph1.png) | ![Fuel Flow Rate](https://i.imgur.com/graph2.png) |
| :----------------------------------------------------------: | :----------------------------------------------------: |
| *Fig 1: Outlet temperature stabilizes at the 580°C target.*  | *Fig 2: Fuel flow adjusts to meet energy demand.*      |

---

## 🌱 Roadmap: The Path to a World-Class Digital Twin

This project is not static. It is an evolving platform for demonstrating cutting-edge control techniques. The roadmap below outlines the planned progression.

-   [ ] **Phase 1: Model Validation (In Progress)**
    -   [ ] Acquire historical process data (DCS logs) from the real-world furnace.
    -   [ ] Compare simulation outputs against plant data to validate and refine the model's accuracy.

-   [ ] **Phase 2: Advanced Control Benchmarking**
    -   [ ] Implement a **Model Predictive Controller (MPC)** and compare its performance against the PID baseline, especially in handling constraints and disturbances.
    -   [ ] Develop and test a **Fuzzy Logic Controller** to manage process nonlinearities.

-   [x] **Phase 3: AI & Machine Learning Integration (Current Focus)**
    -   [x] Design and train a **Neural Network (NN)** to function as an adaptive PID tuner, adjusting controller gains in real-time based on changing process conditions.
    -   [ ] Explore the development of a standalone NN-based controller to replace the PID loop entirely.

-   [ ] **Phase 4: The Digital Twin**
    -   [ ] Enhance the model with real-time data connectivity.
    -   [ ] Develop a user interface for "what-if" scenario analysis, operator training, and predictive maintenance simulations.

---

## 🚀 Installation & Usage

1.  **Clone the Repository**
    ```bash
    git clone https://github.com/SARAVANANRNITT/FURNACE_TEMPERATURE_CONTROL.git
    ```
2.  **Open in MATLAB**
    *   Launch MATLAB (R2022a or newer is recommended).
    *   Navigate to the cloned repository folder.
    *   Open the `models/` directory and run the `furnace_temperature_control.mdl` file.
    *   *Note: Newer versions of MATLAB will automatically prompt you to save a copy in the `.slx` format. It is recommended to do so.*
3.  **Run the Simulation**
    *   Open the model and press the "Run" button.
    *   Double-click on the Scope blocks to view the real-time plots of key process variables.

---

## 📂 Repository Structure
FURNACE_TEMPERATURE_CONTROL/
├── README.md # You are here!
├── LICENSE # The MIT License for this project
└── models/
└── furnace_temperature_control.mdl # The core Simulink model
code
Code
*(Folders for `/data`, `/docs`, and `/results` will be added as the project matures.)*

---

## 📜 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

This project would not have been possible without the invaluable experience and insights gained during an internship at **Chennai Petroleum Corporation Limited (CPCL)**. Special gratitude is extended to **Mr. A. Gowthaman, Chief Manager at CPCL**, for his mentorship and guidance. This work was conducted as part of the B.Tech in Instrumentation and Control Engineering at the **National Institute of Technology, Tiruchirappalli (NIT Trichy)**.

---

## 📬 Contact

I welcome contributions, suggestions, and professional inquiries.

**Author:** Saravanan R
*   **LinkedIn:** [https://www.linkedin.com/in/saravanan-r-nitt/](https://www.linkedin.com/in/saravanan-r-nitt/)
*   **Email:** saravananraja6765965@gmail.com
