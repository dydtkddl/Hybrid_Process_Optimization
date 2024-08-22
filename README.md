# Hybrid_Process_Optimization

**Team:** Octet Innovator  
**Competition:** Chemical Engineering Process Design Competition 2024  

---

## Overview
This repository contains the full implementation of our hybrid modeling approach for chemical process optimization. Our project focuses on integrating large-scale simulations with machine learning models to optimize reactor and scrubber systems efficiently. The primary goal is to analyze and optimize complex process conditions in a systematic and automated manner, leading to the identification of the most economically favorable process combinations.

## Project Structure

The repository is structured as follows:

- **`/simulation/`**: Contains the Python scripts and configuration files used to automate large-scale process simulations in Aspen and AVEVA.
- **`/data/`**: Includes the raw simulation data, processed datasets, and filtered data used for machine learning training and inference.
- **`/models/`**: Houses the machine learning models, along with scripts for training, evaluation, and inference.
- **`/results/`**: Contains the final results of the large-scale inference and optimization processes, including the economic analysis and semi-final process combinations.
- **`/docs/`**: Documentation related to the project, including detailed reports and explanations of each step.

## Key Steps

### 1. Simulation Data Generation
- **Software**: Aspen and AVEVA were used to simulate a wide range of process conditions in the scrubber and reactor systems.
- **Automation**: Python scripts were developed to automate the simulation process, resulting in over 100,000 cases being generated and stored in the `/data/` directory.

### 2. Machine Learning Model Development
- **Training**: The simulation data was used to train machine learning models capable of predicting scrubber outputs and optimizing reactor conditions.
- **Preprocessing**: The raw simulation data was cleaned, filtered, and preprocessed (e.g., scaling and normalization) before being split into training, validation, and test sets.
- **Model**: Multiple machine learning algorithms were tested, and the best-performing model was selected for large-scale inference.

### 3. Large-scale Inference and Optimization
- **Inference**: The trained model was used to infer millions of potential process combinations, significantly reducing the time required for manual simulations.
- **Filtering**: The predicted combinations were filtered to ensure they met process constraints and operational feasibility.
- **Clustering**: Data clustering techniques, such as DBSCAN, were applied to reduce the number of process combinations to a manageable level for further analysis.

### 4. Economic Analysis
- **Cost Estimation**: Equipment costs, operating expenses, and potential revenue were calculated for each optimized process combination.
- **Net Profit Calculation**: A detailed economic analysis was performed, considering factors such as inflation and operational longevity, to identify the most profitable process combinations.

## Requirements

To run the simulations, train the machine learning models, and perform inference, the following dependencies are required:

- Python 3.x
- `pandas`
- `numpy`
- `scikit-learn`
- `tensorflow` or `pytorch` (depending on the chosen ML framework)
- `matplotlib`
- Aspen (for process simulations)
- AVEVA (for process simulations)

You can install the necessary Python libraries using the following command:

```bash
pip install -r requirements.txt
