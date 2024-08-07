# Att-UMamba


## 3D whole-body CT/PET PSMA Visualization
<div align="center"><img width="420" height="420" src=""></div>

## Installation for Google Colab

### Environment setup
`!pip install torch==2.0.1 torchvision==0.15.2 --index-url https://download.pytorch.org/whl/cu118`

`'!pip install causal-conv1d>=1.2.0'`

`!pip install mamba-ssm --no-cache-dir`

`!git clone https://github.com/ygong0712/Att-UMamba`

`%cd /content/Att-UMamba/umamba`

`!pip install -e .`




`!cp -rp YOUR_DATA_PATH /content/Att-UMamba/data`

`!cp -rp YOUR_PREPROCESSED_DATA_PATH /content/Att-UMamba/data`




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


## Train 3D Att-UMamba models

- Train 3D Att-UMamba model

```bash
nnUNetv2_train DATASET_ID 3d_fullres all -tr nnUNetTrainerUMambaBot
```



## Inference

- Predict testing cases with the `Att-UMamba` model

```bash
nnUNetv2_predict -i INPUT_FOLDER -o OUTPUT_FOLDER -d DATASET_ID -c CONFIGURATION -f all -tr nnUNetTrainerUMambaBot --disable_tta
```


# Acknowledgements

We thank the authors of [nnU-Net](https://github.com/MIC-DKFZ/nnUNet), [U-Mamba](https://github.com/bowang-lab/U-Mamba), and [Mamba](https://github.com/state-spaces/mamba) for making their valuable code publicly available.
