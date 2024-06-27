# MAGE-RBD
## Generation of novel paired heavy-light chain antibody sequences against SARS-CoV-2 using large language models
Monoclonal Antibody GEnerator (MAGE) - a fine-tuned LLM for generating paired heavy-light antibody variable sequences with predicted binding specificity to wildtype SARS-CoV-2 receptor binding domain (RBD).

This repository contains Python scripts to accompany Wasdin et al., including model fine-tuning, antibody generation, and the follow-up analyses presented in the manuscript. All analyses were initially ran in Linux Red Hat 8.4, but have also been tested in Ubuntu 22.04. For training, 4 V100s were used and for antibody generation, an Nvidia A6000 was used.

The following libraries are needed, we recommened installing these within a Conda environment with Python 3.11. Note that other versions are likely compatible, but we used the following. 
* Numpy 1.26
* Pandas 2.1.1
* Scikit-learn 1.3.0
* Matplotlib 3.8.1
* Seaborn 0.13.1
* Jupterlab 3.6.3

Model training and generation require the following libraries:
* PyTorch 2.1.0 with pytorch-cuda 11.8
* Transformers 4.32.1

The Progen2 repository must be pulled to interface with and download the model:
https://github.com/enijkamp/progen2
(This has been included in this folder for reviewers)

Once downloaded, move to the 'progen' directory here in order to import within the training/generation scripts.

Follow-up Analyses used these additional libraries:
* python-Levenshtein 0.25.0
* pandarallel 1.6.4 (to speed up Pandas functions)
* Abnumber 0.3.2 (this should

## Overview of directories
_Data cleaning_: notebooks for cleaning data, including a variety of different sources.

_Output_analysis_: notebooks for recreating figures in manuscript

_Antibody_generation_: script for generating antibody sequences against RBD. This yields a CSV file with raw sequences which can be analyzed using the notebooks in the previous directory.
- To run, specify n number of sequences to generate, and an output csv name.
- Example: python generate_antibodies.py --n=1 --output=MAGE_antibodies.csv
- This was tested on an Nvidia A6000 and took ~15 seconds to generate one antibody sequence.
  
_Fine_tuning_: script and example subset dataset (n=1000) for fine-tuning Progen2.
