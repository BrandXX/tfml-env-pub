# tfml-env-pub

Step by step guide to create a TensorFlow 2.0, CUDA enabled, Python environment within WSL2.
The goal of this project is to aid in the setup and configuration of a CUDA enabled WSL2 environment.

Requirements and Assumptions
    # - A CUDA enabled NVIDIA GPU with a recommended Compute Capability of 5.0 or above is present.
        - Check the CUDA Compatibility list for more info - https://developer.nvidia.com/cuda-gpus
    # - A CUDA enabled NVIDIA driver is installed in Windows
        - I have the NVIDIA Studio Driver | Version: 536.99 Release date: 08/08/2023
        - Game Ready Drivers work as well
    # - An Ubuntu WSL2 Distro is up and running in a supported Windows build
        - Recommended: Ubuntu 22.04.3 LTS
        - Recommended: 5.15.90.1-microsoft-standard-WSL2
    # - Network/Internet is available within Windows and the WSL2 environment
    # - A user was created during the deployment of Ubuntu
    # - Basic understanding of ubuntu Linux Command Line, PowerShell and Python
        - Nothing heavy is needed to get started
    
