# Setup-NVIDIA-GPU-for-Deep-Learning

## Step 1: NVIDIA Video Driver


- First, find the which NVIDA Gpu are we using.
```bash
nvidia-smi 
```
- If not find the full name then go to **Device Manager** then **Display Adaptor** 

You should install the latest version of your GPUs driver. You can download drivers here:
 - [NVIDIA GPU Drive Download](https://www.nvidia.com/Download/index.aspx)


## Step 2: Visual Studio C++

You will need Visual Studio, with C++ installed. By default, C++ is not installed with Visual Studio, so make sure you select all of the C++ options.
 - [Visual Studio Community Edition](https://visualstudio.microsoft.com/vs/community/)

## Step 3: Anaconda/Miniconda

You will need anaconda to install all deep learning packages
 - [Download Anaconda](https://www.anaconda.com/download/success)

## Step 4: CUDA Toolkit

 - [Download CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit-archive)

 - [kon_cuda_driver_jono_kon_cuda_tooklit_namate_parbo](https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html)

## Step 5: cuDNN

 - [Download cuDNN](https://developer.nvidia.com/rdp/cudnn-archive)


## Step 6: Install PyTorch 

 - [Install PyTorch](https://pytorch.org/get-started/locally/)




## Finally run the following script to test your GPU

```python
import torch

print("Number of GPU: ", torch.cuda.device_count())
print("GPU Name: ", torch.cuda.get_device_name())


device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
print('Using device:', device)
```
