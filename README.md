# 📈 Quant - Unsupervised Machine Learning Trading Strategy

An **algorithmic trading** project developed in Python within a Jupyter Notebook. This project implements a complete quantitative strategy that utilizes **K-Means Clustering**, an **unsupervised learning** technique, to group financial assets based on their market and fundamental characteristics. The strategy builds and optimizes portfolios monthly, comparing its performance against the market benchmark (S&P 500).

---

## ✨ Key Features

- 🤖 **Unsupervised Clustering**: Leverages the **K-Means** algorithm to identify groups of assets with similar behaviors and characteristics.
- 📊 **Complete Data Pipeline**: Downloads and processes S&P 500 price data from **yfinance**.
- 📈 **Feature Engineering**:
  - Calculates key technical indicators: **RSI**, **Bollinger Bands**, **ATR**, **MACD**.
  - Estimates **Garman-Klass Volatility**.
  - Computes returns across multiple time horizons (1, 2, 3, 6, 9, 12 months).
- 📉 **Risk Factors**: Downloads and calculates **Fama-French 5-factor Betas** using rolling linear regressions (`RollingOLS`).
- 💧 **Liquidity Filtering**: Monthly selects the **top 150 most liquid stocks** based on their dollar volume.
- 💰 **Portfolio Optimization**: For the selected cluster, it constructs the optimal portfolio by seeking to maximize the **Sharpe Ratio** using the `PyPortfolioOpt` library.
- 📊 **Result Visualization**: Compares the resulting strategy's performance against the **S&P 500** index with evolution charts.

---

## 🧰 Technology Stack

| Category                 | Technologies / Libraries                                       |
| ------------------------ | -------------------------------------------------------------- |
| **Language**             | Python                                                         |
| **Environment**          | Jupyter Notebook (`.ipynb`)                                    |
| **Data Manipulation**    | `pandas`, `numpy`                                              |
| **Financial Data**       | `yfinance` (prices), `pandas-datareader` (Fama-French factors) |
| **Machine Learning**     | `scikit-learn` (K-Means)                                       |
| **Statistics**           | `statsmodels` (RollingOLS)                                     |
| **Optimization**         | `PyPortfolioOpt` (Portfolio Optimization)                      |
| **Visualization**        | `matplotlib`                                                   |
| **Technical Indicators** | `pandas-ta`                                                    |

---

## 🛠️ Getting Started

Follow these steps to clone the repository and run the project on your local machine.

### 📋 Prerequisites

- Python 3.8 or higher.
- `pip` (the Python package installer).
- Recommendation: Use a virtual environment (`venv` or `conda`).

### 🔧 Installation

1.  **Clone the repository**

    ```bash
    git clone [https://github.com/your-username/your-quant-repo.git](https://github.com/your-username/your-quant-repo.git)
    cd your-quant-repo
    ```

2.  **Create and activate a virtual environment (optional but recommended)**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Linux/Mac
    # .\venv\Scripts\activate  # On Windows
    ```

3.  **Install the required dependencies**
    You can install them manually with `pip`. The main ones are:
    ```bash
    pip install pandas numpy matplotlib statsmodels pandas-datareader yfinance pandas-ta scikit-learn PyPortfolioOpt
    ```
    _(If a `requirements.txt` file is included, use `pip install -r requirements.txt`)_.

### ▶️ Running the Project

1.  Open the notebook file:

    ```bash
    jupyter notebook Algorithmic_Trading_Machine_Learning_Quant_Strategies.ipynb
    ```

2.  Execute the cells sequentially to reproduce the entire analysis and strategy.

---

## 🧪 Project Workflow

1.  **Data Acquisition**: Downloads S&P 500 stock price data.
2.  **Feature Engineering**: Calculates technical indicators and aggregates data to a monthly level.
3.  **Asset Selection**: Filters the top 150 most liquid stocks per month.
4.  **Return Calculation**: Computes historical returns for different periods.
5.  **Beta Calculation**: Downloads Fama-French factors and calculates rolling betas for each stock.
6.  **Clustering**: Applies K-Means to group the stocks into 4 clusters each month.
7.  **Portfolio Selection & Optimization**: Selects one cluster (e.g., the one with the best historical performance) and calculates the maximum Sharpe Ratio portfolio.
8.  **Backtesting**: Simulates the portfolio's performance over time and compares it against the S&P 500.
