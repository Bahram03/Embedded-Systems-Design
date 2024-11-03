# Embedded Systems - Homework 1 Report

## Introduction
This report addresses various aspects of embedded real-time systems, with a focus on system modeling and control. The assignments were designed to explore the development processes, system modeling in Simulink, and control strategies. All simulations were performed using the principles outlined in the course materials.

## Problem 1: Development Models
### Part A: Comparison of Development Models
Different development models, including **Waterfall**, **Spiral**, and **Agile**, were evaluated for their suitability in embedded system design. Here’s a summary of each:

- **Waterfall Model**: Linear and structured, with clear milestones but limited flexibility in handling changes. It is best for projects with well-defined requirements from the start.
- **Spiral Model**: Combines iterative development with risk management, making it suitable for complex projects with evolving requirements.
- **Agile Model**: Highly adaptable and focused on customer collaboration and feedback, suitable for projects with rapid changes in requirements.

Each model’s strengths and weaknesses were assessed in terms of flexibility, risk management, and suitability for embedded systems projects.

### Part B: Concurrent Engineering
Concurrent engineering involves designing and testing different components of the system simultaneously. This approach can reduce development time and improve product quality, especially for complex, multi-disciplinary projects. An example is **AT&T’s PBX systems**, which leveraged concurrent engineering to streamline collaboration between designers, manufacturers, and marketing teams, resulting in improved coordination and faster product releases.

## Problem 2: Mass-Spring-Damper System Modeling
### Part A: System Setup
A mass-spring-damper system was modeled with the following parameters:
- **Mass (m)**: 1 kg
- **Damping Coefficient (b)**: 10 Ns/m
- **Spring Constant (k)**: 100 N/m

The governing equation for the system is:

\[
F(t) = k \cdot x(t) + b \cdot \frac{dx(t)}{dt} + m \cdot \frac{d^2x(t)}{dt^2}
\]

The Simulink model setup used integrator blocks to simulate this system behavior.

### Part B: System Response
The system response was evaluated under various initial conditions and external forces, such as:
- **Step Force at \( t=0 \)**: \( F(t) = 10 \) N
- **Sine Wave Force**: \( F(t) = 10 \sin(2\pi t) \)

Below are the screenshots of the simulation outputs for different conditions:

- **Step Input Response** ![Screenshot](screenshots/1.jpg)
- **Sine Wave Input Response** ![Screenshot](screenshots/2.jpg)

Each simulation provides insights into the system's oscillatory behavior and stability under different external inputs.

## Problem 3: Feedback Control Design
### Part A: PD Controller Design
A **Proportional-Derivative (PD) controller** was designed to regulate the displacement of the mass by minimizing the error from a desired setpoint. The control law is defined as:

\[
F(t) = -K_p \cdot x(t) - K_d \cdot \frac{dx(t)}{dt}
\]

Different values for \( K_p \) and \( K_d \) were tested to observe the system's response:

- \( K_p = 1 \), \( K_d = 0 \)
- \( K_p = 1000 \), \( K_d = 0 \)
- \( K_p = 1000 \), \( K_d = 1 \)

### Part B: System Response with PD Controller
The following results show how the PD controller affected the system response. As \( K_p \) and \( K_d \) values were adjusted, the system displayed varying levels of stability and responsiveness.

- **PD Controller Response \( K_p = 1000, K_d = 0 \)** ![Screenshot](screenshots/3.jpg)
- **PD Controller Response \( K_p = 1000, K_d = 1 \)** ![Screenshot](screenshots/4.jpg)

Increasing \( K_p \) increased the system’s response rate, while adjusting \( K_d \) helped dampen oscillations.

### Observations
The feedback control system exhibited improved stability with carefully selected \( K_p \) and \( K_d \) values. Higher \( K_p \) values led to faster responses, but excessive values could cause instability. Adding derivative control (\( K_d \)) helped reduce overshoot and oscillations, achieving a more stable response.

## Conclusion
This assignment provided practical insights into development models, system modeling, and feedback control in embedded systems. Using Simulink to model a mass-spring-damper system and applying PD control allowed us to observe real-time system behavior under different scenarios. The study of development methodologies also highlighted the importance of choosing the right model for effective project management in embedded system design.
