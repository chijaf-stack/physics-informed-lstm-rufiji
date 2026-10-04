# Modelling Seasonal Streamflow in the Rufiji River Basin

This repository contains the data-processing workflows, modelling codes, analysis scripts, and supporting materials for the study:

**Modelling of Seasonal Streamflow for Water Resource Planning in the Rufiji River Basin: A Deep Learning-Based Approach**

The study investigates the application of machine learning, deep learning, and physics-informed deep learning approaches for seasonal streamflow modelling in the Rufiji River Basin, Tanzania.

## Research Objective

The main objective is to develop and evaluate data-driven and physics-informed approaches for modelling seasonal streamflow to support water resource planning and management in the Rufiji River Basin.

## Study Area

The study focuses on the **Rufiji River Basin in Tanzania**, with streamflow observations obtained from the Rufiji Basin Water Board (RBWB). The basin is one of Tanzania's major river basins and is important for hydropower generation, agriculture, and other water-resource uses.

## Data

The study uses monthly data covering **2018–2022**, including:

* Streamflow observations from RBWB
* Reservoir release information associated with the Julius Nyerere Hydropower Project
* CHIRPS precipitation data
* NASA POWER meteorological variables
* Tanzania Meteorological Authority meteorological observations
* SRTM-derived elevation and slope information
* Soil and land-use/land-cover information

The final modelling dataset contains **60 monthly observations**.

## Models

Several modelling approaches are implemented and compared:

* ARIMA
* Random Forest
* Long Short-Term Memory (LSTM)
* Physics-Informed Neural Network (PINN)
* Hybrid Physics-Informed LSTM (PINN-LSTM)

The hybrid model incorporates a physics-based regularisation term based on a lumped **advection–diffusion formulation** to constrain the learning process.

## Methodology

The general workflow consists of:

1. Data collection and integration
2. Data quality assessment and preprocessing
3. Missing-value treatment
4. Exploratory data analysis
5. Feature preparation and temporal sequencing
6. Baseline model development
7. LSTM model development
8. Physics-informed model development
9. Hybrid PINN-LSTM development
10. Model evaluation and comparison
11. Interpretation of results for water resource planning

## Model Evaluation

Model performance is assessed using commonly used hydrological and statistical metrics, including:

* Nash–Sutcliffe Efficiency (NSE)
* Root Mean Square Error (RMSE)
* Coefficient of Determination (R²)

Additional validation and sensitivity analyses are used to examine model robustness and the influence of the physics-based constraint.

## Key Results

The hybrid PINN-LSTM approach achieved the strongest overall performance among the evaluated models.

On the held-out test period, the hybrid model achieved approximately:

* **NSE:** 0.942
* **RMSE:** 98.5 m³/s
* **R²:** 0.958

The results indicate that incorporating a physics-based regularisation term can improve the representation of seasonal streamflow dynamics compared with the standalone data-driven models evaluated in this study.

## Repository Structure

```text
rufiji-streamflow-deep-learning/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_data_preparation.ipynb
│   ├── 02_exploratory_analysis.ipynb
│   ├── 03_baseline_models.ipynb
│   ├── 04_lstm_model.ipynb
│   ├── 05_pinn_model.ipynb
│   └── 06_hybrid_pinn_lstm.ipynb
│
├── src/
│   ├── preprocessing/
│   ├── models/
│   ├── physics/
│   ├── evaluation/
│   └── visualisation/
│
├── results/
│   ├── figures/
│   ├── tables/
│   └── model_outputs/
│
├── requirements.txt
├── README.md
└── LICENSE
```

## Reproducibility

The repository is organised to support reproducible analysis. Python-based workflows are used for data preprocessing, model development, evaluation, and visualisation.

Before running the code, install the required dependencies:

```bash
pip install -r requirements.txt
```

Then follow the notebooks or scripts in the recommended order.

## Data Availability

Some datasets used in this study are obtained from external institutions and data providers and may be subject to their respective access and usage conditions.

Raw data that cannot legally be redistributed through this repository should **not** be uploaded. Where appropriate, the repository will provide information on the original data source and instructions for obtaining the data.

## Limitations

The study has several important limitations:

* The modelling dataset contains 60 monthly observations.
* The analysis is based on a relatively short concurrent observation period.
* The main experimental evaluation uses a temporal training–testing split.
* The physics component uses a lumped one-dimensional advection–diffusion formulation rather than a full distributed hydrodynamic model.
* The study focuses on seasonal/monthly streamflow modelling rather than sub-daily or daily forecasting.
* Further validation using longer records and independent catchments would strengthen the generalisability of the findings.

## Research Context

This repository accompanies Master's research in **Applied Mathematics and Computational Science and Engineering (AMCSE)** at the **Nelson Mandela African Institution of Science and Technology (NM-AIST)**.

## Citation

If you use this repository, methodology, or associated materials in your research, please cite the corresponding publication or dissertation.

```text
Chija, F. M. (2026).
Modelling of Seasonal Streamflow for Water Resource Planning
in the Rufiji River Basin: A Deep Learning-Based Approach.
Master's Dissertation, Nelson Mandela African Institution
of Science and Technology, Tanzania.
```

## Author

**Flydon Mashaka Chija**

MSc Applied Mathematics and Computational Science and Engineering
Nelson Mandela African Institution of Science and Technology
Tanzania

## Acknowledgements

The author acknowledges the institutions and data providers that contributed to the availability of hydrological, meteorological, remote-sensing, and geospatial data used in this research.

## License

This repository is intended primarily for **academic and research purposes**. Please check the repository license and the usage conditions of individual datasets before redistributing or reusing the materials.
