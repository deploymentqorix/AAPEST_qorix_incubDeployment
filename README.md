Adaptive AUTOSAR Platform Environment Simulation Tool

This project provides a simulation tool for Adaptive AUTOSAR environments, designed to emulate execution management and communication behaviors.
It is implemented in C++ and integrates socket-based polling, asynchronous execution, and runtime configuration through command-line arguments.

Features

Execution Management
Uses application::platform::ExecutionManagement to initialize and terminate AUTOSAR-like execution cycles.

Asynchronous Polling
Leverages AsyncBsdSocketLib::Poller to simulate socket communication and event-driven execution.

Runtime Configuration
Command-line arguments are parsed via ArgumentConfiguration to securely fetch and manage:

VCC API Key

OAuth 2.0 Bearer Token

Deterministic Polling Cycle
Controlled by ara::exec::DeterministicClient::cCycleDelayMs to ensure predictable execution timing.
Build Instructions
Prerequisites

C++17 or later

CMake (recommended)

POSIX-compatible environment (Linux/macOS)

Build with CMake
