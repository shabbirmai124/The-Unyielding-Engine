# The Unyielding Engine

Welcome to the **Unyielding Engine** workspace. This repository contains two major components:
1. **RayTracer**: An advanced CPU-based ray casting engine.
2. **RayEngine**: A real-time, OpenGL-accelerated graphics and physics engine.

---

## 🚀 RayEngine (Real-Time Graphics & Physics)

`RayEngine` is a custom-built, modern C++ game engine framework focusing on real-time rendering via OpenGL 4.6 and integrated physics simulations. 

It provides a modular architecture with distinct subsystems for:
- **Core Application Layer** (Windowing, Events)
- **Geometry Processing** (Meshes, Vertex Buffers)
- **Shader Management** (GLSL loading and compilation)
- **Math Utilities** (GLM Integration)
- **Physics Simulation** (Integration hooks ready)
- **Acceleration Structures** (BVH stubs for high-performance culling/tracing)

### 📊 Project Statistics & Tech Stack

- **Primary Language**: C++17
- **Shader Language**: GLSL (Version 330 core / 430 core for Compute)
- **Build System**: CMake (Minimum Version 3.16)

**Dependencies (Automatically fetched via CMake):**
- **GLFW** (v3.3.8) - Context creation and window management.
- **GLM** (v0.9.9.8) - OpenGL Mathematics.
- **GLAD** (v2.0.4) - OpenGL Loader Generator.
- **ImGui** (Docking Branch) - Immediate Mod GUI for tooling and debug interfaces.

**Subsystem Breakdown:**
- `src/core/`: Application loop (`Application.h/cpp`), Window management (`Window.h/cpp`).
- `src/renderer/`: Hardware interfacing (`Renderer.cpp`), Shader pipeline (`Shader.cpp`).
- `src/geometry/`: Buffer mapping (`Mesh.cpp`).
- `src/math/`: Linear algebra pipelines.
- `src/physics/`: Logic ticks (`PhysicsWorld.cpp`).
- `src/acceleration/`: Bounding Volume Hierarchies (`BVH.cpp`).
- `src/utils/`: High-resolution timers and file operations (`Timer.h`, `FileUtils.h`).

---

## 🛠️ Build & Run Instructions

### Prerequisites
1. **CMake** (v3.16 or higher) installed and accessible in your system's PATH.
2. A **C++17 Compiler** (MSVC on Windows, GCC/Clang on Linux/macOS).
3. Active internet connection (Required for CMake's `FetchContent` to download dependencies during the first build).

### Building RayEngine

1. **Open a Terminal / PowerShell** at the root of the `RayEngine` directory:
   ```powershell
   cd "g:\All Unique Project Plan\The Unyielding Engine\RayEngine"
   ```

2. **Generate Build Files**:
   Tell CMake to configure the project and generate the build system in a new `build/` directory.
   ```powershell
   cmake -S . -B build
   ```

3. **Compile the Engine**:
   Run the build process. CMake will automatically fetch GLFW, GLM, ImGui, and GLAD before compiling the engine source.
   ```powershell
   cmake --build build --config Release
   ```

### Running RayEngine

After a successful compilation, the executable will be located inside the generated build directory (the exact path depends on your compiler, e.g., MSVC outputs to `build\Release\RayEngine.exe`).

Run the engine from the command line:
```powershell
.\build\Release\RayEngine.exe
```
*(Note: If using a single-configuration generator like MinGW/Makefiles, the executable will just be `.\build\RayEngine.exe`)*

Upon running, you should see a newly created window displaying a continuously rendered colored triangle spinning up the OpenGL context, alongside console logs confirming subsystem initialization.
