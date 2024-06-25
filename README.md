# MAGE-RBD
## Generation of novel paired heavy-light chain antibody sequences against SARS-CoV-2 using large language models
Monoclonal Antibody GEnerator (MAGE) - a fine-tuned LLM for generating paired heavy-light antibody variable sequences with predicted binding specificity to wildtype SARS-CoV-2 receptor binding domain (RBD).

This repository contains Python scripts to accompany Wasdin et al., including model fine-tuning, antibody generation, and the follow-up analyses presented in the manuscript.
General libraries used:
* Numpy 1.26
* Pandas 2.1.1
* Scikit-learn 1.3.0
* Matplotlib 3.8.1
* Seaborn 0.13.1

Model training and generation require the following libraries:
* PyTorch 2.1.0 with pytorch-cuda 11.8
* Transformers 4.32.1

The Progen2 repository much be pulled to interface with and download the model:
https://github.com/enijkamp/progen2

Once downloaded, move to the 'progen2' directory here in order to import within the training/generation scripts.

Follow-up Analyses used these additional libraries:
* python-Levenshtein 0.25.0
* pandarallel 1.6.4 (to speed up Pandas functions)
* Abnumber 0.3.2 (this should

