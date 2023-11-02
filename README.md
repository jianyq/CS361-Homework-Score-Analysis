

# CS361-Homework-Score-Analysis


This project aims to predict students' midterm scores based on their homework scores using two different machine learning models: Linear Regression and Long Short-Term Memory (LSTM).

## Methods and Performances

### 1. Linear Regression

#### Description:
Linear Regression is a statistical method to model the relationship between a dependent variable and one or more independent variables. In this project, we used students' scores from Homework 1 to 10 (`HW1` to `HW10`) as independent variables to predict the `mid1` score.

#### Implementation:
- Data Cleaning: Handled NaN values by filling them with 0.
- Model: Used `LinearRegression` from `sklearn`.
- Evaluation Metrics: Mean Squared Error (MSE) and $R^{2}$ Score. Additionally, we calculated the accuracy within a range of ±12.5 points.

#### Performance:

- Accuracy: 0.5
- Mean Squared Error: 454.59267933162926
- $R^{2}$ Score: 0.18515071572160635

### 2. LSTM (Long Short-Term Memory) Networks

#### Description:
LSTM is a type of recurrent neural network (RNN) which is capable of learning long-term dependencies and is used for sequence prediction problems. Here, the sequence of homework scores is used to predict the midterm scores.

#### Implementation:
- Data Cleaning: Filled NaN values with 0.
- Model: Defined an LSTM model using `PyTorch`.
- Evaluation Metrics: Loss (MSE) and accuracy within a range of ±2.5 points were monitored during training.
- Special Handling: The model is saved every 1000 epochs.

#### Performance:

- on Training Set:
  - Best_Accuracy: 0.7289
  - Epoch: 80000
- on Validation Set:
  - Best_Accuracy: 0.9412
  - Epoch: 1000

## Datasets

The datasets consist of scores from 10 homework assignments (`HW1` to `HW10`) and a midterm (`mid1`) for a set of students, each identified by a unique `randNumCol`. 

### Data Cleaning:
- Entries with a `Total Score` less than or equal to 1 were removed.
- Cleaned data was saved as `HW{i}_clean.csv`.
- The data was merged on `randNumCol` to create a consolidated dataset `data_total.csv`.

## Special Enhancements

To improve the baseline models:
1. **Data Imputation**: NaN values were replaced with 0.
2. **Data Preprocessing**: Data was cleaned and only relevant features were kept.
3. **Model Saving**: For the LSTM model, the state was saved every 1000 epochs to monitor progress and potentially use transfer learning later.

## Conclusion

This project showcases two different approaches to predict midterm scores based on homework scores. By comparing the performances of Linear Regression and LSTM, we can gain insights into the predictability of the midterm scores and potentially improve the teaching strategies to assist students in better preparation.