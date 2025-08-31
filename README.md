# 🏡 King County House Price Prediction (2014–2015)

Exploring housing market dynamics in King County (Seattle area) by analyzing property features and predicting sale prices using Machine Learning models.  

---

## 📊 Dataset Description
**Source:** King County house sales dataset (2014–2015)  
**Size:** ~21,000 records, 21 features  

**Key Variables:**
- `id` — Unique house identifier  
- `date` — Sale date  
- `price` — Sale price (**target variable**)  
- `bedrooms` — Number of bedrooms  
- `bathrooms` — Number of bathrooms (per bedroom basis)  
- `sqft_living` — Interior living space (sq. ft.)  
- `sqft_lot` — Land space (sq. ft.)  
- `floors` — Number of floors  
- `waterfront` — Whether house has waterfront view  
- `view` — View rating  
- `condition` — Overall house condition  
- `grade` — King County grading system  
- `sqft_above` — Sq. ft. above basement  
- `sqft_basement` — Basement area (sq. ft.)  
- `yr_built` — Year built  
- `yr_renovated` — Year renovated  
- `zipcode` — ZIP code  
- `lat` / `long` — Coordinates  
- `sqft_living15` — Living space of nearest 15 neighbors (2015)  
- `sqft_lot15` — Lot size of nearest 15 neighbors (2015)  

**Target →** `price`  
- Primary focus: Identify which features most strongly impact house prices.  
- Additional focus: Houses valued at **$650K+** for premium property insights.  

---

## 🎯 Research Goals
- Which features most influence house sale prices?  
- How accurately can we predict house prices with ML models?  
- What differences emerge when analyzing premium homes ($650K+)?  

---

## 🔍 Methodology

### 1. Data Cleaning
- Standardized column names  
- Fixed data types  
- Handled missing values  
- Removed extreme outliers  

### 2. Exploratory Data Analysis (EDA)
- Price distribution, feature correlations, and outlier detection  
- Heatmaps, bar plots, scatter plots for feature relationships  
- Segmentation of premium vs non-premium houses  

### 3. Modeling & Evaluation
- **Baseline Models:** Linear, Ridge, Lasso, KNN, Decision Tree, Ensemble Methods  
- **Feature Engineering:** Scaling, transformations, categorical encoding  
- **Model Comparison:** XGBoost, Random Forest, Gradient Boosting performed best  
- **Metrics Used:** R² (Train/Test), RMSE  

---

## 📌 Key Findings
- **Top drivers:** `grade`, `sqft_living`, location (`lat`, `long`, `zipcode`)  
- **Model performance:**
  - Ensemble methods (XGBoost, Random Forest, Gradient Boosting) achieved highest predictive power  
  - Linear/Ridge/Lasso models showed better generalization after feature engineering  
  - AdaBoost and Decision Tree underperformed (underfitting/overfitting issues)  
- **Premium homes ($650K+):** Stronger influence from `waterfront`, `view`, and `location`  

---

## ⚙️ How to Reproduce

### Prerequisites
- Python **3.9+**  
- `pip` and `virtualenv`/`venv` recommended  

### Setup
```bash
# Clone repository
git clone https://github.com/yourusername/kingcounty-houseprices.git
cd kingcounty-houseprices

# Create virtual environment
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

## ▶️ Run Analysis
1. Open **`EDA_house_prices.ipynb`** in Jupyter Notebook or JupyterLab  
2. Execute all cells to reproduce results  
3. Visualizations are saved in `figures/`  

---

## 🚀 Next Steps
- Hyperparameter tuning for XGBoost and Random Forest (already partially explored)  
- Build a production-ready price prediction API  
- Incorporate time-series trends (seasonality of sales)  
- Expand dataset with external features (schools, crime rates, economic indicators)  

