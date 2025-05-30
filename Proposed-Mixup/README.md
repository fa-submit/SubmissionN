# Time Series Forecasting with Proposed Vanilla-Mixup 

This directory builds upon the [ForecastPFN](https://github.com/automl/ForecastPFN) codebase. Using this repository as the base, we have implemented our **proposed Mixup-based method for time series forecasting**.

Our method is designed to be **model-agnostic** and can be applied across different **neural-based Transformer architectures** such as:

- Transformer  
- Informer  
- Autoformer  
- FEDformer  
- and others supported in the base code.

## Running Our Method

All experiments and evaluations can be run using the provided script:

```bash
bash run.sh
```

This script contains the full configuration for running our proposed Mixup approach on multiple models and datasets.

## Datasets

We evaluate on seven commonly used real-world datasets:

- Illness  
- Exchange  
- ECL  
- ETTh1  
- ETTh2  
- Weather  
- Traffic  

The datasets are provided in the `academic_data.zip` file. Please extract it to the root directory so that the data is available under `../academic_data/`.

## Acknowledgment

We gratefully acknowledge the original authors of ForecastPFN for their excellent open-source code, which forms the foundation of this repository.

> Tobias Domhan, Aaron Klein, Frank Hutter. **Forecasting Time Series with Learned Neural Representation Optimizers**.  
> In *International Conference on Learning Representations (ICLR)*, 2024.  
> GitHub: [https://github.com/automl/ForecastPFN](https://github.com/abacusai/ForecastPFN)
