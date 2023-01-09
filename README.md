# London Airbnb Prediction ML Model


## Download and store the raw data
Download the data by running `src/data_wrangling/pull_data.py`:\
    `--file_path` should be the path where the data will be saved,\
    `--url` should be the link to the data

    python src/data_wrangling/pull_data.py --file_path="data/raw/raw_df.csv" --url="http://data.insideairbnb.com/united-kingdom/england/london/2022-09-10/data/listings.csv.gz"

## Clean the raw data frame to remove unnecessary columns
Download the data by running `src/data_wrangling/clean_data.py`:\
    `--output_file_path` should be the path where the clean data will be saved,\
    `--input_file_path` should be the path where the raw data is stored

    python src/data_wrangling/clean_data.py --output_file_path="data/raw/clean_df.csv" --input_file_path="data/raw/raw_df.csv"

## Preprocess the cleaned to prepare it for the model building
Download the data by running `src/data_wrangling/preprocessing.py`:\
    `--output_file_path` should be the path where the clean data will be saved,\
    `--input_file_path` should be the path where the raw data is stored

    python src/data_wrangling/preprocessing.py --output_file_path="data/preprocessed/preprocessed_df.csv" --input_file_path="data/raw/clean_df.csv"

## Run the EDA analysis
Download the data by running `src/model_building/eda.py`:\
    `--output_dir`  Path to folder where the EDA results will be saved, `in quotes.\
    `--clean_df_file_path`  Path to folder and file name where the clean df is stored, including the name, `in quotes.\
    `--preprocessed_df_file_path`  Path to folder and file name where the preprocessed df is stored, including the name, `in quotes.

    python src/model_building/eda.py --output_dir="results/eda_plots" --clean_df_file_path="data/raw/clean_df.csv"  --preprocessed_df_file_path="data/preprocessed/preprocessed_df.csv"

## Run the feature engineering script
Download the data by running `src/model_building/feat_eng.py`:\
    `--output_file_path` should be the path where the file with new features will be saved,\
    `--input_file_path`  should be the path where the preprocessed data is stored.

    python src/model_building/feat_eng.py --output_file_path="data/preprocessed/feat_eng_df.csv" --input_file_path="data/preprocessed/preprocessed_df.csv"

## Run the linear models
Download the data by running `src/model_building/linear_models.py`:\
    `--output_dir`  Path to folder where the model results dictionary will be saved, `in quotes.\
    `--input_file_path`  Path to folder and file name where the preprocessed file with engineered features is stored, including the name, `in quotes.

    python src/model_building/linear_models.py --output_dir="results/model_results" --input_file_path="data/preprocessed/feat_eng_df.csv"

## Run the non linear models (ensembles)
Download the data by running `src/model_building/ensembles.py`:\
    `--output_dir`  Path to folder where the model results dictionary will be saved, `in quotes.\
    `--input_file_path`  Path to folder and file name where the preprocessed file with engineered features is stored, including the name, `in quotes.

    python src/model_building/ensembles.py --output_dir="results/model_results" --input_file_path="data/preprocessed/feat_eng_df.csv"

## Run the permutation feature importances analysis 
Download the data by running `src/model_building/perm_feat_importances.py`:\
    `--output_dir`  Path to folder where the model results dictionary will be saved, `in quotes.\
    `--input_file_path`  Path to folder and file name where the preprocessed file with engineered features is stored, including the name, `in quotes.

    python src/model_building/perm_feat_importances.py --output_dir="results/model_results" --input_file_path="data/preprocessed/feat_eng_df.csv"

## Run the SHAP analysis 
Download the data by running `src/model_building/shap_feat_importances.py`:\
    `--output_dir`  Path to folder where the model results dictionary will be saved, `in quotes.\
    `--input_file_path`  Path to folder and file name where the preprocessed file with engineered features is stored, including the name, `in quotes.

    python src/model_building/shap_feat_importances.py --output_dir="results/model_results" --input_file_path="data/preprocessed/feat_eng_df.csv"