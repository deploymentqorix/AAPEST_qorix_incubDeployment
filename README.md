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

## Structure 
project_extracted/
    AAPEST_qorix_incubDeployment-main/
        README.md
        configuration/
            diagnostic_manager_manifest.arxml
            execution_manifest.arxml
            extended_vehicle_manifest.arxml
            health_monitoring_manifest.arxml
        doc/
            doxygen.conf
            simulation_flow_diagram.drawio
            simulation_flow_diagram.png
        src/
            main.cpp
            application/
                extended_vehicle.cpp
                extended_vehicle.h
                doip/
                    diag_message_handler.cpp
                    diag_message_handler.h
                    doip_client.cpp
                    doip_client.h
                    doip_server.cpp
                    doip_server.h
                    obd_to_doip_converter.cpp
                    obd_to_doip_converter.h
                    vehicle_id_request_handler.cpp
                    vehicle_id_request_handler.h
                helper/
                    argument_configuration.cpp
                    argument_configuration.h
                    curl_wrapper.cpp
                    curl_wrapper.h
                    fifo_checkpoint_communicator.cpp
                    fifo_checkpoint_communicator.h
                    log_recovery_action.cpp
                    log_recovery_action.h
                    memory_cache.h
                    network_configuration.cpp
                    network_configuration.h
                    read_data_by_identifier.cpp
                    read_data_by_identifier.h
                    rpc_configuration.cpp
                    rpc_configuration.h
                platform/
                    diagnostic_manager.cpp
                    diagnostic_manager.h
                    execution_management.cpp
                    execution_management.h
                    platform_health_management.cpp
                    platform_health_management.h
                    state_management.cpp
                    state_management.h

