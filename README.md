# Classical machine learning models to predict TE

**Predicting the translation efficiency of messenger RNA in mammalian cells**\
Dinghai Zheng, Logan Persyn, Jun Wang, Yue Liu, Fernando Ulloa Montoya, Can Cenik, Vikram Agarwal\
bioRxiv 2024.08.11.607362; doi: [https://doi.org/10.1101/2024.08.11.607362](https://doi.org/10.1101/2024.08.11.607362)


## Environemnt Setup
1. Create conda environment: \
`conda env create -f environment.yml --prefix ./TE_classic_ML_env/`
1. Activate conda environment:\
`conda activate ./TE_clasic_ML_env`

## Data
Training data is already provided in `./data/`.

If generating training data yourself:
- Place/symlink `appris_human_v2_selected.fa` and `appris_mouse_v2_selected.fa` in `./data/`.
- Place/symlink `human_all_biochem_feature_no_len.csv` in `./biochem_and_struct_data` if training with biochem data.

## Training
Training examples can be found in `experiments.py`. Use `-e human_all_no_struct` argument to train all human models (save models with `-s` flag).

## Predicting
Predict with `predict.py`. Example inputs and outputs can be found in `./examples`. Full command example: \
 `python .\predict.py --model_dir ./results/human/all_cell_lines/lgbm-LL_P5_P3_CF_AAF_3mer_freq_5/ --data_path ./examples/predict_input_example.csv --output_path ./examples/predict_output_example.csv`

