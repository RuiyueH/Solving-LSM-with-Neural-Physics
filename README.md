# SEB-model

## Requirements

This project uses **Python 3.11.8**. Before running the notebooks, install the following packages:

```
numpy==1.26.4
matplotlib==3.8.2
torch==2.1.2
pandas==2.2.1
scipy==1.12.0
xarray==2023.12.0
```

You can install all required packages using:

```
pip install -r requirements.txt
```

## Overview

This repository contains code to create forward and inverse models using the NN4PDEs method. 

To help users understand the NN4PDEs method, we have included some sample code in the Jupyter notebook **Sample code.ipynb**. This notebook shows how we can calculate the second-order derivative of Sin(x) using the NN4PDEs method. 

The other folders contain code for the land surface model. Each of the folder contains Jupyter notebooks for the forward/inverse models, output files, and code and figures for visualising results. Below is a summary of the contents:

### Forward model/
- **Forward_SEB_model.ipynb**: This file contains code for the forward model. It solves for temperature profiles in the soil over time, given known physical parameters and boundary conditions. 
- **Output files**: This file contains synthetic temperature data at specified depths are saved as text files (e.g., `Target_T1.txt`, `Target_T2.txt`) for use in inverse modeling.

### Inverse model_Synthetic data/
- **Inverse_SEB_model_Synthetic_data_1depth.ipynb**: This file performs inverse modelling to estimate input parameters from synthetic temperature data at a single depth. It uses backpropagation to fit input parameters so that the simulated temperature matches the synthetic data. 
- **Inverse_SEB_model_Synthetic_data_2depths.ipynb**: This file is similar to the single-depth inverse model, except it uses synthetic temperature data from two depths for improved parameter estimation.
- **Output files**: These files contain the final parameter values from optimisation runs (e.g., `final_parameter_values_*.txt`).
- **Synthetic data_graphs.ipynb**: This file contains code to generate figures based on the results obtained from the inverse models. 

### Inverse model_West Phoenix/
- **Inverse_SEB_model_WestPhoenix.ipynb**: The file applies the inverse modelling approach to flux tower data from West Phoenix, US. 
- **Output files**: These files contain the final parameter values from optimisation runs (e.g., `final_parameter_values_WP_T5T15_*.txt`).
- **West Phoenix_graphs.ipynb**: This file contains code to generate figures based on the results obtained from the West Phoenix inverse model. 

---
For more details on each notebook's workflow, requirements, and usage, please refer to the markdown cells and comments within each notebook. 