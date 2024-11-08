# DCS: PC-9/A EFM by Check Six Simulations

## Introduction

The **PC-9A** is a turboprop military trainer aircraft developed by **Pilatus Aircraft**. It is widely used by air forces worldwide for basic and advanced pilot training. The aircraft features a **PT6A-62 turboprop engine**, known for its reliability and efficiency, providing a maximum shaft horsepower (SHP) of up to **950 HP**. The PC-9A is designed to deliver realistic handling, high maneuverability, and a comprehensive suite of training capabilities.

This module aims to deliver a **Professional Flight Model (PFM)** for the **PC-9A** in DCS World, providing a realistic and immersive flight experience. The model includes detailed simulations of the engine, fuel, electrical, hydraulic, and other critical systems.

---

## Features

The **PC-9A EFM** module for DCS World includes the following features:

1. **Realistic Engine Model**:
   - Accurate simulation of the **PT6A-62 turboprop engine**, including:
     - **Torque (TQ)**
     - **Interturbine Temperature (ITT)**
     - **Gas Generator Speed (Ng)**
     - **Propeller Speed (Np)**
     - **Fuel Flow**
     - **Oil Temperature**
     - **Oil Pressure**
   - Detailed engine dynamics including **startup**, **shutdown**, and **in-flight behavior**.
   - Integrated **Electronic Limiting System (ELS)** to prevent engine overspeed and overheating.

2. **Fuel System**:
   - Simulates the main and auxiliary fuel tanks with accurate fuel flow, consumption, and transfer behavior.
   - Manual and automatic fuel pump operation.
   - Realistic fuel consumption rates based on engine power settings.

3. **Electrical System**:
   - Full simulation of the primary and secondary electrical systems.
   - Includes generator and battery operations, with load monitoring and failure modes.

4. **Hydraulic System**:
   - Simulates the hydraulic systems for landing gear, brakes, and flight control surfaces.
   - Includes realistic pressure drops during high-demand operations.

5. **Flight Control System**:
   - Realistic flight control response, including ailerons, rudder, and elevator inputs.
   - Simulates control surface deflection based on pilot input and hydraulic pressure.

6. **ImGui Debug Menu**:
   - Real-time monitoring of engine and system parameters using an integrated **ImGui** debug panel.
   - Displays critical information such as **Torque**, **Ng**, **ITT**, **Fuel Flow**, **Oil Temp**, and **Oil Pressure** for testing and debugging purposes.

---

## Installation

To integrate the **PC-9A EFM** into your DCS World setup, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Dillen198/PC9A_EFM.git
   ```

2. **Project Setup**:
   - Open the **PC9A_EFM** project in **Visual Studio** or your preferred IDE.
   - Ensure that all ImGui files (`imgui.cpp`, `imgui_draw.cpp`, `imgui_widgets.cpp`, `imgui_impl_opengl3.cpp`, etc.) are included in your project.

3. **Build the EFM**:
   - Select the appropriate build configuration (e.g., **Release x64**).
   - Build the project. The output DLL (`PC9A_EFM.dll`) will be located in the `x64/Release` folder.

4. **Copy the EFM DLL**:
   - Copy the `PC9A_EFM.dll` to your DCS World Mods folder:
     ```
     Saved Games\DCS\Mods\Aircraft\PC-9A\bin\
     ```

5. **Configure the Aircraft**:
   - Ensure that the `FMOptions.lua` file is properly configured to use the EFM:
     ```lua
     FM = {
         self_ID = "PC-9A",
         file = "bin/PC9A_EFM.dll",
         type = "external",
     }
     ```

---

## How to Use the Aircraft Manual

The **PC-9A Aircraft Manual** provides detailed information on the aircraft's performance, procedures, and systems. To make full use of the manual:

1. **Engine Operations**:
   - Refer to the **Engine Performance Data** section for information on throttle settings, power curves, and fuel consumption.
   - Use the **Startup and Shutdown Procedures** for realistic engine handling in the simulation.

2. **Fuel Management**:
   - Consult the **Fuel System Overview** for details on fuel tank capacities, pump operations, and emergency procedures.

3. **Electrical and Hydraulic Systems**:
   - Refer to the **Systems Description** sections for in-depth explanations of electrical load management, hydraulic pressure, and failure modes.

4. **Performance Charts**:
   - Use the **Performance Data Charts** for accurate reference during flight, including takeoff, climb, cruise, and landing performance.

---

## Troubleshooting

If you encounter any issues during installation or operation, consider the following:

1. **ImGui Not Displaying**:
   - Ensure that `ImGui::NewFrame()` and `ImGui::Render()` are called every frame in your main loop.
   - Check that all ImGui source files are included in the project and linked correctly.

2. **Linker Errors**:
   - Verify that all necessary libraries (`imgui.lib` or equivalent) are linked in the project settings.
   - Ensure the correct paths are set for include and library directories.

3. **Engine Model Issues**:
   - Refer to the **Aircraft Manual** for correct engine performance data and ensure it matches the implemented model.
   - Check the debug panel for real-time feedback on engine parameters and identify any discrepancies.

---

## Future Updates

Planned enhancements for the **PC-9A EFM** module include:
- Improved failure simulations for engine and system components.
- Enhanced avionics and navigation systems.
- Additional flight model refinements based on real-world flight data.
