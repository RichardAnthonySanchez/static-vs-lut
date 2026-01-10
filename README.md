# static-vs-lut

Comparing static wave shapers and LUT-based distortion in audio plug-ins.

This repository is dedicated to exploring and benchmarking various implementations of distortion effects, specifically comparing traditional mathematical (static) wave shapers with Look-Up Table (LUT) based approaches.

## 📁 Directory Structure

The project is organized by the language/platform of the plug-in implementations:

-   **/jsfx**: REAPER JSFX implementations.
-   **/cpp**: C++ implementations (VST3, AU, CLAP, etc.).
-   **/faust**: Implementations using the Faust functional DSP language.

## 🛠 Contributing

We welcome contributions from the community! Whether you are an expert in DSP or just getting started, your help is appreciated.

### How to Contribute

1.  **Fork the repository** and create your branch from `main`.
2.  **Choose a directory** based on the technology you are using:
    -   `jsfx/` for REAPER JSFX scripts.
    -   `cpp/` for C++ based implementations.
    -   `faust/` for Faust DSP code.
3.  **Follow the specific guidelines** in the README of each directory.
4.  **Ensure your code is documented** and follows standard practices for that platform.
5.  **Submit a Pull Request** with a clear description of your implementation and the distortion algorithm used.

### Contribution Areas

-   **New Distortion Algorithms**: Implement classic or novel distortion types in any of the supported formats.
-   **Benchmarking Tools**: Help us develop more accurate ways to measure the performance and aliasing differences between static and LUT methods.
-   **Documentation**: Improve the READMEs or add technical write-ups on the trade-offs of each approach.

## 🚀 Getting Started

### JSFX (REAPER)
To use or develop the JSFX plug-ins:
1.  Navigate to the `jsfx/` directory.
2.  Follow the detailed instructions in [jsfx/README.md](jsfx/README.md) for installation and setup within REAPER.

### C++
Details for C++ environment setup and build instructions will be added as implementations are contributed.

### Faust
Details for Faust compilation and usage will be added as implementations are contributed.
