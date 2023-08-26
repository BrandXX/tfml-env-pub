# Step by Step Guide to Create a Tensorflow 2.0, CUDA Enabled, Python Environment within WSL2
#### This quick start guide assumes:

*   A CUDA enabled NVIDIA GPU is present. Check the [CUDA Compatibility list](https://developer.nvidia.com/cuda-gpus) for more info.
*   A CUDA enabled NVIDIA driver is installed in Windows.
*   An Ubuntu WSL2 Distro is up and running in a supported Windows build.
*   Network/Internet is available within Windows and the WSL2 environment.
*   A user was created during the deployment of Ubuntu.
*   Basic understanding of Ubuntu Linux command line, PowerShell, and Python (Nothing heavy is needed).

#### More info:

*   TFML = TensorFlow Machine Learning.
*   My Distro is named 'ubuntu-tfml' which I use in the examples.
*   My Conda environment is named 'tfml' which I use in the examples.

## Getting Started
#### Set the Default User in /etc/wsl.conf
> **Note:** This must be done as root
```
sudo su
echo -e '# My TFML Environment \n[boot] \nsystemd=true \n \n[user] \ndefault=userx \n' > /etc/wsl.conf
```

#### Restart Ubuntu
> **Note:** Exit Ubuntu, then in PowerShell, run the following:
```
wsl --shutdown
wsl -d ubuntu-tfml
```

#### Update/Upgrade with apt
```
sudo apt update && sudo apt upgrade
```

#### Create the Folder Structure
```
cd ~
mkdir {_admin,_temp,docs,downloads,env,projects,env/base,env/tfml}
```

#### Download Latest Version of Miniconda
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -P ~/downloads/
```

#### Install Miniconda
```
bash ~/downloads/Miniconda3-latest-Linux-x86_64.sh
```

#### Cleanup Install Files
```
rm ~/downloads/Miniconda3-latest-Linux-x86_64.sh
```

#### Restart Ubuntu
> **Note:** Exit Ubuntu, then in PowerShell, run the following:
```
wsl --shutdown
wsl -d ubuntu-tfml
```

#### Update Conda
```
conda update conda
```

#### Save the Environments Package Info in 'env/base'
```
conda env export > ~/env/base/conda-env-export.yaml
```

#### Create and Activate the tfml Environment
```
wget https://raw.githubusercontent.com/BrandXX/tfml-env-pub/master/tfml/conda-env-export.yaml -P ~/env/tfml/
conda env create --file=env/tfml/conda-env-export.yaml
conda activate tfml
```

## Tensorflow 2 Configuration
#### Config Conda environment activation scripts and set GPU Lib env var
```
mkdir -p $CONDA_PREFIX/etc/conda/activate.d
echo 'CUDNN_PATH=(python -c "import nvidia.cudnn;print(nvidia.cudnn.__file__)")' >> $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
echo 'export LD_LIBRARY_PATH=CUDNN_PATH/lib:$LD_LIBRARY_PATH' >> CONDA_PREFIX/lib/nvvm/libdevice/
cp -p $CONDA_PREFIX/lib/libdevice.10.bc $CONDA_PREFIX/lib/nvvm/libdevice/
echo 'export XLA_FLAGS=--xla_gpu_cuda_data_dir=$CONDA_PREFIX/lib' >> CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
```

## Testing the Environment
#### Verify Test01
```
python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
```

#### Verify Test02
```
python3 -c "import tensorflow.compat.v1 as tf; tf.test.is_gpu_available()"
```

#### Verify Test03
```
python3 -c "import tensorflow.compat.v1 as tf; tf.enable_eager_execution(tf.ConfigProto(log_device_placement=True)); print(tf.add([1.0, 2.0], [3.0, 4.0]))"
```

## Finishing Up
#### Save Package Lists for tfml environment
```
conda env export > ~/env/tfml/conda-env-export.yaml
```

#### Backup the WSL Distro via PowerShell
> **Note:** Do any additional configuration(s) before backing up. This should be the last step...
```
wsl --export ubuntu-tfml path/ubuntu-tfml-00.tar
```

## Install and Configure VScode
> **Note:** No need to install VScode in your WSL environment. Install VScode on your ***WINDOWS*** host machine. Once installed, run ```code .``` from the Linux terminal.
```
code.
```

#### Recommended VScode Extensions

*   Visual Studio Code Remote Development Extension Pack
*   Python Development Extensions Pack
*   Git Extension Pack
*   Backup the WSL Environment

## Additional Useful Info
#### Set GIT Global Username and Email
```
git config --global user.name "Your Name"
git config --global user.email "youremail@yourdomain.com"
```

#### Confirm GIT Config Changes
```
git config --list
```

#### Saving Package Info
> **Note:** Recommended method
```
conda env export > ~/env/tfml/conda-env-export.yaml
```
> **Note:** The following method can be used with |  ```pip install -r ~/env/tfml/requirements.txt```
```
pip freeze > ~/env/tfml/requirements.txt
```
> **Note:** Additional methods
```
conda list --explicit > ~/env/tfml/package-list-explicit_tf2.txt
conda list > ~/env/tfml/package-list-simple_tf2.txt
```

## Check Versions and Info
#### Check Python Version
```
python3 --version
```

#### Check Tensorflow Version
```
python3 -c "import tensorflow as tf; print('TensorFlow version:', tf.__version__)"
```
#### Check Keras Version
```
python -c 'import keras; print(keras.__version__)'
```

#### NVIDIA Environment Info
```
nvidia-smi
```

> **Note:** formatting and indentation might need further adjustments based o

&copy; Johnathan Carroll 2023. All Rights Reserved.
