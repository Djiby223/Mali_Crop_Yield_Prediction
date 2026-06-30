# Mali_Crop_Yield_Prediction
This project builds a machine learning model to predict cereal crop yield in Mali using real agricultural statistics from FAOSTAT and climate indicators such as rainfall and drought conditions. The goal is to demonstrate how climate variability impacts agricultural productivity and to build a reproducible AI pipeline for agricultural forecasting.

Objectives
•	Clean and process FAOSTAT agricultural yield data 
•	Integrate climate data (rainfall + SPI) 
•	Build a supervised machine learning model 
•	Predict crop yield using climate indicators 
•	Evaluate model performance using regression metrics 
________________________________________
📊 Datasets Used
1. FAOSTAT Agricultural Data
Source: FAOSTAT (Food and Agriculture Organization)
•	Area: Mali 
•	Item: Cereals, primary 
•	Variable used: Yield 
•	Time range: ~1961–2024 
📄 File:
FAOSTAT_data_en_6-28-2026.csv
________________________________________
2. Climate Data (SPI + Rainfall)
•	Annual rainfall (mm) 
•	Standardized Precipitation Index (SPI) 
📄 File:
mali_spi_results(2).csv
________________________________________
🧹 Data Processing Workflow
Step 1: FAOSTAT Cleaning
•	Removed irrelevant columns 
•	Filtered Element = Yield 
•	Renamed target column to yield_t_ha 
•	Kept only cereals data 
Step 2: Climate Aggregation
•	Converted monthly SPI to yearly values 
•	Aggregated rainfall and SPI by year: 
o	Annual rainfall mean 
o	Annual SPI mean 
Step 3: Data Merge
Merged datasets on:
Year
Final dataset:
mali_crop_yield_climate_merged.csv
________________________________________
📦 Final Dataset Structure
Year	yield_t_ha	annual_rainfall_mm	annual_spi
1981	837.9	90.48	-0.146
1982	785.0	86.00	0.035
________________________________________
🤖 Machine Learning Model
Model Used
•	Random Forest Regressor (scikit-learn) 
Features (X)
•	annual_rainfall_mm 
•	annual_spi 
Target (y)
•	yield_t_ha 
________________________________________
⚙️ Model Pipeline
1.	Train/test split (80/20) 
2.	Model training 
3.	Prediction 
4.	Evaluation 
________________________________________
📈 Evaluation Metrics
The model is evaluated using:
•	MAE (Mean Absolute Error) 
•	RMSE (Root Mean Squared Error) 
•	R² Score 
________________________________________
🌳 Feature Importance
The model analyzes which climate variable affects yield most:
•	Rainfall contribution 
•	SPI (drought index) contribution 
________________________________________
📊 Results Interpretation
•	Higher R² → better predictive performance 
•	MAE → average prediction error in yield units 
•	RMSE → sensitivity to large errors 
________________________________________
🧠 Key Insights
•	Climate variability strongly affects cereal yield in Mali 
•	SPI (drought index) is a critical predictor 
•	Rainfall alone is not sufficient; combined indicators improve prediction 
•	FAOSTAT real data significantly improves model reliability 
________________________________________
📁 Project Structure
mali-crop-yield-prediction/
│
├── data/
│   ├── FAOSTAT_data_en_6-28-2026.csv
│   ├── mali_spi_results.csv
│   └── mali_crop_yield_climate_merged.csv
│
├── notebooks/
│   └── 01_data_cleaning_and_model.ipynb
│
├── src/
│   ├── data_cleaning.py
│   ├── feature_engineering.py
│   └── model_training.py
│
├── models/
│   └── random_forest_model.pkl
│
├── figures/
│   └── feature_importance.png
│
├── README.md
└── requirements.txt
________________________________________
🧪 How to Run the Project
1. Clone repository
git clone https://github.com/djiby223/mali-crop-yield-prediction.git
cd mali-crop-yield-prediction
________________________________________
2. Install dependencies
pip install -r requirements.txt
________________________________________
3. Run training script
python src/model_training.py
________________________________________
📦 Requirements
pandas
numpy
scikit-learn
matplotlib
seaborn
________________________________________
📊 Future Improvements
•	Add NDVI and VCI vegetation indices 
•	Use XGBoost / LightGBM models 
•	Move from national to regional yield modeling 
•	Build a Streamlit dashboard for predictions 
•	Add weather forecasting integration 
________________________________________
👨‍💻 Author
Adama D. Savane
AI & Data Science Practitioner (Agriculture & Climate Focus)
________________________________________
⭐ Project Value
This project demonstrates:
•	Real-world agricultural AI application 
•	Climate impact modeling 
•	End-to-end machine learning pipeline 
•	FAOSTAT + remote sensing data integration 
