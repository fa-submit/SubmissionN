# Temporal Augmentations for Robust Time Series Forecasting

This repository provides a comprehensive setup for evaluating time series forecasting methods, including:

- ✅ **Baseline models** (e.g., ARIMA, Transformer, Informer, Autoformer, FEDformer, ForecastPFN, etc.)
- ✅ Our **proposed Mixup-based method for time series forecasting**, implemented on top of neural-based Transformer architectures.

## Repository Structure

```
.
├── benchmark/               # Contains ForecastPFN and baseline model evaluation code
├── proposed-mixup/         # Contains our proposed Mixup-based method implementation
├── academic_data.zip       # Zipped datasets used across all experiments
├── requirements.txt        # Python dependencies for both benchmark and mixup code
├── README.md               # (You are here) Overview of the full repository
```

## Getting Started

To run any code in this repository (both baseline and proposed method), please follow the steps below.

### 1. Set Up Environment

We recommend using `conda` or `venv` to manage your environment.

```bash
# Create a virtual environment
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

Alternatively, if you're using `conda`:

```bash
conda create -n ts-forecasting python=3.9
conda activate ts-forecasting
pip install -r requirements.txt
```

### 2. Prepare Datasets

Extract the provided `academic_data.zip` file into the root directory:

```bash
unzip academic_data.zip
```

After extraction, the datasets will be available under:

```
academic_data/
├── illness/
├── exchange/
├── ecl/
├── etth1/
├── etth2/
├── weather/
└── traffic/
```

These are used by both the baseline and the Mixup method code.

---

## Running the Code

### 🔹 Baseline + ForecastPFN Evaluation

Navigate to the `benchmark/` folder and run:

```bash
bash run.sh
```

This will evaluate models including ForecastPFN and other baselines on the datasets.

### 🔹 Our Proposed Mixup Method

Navigate to the `proposed-mixup/` folder and run:

```bash
bash run.sh
```

This script will execute our Mixup-based approach on supported Transformer architectures.

---

## Citation and Acknowledgment

We build on the official [ForecastPFN](https://github.com/automl/ForecastPFN) codebase for baseline evaluation and thank the authors for open-sourcing their work.

If you use this repository, please consider citing both the original ForecastPFN paper and our method.

---

