# BrainLM

[![Preprint License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC_BY--NC--ND_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-nd/4.0/)

Pytorch implementation of Brain Language Model (BrainLM), aiming to achieve a general understanding of brain dynamics through self-supervised masked prediction. 
![Alt text](/figures/brainlm_overview.png)

# Quickstart
Clone this repository locally:

```
git clone https://github.com/vandijklab/BrainLM.git
```


Create an Anaconda environment by running the setup file:

```
sh setup.sh
```

And check the installation of major packages (Pytorch, Pytorch GPU-enabled, huggingface) by running these lines in a terminal:
```
python -c "import torch; print(torch.randn(3, 5))"
python -c "from transformers import pipeline; print(pipeline('sentiment-analysis')('I love you'))"
```


# Datasets

The UK Biobank dataset, used for pretraining BrainLM, has a data sharing agreement which does not allow for direct public sharing of the dataset. To get access, you can apply to the UK Biobank for access to their fMRI data, and follow their preprocessing pipeline (https://www.fmrib.ox.ac.uk/ukbiobank/fbp/) followed by using our preprocessing scripts (https://github.com/vandijklab/BrainLM/blob/main/toolkit/BrainLM_Tutorial.ipynb) to arrive at the same data.

# Data Preprocessing

Checkout first 3 cells of brainlm_tutorial.ipynb for preprocessing data. Some are processed differently than others and might require changes to the script located at toolkit/BrainLM-Toolkit.py, mostly transposing the matrix.

# Running Inference 

brainlm_tutorial.ipynb provides a pipeline for zero-shot predictions. Models can be downloaded from [HF repo](https://huggingface.co/vandijklab/brainlm/) which includes both 111M and 650M param models. We're still working to release the finetuned models.


# Training Models

To train a model on Yale HPC, see the example HPC job submission script in ```scripts/train_brainlm_mae.sh```.

# Pre-trained model

The weights for our pre-trained model can be downloaded from [huggingface](https://huggingface.co/vandijklab/brainlm/)

# Environment Creation

You'll probably need a separate environment to run larger models (111M and 650M), both of which require flash attention which can be tricky to install. Just run setup.sh to setup the environment.


# My Own Setup:

1. Clone the repo
2. python3.10 -m venv . under repo root
3. pip install -r requirements.local.txt

