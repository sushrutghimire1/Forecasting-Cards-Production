# Fiserv Card Production Forecast Model

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Made with Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange)](https://jupyter.org/)

Forecast daily card production across 676 job types using time series models. Built for Fiserv Output Solutions to optimize manufacturing.

## 📊 Data
- **File**: `All Time Series (1) (1).csv` (365 days, 2023).
- **Format**: Date index; 676 columns (`'JobType_001'` to `'_676'`); sparse NaN-filled counts.

## 🛠️ Setup
1. Clone: `git clone https://github.com/yourusername/fiserv-card-forecaster.git`
2. Env: `python -m venv venv && source venv/bin/activate`
3. Install: `pip install -r requirements.txt`
4. Run: `jupyter notebook Code_(1).ipynb`

**Requirements**: numpy, pandas, matplotlib, statsmodels, prophet, scikit-learn, xgboost, tqdm.

## 🔬 Models & Methods
- **EDA**: Decomposition, stationarity (ADF/KPSS), PACF.
- **Models**:
  - Holt-Winters (classical).
  - Prophet (baseline/tuned via GridSearchCV).
  - XGBoost (baseline/tuned via RandomizedSearchCV; features: lags, rolling stats).
- **Split**: 80/20 chronological.
- **Metrics**: RMSE, MAPE.

## 📈 Results
| Model                  | RMSE      | MAPE   |
|------------------------|-----------|--------|
| Holt-Winters          | 729K     | 248   |
| Baseline Prophet      | 633K     | 165   |
| Tuned Prophet         | 629K     | 168   |
| Baseline XGBoost      | 642K     | 99    |
| **Tuned XGBoost**     | **595K** | **114**|

Visuals in notebook (forecast vs. actual plots).

## 🚀 Next Steps
- Multi-step forecasts.
- Add regressors (holidays, supply).
- Ensemble models.
- Deploy via FastAPI.

## 🤝 Contribute
Fork, branch, PR. See [CONTRIBUTING.md](CONTRIBUTING.md).

## 📝 License
MIT. See [LICENSE](LICENSE).

**Author**: [Your Name] – [@yourhandle](https://x.com/yourhandle)  
Issues: [New Issue](https://github.com/yourusername/fiserv-card-forecaster/issues/new)
