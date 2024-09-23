# Stock Price Prediction Using K-Nearest Neighbors (KNN)

### Description
This project aims to predict the movement of stock prices using a supervised machine learning algorithm, K-Nearest Neighbors (KNN). By analyzing features derived from historical stock data, such as the difference between opening and closing prices and the high-low price spread, the model attempts to classify whether the stock price will increase or decrease the following day.

---

## Table of Contents
- [Description](#description)
- [Features](#features)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Model Selection](#model-selection)
- [Results](#results)
- [Future Improvements](#future-improvements)

---

## Features
- **Open-Close Difference**: The difference between the opening and closing prices.
- **High-Low Difference**: The range between the highest and lowest prices on a given day.
- **Price Movement Prediction**: The model predicts whether the stock price will increase (Buy) or decrease (Sell) on the next day.

---

## Dataset
The project uses historical stock market data from the **NSE-TATAGLOBAL** dataset. This dataset includes the following key features:
- `Date`: Date of the trading session.
- `Open`: Opening price.
- `Close`: Closing price.
- `High`: Highest price during the session.
- `Low`: Lowest price during the session.
  
You can download or use your own dataset by placing it in the `sample_data/` folder.

---

## Project Structure
```
├── sample_data/
│   └── NSE-TATAGLOBAL.csv   # The stock data used in the project
├── stock_price_prediction.py # The main Python script
├── README.md                # Project documentation (this file)
└── requirements.txt         # Required Python packages
```

---

## Installation
To run this project locally, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/priyammanna13/stock-prediction.git

2. **Install required Python packages**:
   Make sure you have `pip` installed. Then run:
   ```bash
   pip install -r requirements.txt
   ```

3. **Install additional dependencies** (if needed):
   If you're running the code in a fresh environment, you might need to install `scikit-learn`:
   ```bash
   pip install scikit-learn
   ```

---

## Usage
1. **Prepare the Data**: 
   The data is preprocessed by calculating two new features:
   - **Open-Close Difference** (`open-close`): The difference between the opening and closing prices.
   - **High-Low Difference** (`high-low`): The spread between the highest and lowest prices.
   
2. **Train the Model**:
   Use the K-Nearest Neighbors (KNN) algorithm to classify the stock's future price movement:
   ```bash
   python stock_price_prediction.py
   ```

3. **Evaluate the Model**:
   The model is evaluated based on its prediction accuracy on both training and testing data. The best number of neighbors is chosen using GridSearchCV.

4. **Visualization**:
   The project includes graphical plots for visualizing stock prices over time and the accuracy of predictions using bar charts.

---

## Model Selection
We use the K-Nearest Neighbors (KNN) algorithm, tuned via GridSearchCV. Key model selection points:
- **Parameters**: The model checks `n_neighbors` values from 2 to 15 to find the optimal number of neighbors.
- **Cross-Validation**: The GridSearchCV is set to `cv=5` to ensure robustness of parameter tuning.

---

## Results
The model's performance is evaluated based on **accuracy**:
- **Training Accuracy**: `accuracy_train` is computed to check how well the model fits the training data.
- **Testing Accuracy**: `accuracy_test` is used to determine how well the model generalizes to unseen data.

Results are displayed via:
- **Bar Chart**: Visual representation of actual vs. predicted values.
  
Sample output:
```bash
Accuracy of train data: 0.8859764089121888
Accuracy of test data:  0.8546168958742633
```

---

## Future Improvements
- **Feature Engineering**: Incorporating more features such as volume, moving averages, and technical indicators.
- **Advanced Models**: Testing other models like Random Forest, SVM, or Neural Networks to compare performance.
- **Hyperparameter Tuning**: Expanding the search for other hyperparameters, including different distance metrics for KNN.

---

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
