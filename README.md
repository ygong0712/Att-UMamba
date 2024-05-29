# nnU-Mamba
 
## Installation for Google Colab

### Environment setup
`!pip install torch==2.0.1 torchvision==0.15.2 --index-url https://download.pytorch.org/whl/cu118`

`'!pip install causal-conv1d>=1.2.0'`

`!pip install mamba-ssm --no-cache-dir`

`!git clone https://github.com/ygong0712/nnU-Mamba`

`%cd /content/nnU-Mamba/umamba`

`!pip install -e .`


`!rm -rf /content/nnU-Mamba/data/nnUNet_raw`

`!rm -rf /content/nnU-Mamba/data/nnUNet_preprocessed`

`!rm -rf /content/nnU-Mamba/data/nnUNet_results`

`!cp -rp YOUR_PATH /content/nnU-Mamba/data`




### Python packages

```bash
import torch

import mamba_ssm

import os
```

## Preprocessing

```bash
nnUNetv2_plan_and_preprocess -d DATASET_ID --verify_dataset_integrity
```


## Train 3D models

- Train 3D `U-Mamba_Bot` model

```bash
nnUNetv2_train DATASET_ID 3d_fullres all -tr nnUNetTrainerUMambaBot
```



## Inference

- Predict testing cases with `U-Mamba_Bot` model

```bash
nnUNetv2_predict -i INPUT_FOLDER -o OUTPUT_FOLDER -d DATASET_ID -c CONFIGURATION -f all -tr nnUNetTrainerUMambaBot --disable_tta
```


# Acknowledgements

We thank the authors of [nnU-Net](https://github.com/MIC-DKFZ/nnUNet), [U-Mamba](https://github.com/bowang-lab/U-Mamba), and [Mamba](https://github.com/state-spaces/mamba) for making their valuable code publicly available.
