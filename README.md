# Adaptive AUTOSAR Platform Environment Simulation Tool  

This project provides a **simulation tool for Adaptive AUTOSAR environments**, designed to emulate execution management and communication behaviors.  
It is implemented in C++ and integrates socket-based polling, asynchronous execution, and runtime configuration through command-line arguments.  

---

## Features  

- **Execution Management**  
  Uses `application::platform::ExecutionManagement` to initialize and terminate AUTOSAR-like execution cycles.  

- **Asynchronous Polling**  
  Leverages `AsyncBsdSocketLib::Poller` to simulate socket communication and event-driven execution.  

- **Runtime Configuration**  
  Command-line arguments are parsed via `ArgumentConfiguration` to securely fetch and manage:  
  - VCC API Key  
  - OAuth 2.0 Bearer Token  

- **Deterministic Polling Cycle**  
  Controlled by `ara::exec::DeterministicClient::cCycleDelayMs` to ensure predictable execution timing.  

---

## Project Structure  

---

## Build Instructions  

### Prerequisites  
- **C++17 or later**  
- **CMake** (recommended)  
- POSIX-compatible environment (Linux/macOS)  

### Build with CMake  

```bash
mkdir build && cd build
cmake ..
make
```

This generates an executable, e.g. `adaptive_autosar_sim`.  

---

## Usage  

Run the executable:  

```bash
./adaptive_autosar_sim
```

The tool will:  
1. Ask for the **VCC API Key**.  
2. Ask for the **OAuth 2.0 Bearer Token**.  
3. Initialize execution management and begin polling.  
4. Wait for user input (`Enter` twice) to terminate.  

---

## Example  

```text
Enter VCC API Key: *********
Enter OAuth Bearer Token: *********
[System initialized... Polling started]

Press ENTER to continue...
```

---

## Future Improvements  

- Integration with full **Adaptive AUTOSAR Execution Management APIs**.  
- Logging framework for detailed traceability.  
- Configurable polling cycle delay.  
- Docker containerization for easy deployment.  
