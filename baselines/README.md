

# Baseline Evaluation

This directory is for **evaluating Baselines** as part of our experiments on time series forecasting. We have adopted and integrated the [ForecastPFN](https://github.com/automl/ForecastPFN) codebase within our repository, and it include evaluation on **seven real-world datasets** commonly used in literature. These include:

* Illness
* Exchange
* ECL
* ETTh1
* ETTh2
* Weather
* Traffic

The data required for these evaluations is provided in the compressed file: `academic_data.zip`. Please extract this zip file into the root directory so that the datasets are available at `../academic_data`.

## Running Code

To evaluate Baseline models and ForecastPFN on a dataset (e.g., **Illness**), use the following command:

```bash
# illness
python run.py \
 --is_training 0 \
 --data ili \
 --root_path ../academic_data/illness/ \
 --data_path national_illness.csv \
 --model ForecastPFN \
 --seq_len 36 \
 --label_len 18 \
 --pred_len 14 \
 --train_budget 50 \
 --itr 5
```

### Arguments

* `is_training`: Set to `0` for zero-shot models like ForecastPFN and Metalearn. Set to `1` for trainable models like ARIMA, Transformer, etc.
* `data`: Dataset identifier. See `benchmark/data_provider/data_factory.py` for supported values.
* `root_path`: Path to the folder containing the dataset file.
* `data_path`: Filename of the CSV file containing the dataset.
* `model`: One of `ForecastPFN`, `Metalearn`, `ARIMA`, `Autoformer`, `Informer`, `Transformer`, `FEDformer-w`, `Prophet`, etc.
* `seq_len`: Input sequence length. (Typically `36`, or `96` for Exchange.)
* `label_len`: Label length used internally for forecasting. (Usually `18`, or `48` for Exchange.)
* `pred_len`: Prediction horizon.
* `train_budget`: Number of training samples available. `0` for zero-shot models like ForecastPFN.
* `itr`: Number of repetitions to average out randomness in model runs.

## Baselines Evaluated

The model has been benchmarked against the following baselines:

* Statistical: `ARIMA`, `Prophet`
* Neural: `Informer`, `FEDformer-w`, `Autoformer`, `Transformer`
* Zero-shot: `ForecastPFN`, `Metalearn`
* Simple heuristics: `Mean`, `Last`, `NaiveSeasonal`

All experiment configurations used in our paper can be found in `run.sh`. 

## Reference

We gratefully acknowledge the authors of ForecastPFN for their codebase, which we use as the foundation of our evaluation setup. If you use this code or our results in your work, please cite their original paper:

> Tobias Domhan, Aaron Klein, Frank Hutter. **Forecasting Time Series with Learned Neural Representation Optimizers**. In *International Conference on Learning Representations (ICLR)*, 2024.
> GitHub: [https://github.com/automl/ForecastPFN](https://github.com/automl/ForecastPFN)


