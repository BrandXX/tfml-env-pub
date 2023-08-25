# tfml-env-pub

## Step by step guide to create a TensorFlow 2.0, CUDA enabled, Python environment within WSL2.


The goal of this project is to aid in the setup and configuration of a CUDA enabled WSL2 environment.


Requirements and Assumptions
1. 'A CUDA enabled NVIDIA GPU or above'
    1. 'Check the CUDA Compatibility list for more info - https://developer.nvidia.com/cuda-gpus'
    1. 'Recommended Compute capability of 5.0'
1. 'A CUDA enabled NVIDIA driver is installed in Windows'
    1. 'I have the NVIDIA Studio Driver | Version: 536.99 Release date: 08/08/2023'
    1. 'Game Ready Drivers work as well'
1. 'An Ubuntu WSL2 Distro is up and running in a supported Windows build'
    1. 'Recommended: Ubuntu 22.04.3 LTS'
    1. 'Recommended: 5.15.90.1-microsoft-standard-WSL2'
1. 'Network/Internet is available within Windows and the WSL2 environment'
1. 'A user was created during the deployment of Ubuntu'
1. 'Basic understanding of ubuntu Linux Command Line, PowerShell and Python'
    1. 'Nothing heavy is needed to get started'


## For more info, please review the included documents


CUDA on WSL User Guide
    1. 'cuda_on_wsl_user_guide.pdf (located in the /docs/ directory)'
    1. 'https://docs.nvidia.com/cuda/archive/11.5.2/pdf/CUDA_on_WSL_User_Guide.pdf'

Tensorflow Compatibility list
    1. 'https://www.tensorflow.org/install/source#gpu'

Tensorflow's main site
    1. 'https://www.tensorflow.org/'

NVIDIA's Developer site
    1. 'https://developer.nvidia.com/'


## More to come

Moving forward, I plan to release a WSL install guide, DirectML install guide, example projects, useful instructions and code, code snippets and more.

I also plan to do an in-depth look into the packages that are loaded via the conf-env-tfml.yaml file. 

