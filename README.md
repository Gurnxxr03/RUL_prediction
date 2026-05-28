# 🔧 Turbofan Engine Remaining Useful Life (RUL) Prediction using LSTM

## 📌 Overview

This project focuses on predicting the **Remaining Useful Life (RUL)** of turbofan engines using deep learning techniques. By leveraging time-series sensor data, we train an **LSTM-based neural network** to model degradation patterns and estimate how many cycles an engine can continue to operate before failure.

The project uses the **NASA CMAPSS dataset**, a widely used benchmark for predictive maintenance and prognostics.

---

## ⚙️ Key Features

* 📊 Time-series preprocessing with sliding window approach
* 🔍 Feature selection (removal of constant sensors)
* 📉 RUL labeling with piecewise linear degradation (clipped at 125 cycles)
* 🧠 Deep learning model using stacked LSTM layers
* 📏 Evaluation using regression metrics (MAE, MSE, R²)
* 📈 Visualization of training performance

---

## 🧠 Model Architecture

* LSTM Layer (128 units, return sequences)
* Dropout (0.2)
* LSTM Layer (64 units)
* Dropout (0.2)
* Dense Layer (32 units, ReLU)
* Output Layer (1 unit, Linear)

**Loss Function:** Huber Loss
**Optimizer:** Adam (learning rate = 0.001)

---

## 📂 Dataset

* Source: NASA CMAPSS Turbofan Engine Degradation Dataset
* Subset used: `FD001`
* Contains multiple engine units with sensor readings over time

---

## 🔄 Data Processing Pipeline

1. Load dataset from Google Drive
2. Assign column names (settings + sensor values)
3. Compute RUL:

   * `RUL = max_cycle - current_cycle`
4. Clip RUL values at 125 for stability
5. Normalize features using MinMaxScaler
6. Generate sequences using sliding window (length = 50)

---

## 🧪 Training

* Train-validation split: 80-20
* Early stopping applied to prevent overfitting
* Model trained for up to 60 epochs

---

## 📊 Results

* Significant drop in MAE after initial epochs
* Model successfully learns degradation patterns
* Achieved strong predictive performance on validation data

---

## 🛠️ Tech Stack

* Python
* TensorFlow / Keras
* NumPy, Pandas
* Scikit-learn
* Matplotlib, Seaborn

---

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the notebook

Open the notebook in Google Colab or Jupyter:

```bash
jupyter notebook
```

---

## 📌 Future Improvements

* 🚀 Experiment with GRU / Transformer architectures
* 📊 Hyperparameter tuning
* 🧠 Add attention mechanisms
* 🌐 Deploy as a real-time predictive maintenance system

---

## 🤝 Contributing

Feel free to fork this repository, open issues, and submit pull requests.

---

## 📜 License

This project is open-source and available under the MIT License.

---

## 👨‍💻 Author

**Gurnoor Singh Brar**

---

## ⭐ If you found this useful

Give this repo a star ⭐ and share it!
