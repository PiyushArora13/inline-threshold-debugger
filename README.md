# inline-threshold-debugger

Non-Intrusive USB-C Inline Diagnostic PCB for Master–Slave Systems

Overview

This project presents a non-intrusive inline hardware debugger PCB designed for master–slave embedded architectures, where continuous electrical monitoring is required without altering normal system behavior. The board is placed directly in-line between master and slave nodes, enabling real-time observation of voltage and current characteristics while preserving signal integrity.

The design focuses on high-impedance sensing and comparator-based threshold detection, ensuring that monitored signals experience minimal loading and no functional disturbance. This approach allows the debugger to operate transparently within active systems, making it suitable for live diagnostics, validation, and safety monitoring.

A USB Type-C pass-through interface is used for both input and output, providing a compact, reversible, and standardized physical layer compatible with modern embedded and robotics platforms.

System Architecture

The PCB is built around an Arduino Nano (ATmega328P), which serves as the central processing unit for data acquisition, threshold evaluation, and status indication. The microcontroller samples analog signals via its ADC and coordinates with dedicated comparator stages to classify operating conditions deterministically.

Current sensing is implemented using the ACS712 Hall-effect current sensor, providing galvanically isolated measurement with low insertion impact on the monitored path. This enables accurate current monitoring while maintaining electrical separation and system safety.

Voltage monitoring is achieved through a high-impedance sensing network followed by comparator stages configured with predefined threshold levels. Comparator outputs allow fast detection of limit violations independent of firmware execution latency, ensuring reliable indication under transient conditions.

The inline signal path is designed to maintain impedance continuity between master and slave devices, allowing the debugger PCB to function as a transparent diagnostic layer rather than an active system element.

Threshold Evaluation and Visual Indication

Measured voltage and current parameters are continuously evaluated against predefined threshold regions. The system provides immediate visual feedback through:

Discrete LEDs indicating individual threshold events

An RGB LED representing overall system state:

Green – Normal / safe operating region

Yellow – Warning or near-limit condition

Red – Critical or unsafe operating condition

This hardware-level indication enables rapid fault identification without requiring external instruments or software-based debugging tools.

Design Intent and Rationale

Non-intrusive monitoring: High-impedance sensing and isolated current measurement prevent disturbance of the original signal path.

Comparator-based thresholding: Ensures fast, deterministic response independent of microcontroller timing.

Inline architecture: Allows real-time diagnostics in active master–slave systems.

USB Type-C interface: Provides a compact, reversible, and standardized physical connection.

Separation of sensing and indication: Improves robustness and simplifies system-level fault analysis.

Applications

Inline debugging of master–slave embedded systems

Power and signal integrity validation

Current and voltage health monitoring

Safety threshold enforcement in robotics and control systems

Rapid fault detection during system integration and testing

Project Status

Hardware: Prototype PCB designed and validated

Firmware: Threshold evaluation and visual indication logic implemented

Future work: Data logging, configurable thresholds, and host-side visualization
