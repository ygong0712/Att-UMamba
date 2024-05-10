# nnU-Mamba
 
## Installation for Google Colab

### Environment setup
!pip install torch==2.0.1 torchvision==0.15.2 --index-url https://download.pytorch.org/whl/cu118

!pip install causal-conv1d>=1.2.0

!pip install mamba-ssm --no-cache-dir

!git clone https://github.com/ygong0712/nnU-Mamba

%cd /content/nnU-Mamba/umamba

!pip install -e .

!rm -rf /content/nnU-Mamba/data/nnUNet_raw

!rm -rf /content/nnU-Mamba/data/nnUNet_preprocessed

!rm -rf /content/nnU-Mamba/data/nnUNet_results

!cp -rp YOUR_PATH /content/nnU-Mamba/data



### Libs
import torch

import mamba_ssm

import os
