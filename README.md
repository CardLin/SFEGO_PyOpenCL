# Spatial Frequency Extraction using Gradient-liked Operator (SFEGO)
## PyOpenCL Version
### Introduction
- In 1D signal, we can use Empirical Mode Decomposition (EMD) to analysis the signal and decomposetition the signal to several Intrinsic Mode Function (IMF) that can see the different frequency band's signal that composition the input signal.

- In 2D or higher dimension signal, there is Bi-dimensional Empirical Mode Decomposition (BEMD) and Multi-dimensional Ensemble Empirical Mode Decomposition (MEEMD) can decompose the 2D signal into different Bi-dimensional Intrinsic Mode Function (BIMF).

- Now, we are using Gradient-liked Operator that can choose different Radius=Wavelength (different spatial frequency) to do Differental on 2D signal to get the vector map (magnitude and direction=phase) Then we can do Integral on vector map to get Spatial Frame that contain such a spatial frequency information in specific Radius.

- So... this is a mimic of MEEMD. The BIMF1, BIMF2, BIMF3, BIMF4 and BIMF5 of MEEMD is very similar to R=1, R=2, R=6, R=12 and R=27 of SFEGO.

- Our work about this project is starting with name Gradient-based Multi-dimensional Empirical Mode Decomposition (GMEMD) but finally we don't use EMD... so we change the title to Spatial Frequency Extraction using Gradient-liked Operator (SFEGO)

### Hardware Requirement
- Require GPU to execute OpenCL Kernel Code

- Recommend to use NVIDIA GPU with 1GB+ VRAM (VRAM usage is depend on Image Size)

- AMD Integrated GPU and Intel Integrated GPU can also run this project

- Although It can also run OpenCL on CPU mode but even the Intel Integrated GPU is faster than high-end CPU

### Execution
- python SFEGO.py lena.png

- Modify Platfrom_ID(AMD, Intel, NVIDIA) and Device_ID(GPU0, GPU1...) to select OpenCL target

- Also can use ctx = cl.create_some_context() instead cl.Context() to select OpenCL target every time you run the code