# SBI‑Workshop‑Legend2025

This repository contains materials for a hands‑on workshop on **simulation‑based inference (SBI)** in population genetics.  The workshop is organised around a series of Jupyter notebooks that gradually introduce SBI methods, demonstrate toy examples, and apply these techniques to coalescent simulations using the [`msprime`](https://tskit.dev/msprime/docs/stable) library.

## Repository structure

```
sbi_workshop_Legend2025/
├── LICENSE                
├── README.md              # This overview
├── requirements.yaml      # Conda environment specification
└── notebooks/             # Jupyter notebooks for the workshop
      ├── 1_introduction_to_sbi.ipynb
      ├── 2_data_simulation_msprime.ipynb
      ├── 3_sbi_in_popgen.ipynb
      ├── 4_playground_complex_scenario.ipynb
      └── 5_snakemake_workflow.ipynb

```

## Getting started
### **The installation requires large memory usage, so we highly recommend you to set up the environment in advance!**

We recommend using **Visual Studio Code** or JupyterLab for exploring the notebooks.  To set up a working environment:

1. **Install Conda**: If you do not already have a conda distribution (e.g., Miniconda), install it from <https://docs.conda.io/en/latest/miniconda.html>.

2. **Clone the repository**: clone the workshop repo to your local machine
   ```bash
   git clone https://github.com/ningyuxin1999/SBI-WORKSHOP-LEGEND2025.git

   cd SBI-WORKSHOP-LEGEND2025
   ```
3. **Create an environment**: Use the provided `requirements.yaml` to create a reproducible environment:

   ```bash
   conda env create -f requirements.yaml
   conda activate sbi-workshop
   ```
   The `requirements.yaml` file lists the core dependencies (`msprime`, `tskit`, `torch`, `sbi`, `matplotlib`, etc.).  Feel free to install additional packages manually. 
   
   You might need to upgrade jupyter:
   ```bash
   pip install --upgrade notebook jupyter_server jupyterlab jupyter_core traitlets
   ```

4. **Launch notebooks**: Open the notebooks folder in VS Code or run

   ```bash
   jupyter notebook notebooks/
   ```

## Notebook overview

### Notebook 1: Introduction to SBI
Understand the syntax of the `sbi` package and the concept of Neural Posterior Estimation (NPE):
* Inference on a simple Linear Gaussian model.
* Define a `Prior`, a `Simulator`, and run the `NPE` trainer to learn parameter-data relationships.

### Notebook 2: Data Simulation with msprime
Generate genetic data and summary statistics.
* Simulating constant populations, extracting genotype matrices from tree sequences, and the Site Frequency Spectrum (SFS).

### Notebook 3: SBI in Population Genetics
SBI in inference of popgen parameters
* Inferring effective population size ($N_e$) and recombination rates from SFS data.
* The whole workflow: generating training data ($\theta, x$), training the density estimator, and performing posterior predictive checks.

### Notebook 4: Playground and Complex Demographic Scenarios
Handling real-world complexity and custom classes. 
* Defining custom prior and model simulation.

### Notebook 5: Snakemake Workflow
Reproducibility and scaling.
* Integrating the [popgensbi_snakemake](https://github.com/kr-colab/popgensbi_snakemake) pipeline.
* Automating training and prediction tasks via Snakemake configurations.

---

## Acknowledgement
Thanks to Prof.Franz Baumdicker, Dr.Lukas Tatzel, Dr.Hannah Götsch, Axel Fehrenbach, and Johannes Kippnich for building up this workshop together. 

---

## Contributing

...
