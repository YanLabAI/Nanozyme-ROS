# Nanozyme-ROS

Nanozyme-ROS is a manuscript-facing data and reproducibility release for the study of nanozyme-mediated reactive oxygen species (ROS) homeostasis in crops.

This repository contains the curated literature-derived dataset and the XGBoost reproducibility notebook used for model development, response prediction, feature-importance analysis, and nanozyme screening in the associated manuscript. Large working files, intermediate drafts, local analysis outputs, and manuscript figure-editing assets are not included in this release.

## Manuscript Dataset

The manuscript-reported analyses used the frozen v1.0 curated dataset in:

```text
data/crop_nanozyme_ros_dataset_v1.0.xlsx
```

The dataset contains 1,329 curated experimental records from 57 peer-reviewed studies. Each record describes a crop response to metal oxide nanomaterials/nanozymes under defined exposure conditions. The dataset includes 22 variables covering study identifiers, DOI, plant species, exposure target, exposure medium, experimental environment, concentration class, plant life stage, nanoparticle type, endpoint information, material descriptors, exposure timing, and RRDelta.

## Repository Layout

```text
data/                    Curated manuscript dataset
notebooks/               Reproducibility notebook for XGBoost modelling
outputs/                 Generated outputs from local notebook runs (ignored)
README.md                Repository documentation
LICENSE                  Data and code reuse licence
requirements.txt         Python package requirements for notebook execution
```

Key release files:

```text
data/crop_nanozyme_ros_dataset_v1.0.xlsx
notebooks/os3-xbg-repro.ipynb
requirements.txt
```

## Installation

Python 3.9 or newer is recommended.

```bash
pip install -r requirements.txt
```

The reproducibility notebook uses common scientific Python packages, including pandas, numpy, scikit-learn, xgboost, shap, matplotlib, seaborn, and openpyxl.

## Running the Reproducibility Notebook

Open and run:

```text
notebooks/os3-xbg-repro.ipynb
```

The notebook is configured to read the curated dataset from:

```text
../data/crop_nanozyme_ros_dataset_v1.0.xlsx
```

When executed from the `notebooks/` directory, the notebook trains the XGBoost regression model, evaluates train/test performance, exports prediction and feature-importance tables, and optionally performs SHAP-based model interpretation.

Generated local outputs are written to:

```text
outputs/
```

The `outputs/` directory is intentionally excluded from version control because figures and exported tables can be regenerated from the dataset and notebook.

## Data Fields

The main worksheet is:

```text
Curated_dataset
```

The dataset includes the following column groups:

| Group | Variables |
|---|---|
| Study metadata | Study ID, DOI |
| Experimental conditions | Plant species, exposure target, exposure medium class, medium description, experimental environment, concentration class, plant life stage |
| Nanozyme/material descriptors | Nanoparticle type, molecular weight, atomic number of metal, number of metal atoms, number of oxygen atoms, metal electronegativity, period number of metal, nanoparticle size |
| Exposure and response | Exposure start time, exposure duration, endpoint detail, RRDelta |

## Validation and Reproducibility Notes

The released dataset is the frozen v1.0 table used for manuscript analyses. The notebook provides a reproducible XGBoost workflow using fixed random seeds and a scikit-learn preprocessing pipeline with one-hot encoding for categorical variables and scaling for numeric variables.

The notebook is intended to reproduce the machine-learning workflow and key exported analysis tables. Minor numerical differences may occur across operating systems or package versions, especially for stochastic model components.

## Citation

If you use this dataset or notebook, please cite the associated manuscript:

```text
Citation will be added after publication.
```

## License

This repository is released under the license provided in `LICENSE`.

