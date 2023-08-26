# tfml-env-pub

## Step by step guide to create a TensorFlow 2.0, CUDA enabled, Python environment within WSL2.
In hopes of helping others subvert the trials and tribulations of setting up a fully function TenserFlow 2.0 environment, I decided to record my process and share it with the masses.

The goal of this project is to aid in the setup and configuration of a CUDA enabled TensorFlow 2.0 Machine Learning environment (TFML) within WSL2.

### Requirements and Assumptions
1. A CUDA enabled NVIDIA GPU or above
    1. Check the CUDA Compatibility list for more info - https://developer.nvidia.com/cuda-gpus
    1. Recommended Compute capability of 5.0
1. A CUDA enabled NVIDIA driver is installed in Windows
    1. I have the NVIDIA Studio Driver | Version: 536.99 Release date: 08/08/2023
    1. Game Ready Drivers work as well
1. An Ubuntu WSL2 Distro is up and running in a supported Windows build
    1. Recommended: Ubuntu 22.04.3 LTS
    1. Recommended: 5.15.90.1-microsoft-standard-WSL2
1. Network/Internet is available within Windows and the WSL2 environment
1. A user was created during the deployment of Ubuntu
1. Basic understanding of ubuntu Linux Command Line, PowerShell and Python
    1. Nothing heavy is needed to get started

### Primary environment info
1. TensorFlow version: 2.13.0
1. Keras version: 2.13.1
1. Python version: 3.11.4
1. ipykernel: 6.25.1
1. WSL: 5.15.90.1-microsoft-standard-WSL2
1. Ubuntu version: Ubuntu 22.04.3 LTS
1. CUDA NVCC version: 12.2.128
1. CUDA Toolkit version: 11.8.0
1. Jupyter Core version: 5.3.1
1. Conda version: 23.7.3

Full list of packages.
https://github.com/BrandXX/tfml-env-pub/blob/master/tfml/conda-env-export.yaml

## More about Tensorflow and Cuda

CUDA on WSL User Guide
1.  CUDA on WSL User Guide
    1. https://docs.nvidia.com/cuda/archive/11.5.2/pdf/CUDA_on_WSL_User_Guide.pdf
    1. Also located at /docs/cuda_on_wsl_user_guide.pdf

1. Tensorflow Compatibility list
    1. https://www.tensorflow.org/install/source#gpu

1. Tensorflow's main site
    1. https://www.tensorflow.org/

1. NVIDIA's Developer site
    1. https://developer.nvidia.com/

## More to come

Moving forward, I plan to release a WSL install guide, DirectML install guide, example projects, useful instructions, scripts, code snippets and more.







