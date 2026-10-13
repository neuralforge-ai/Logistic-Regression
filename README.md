# Logistic Regression with Gradio and Flask

This project applies **Logistic Regression** to two different UCI datasets and provides a web interface for each, built with both **Gradio** and **Flask**.

## Datasets

| Folder | Dataset | Goal |
|---|---|---|
| `bank_marketing/` | UCI Bank Marketing (`bank_full.csv`) | Predict whether a client subscribes to a term deposit |
| `breast_cancer/` | UCI Breast Cancer Wisconsin Diagnostic (`wdbc.data`) | Predict whether a tumor is malignant or benign |

## Files in each folder

- `train.py` - loads the data, preprocesses it, trains the Logistic Regression model, prints the evaluation, and saves the model
- `gradio_app.py` - Gradio user interface
- `flask_app.py` - Flask user interface

## How to run

1. Install the requirements:
```
pip install pandas scikit-learn joblib gradio flask
```
2. Open a terminal inside a dataset folder, for example `bank_marketing`.
3. Train the model:
```
python train.py
```
4. Start one of the interfaces:
```
python gradio_app.py
```
or
```
python flask_app.py
```
5. Open the link shown in the terminal (Gradio: http://127.0.0.1:7860, Flask: http://127.0.0.1:5000).

Repeat the same steps in the `breast_cancer` folder.

## Method

- Preprocessing: numeric features are scaled with StandardScaler; categorical features are one-hot encoded (bank marketing).
- Model: scikit-learn `LogisticRegression`.
- Data is split 80% for training and 20% for testing.
- Bank Marketing uses balanced class weights because most clients answer "no".
- Breast Cancer uses the 10 "mean" features.

## Author
Amna Khalid
