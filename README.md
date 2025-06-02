# Income Classifier API – Predict Income Bracket with a Trained ML Model

## 📌 Project Description
This project serves a trained machine learning model that predicts whether a person earns more than $50K per year based on U.S. Census-style input data. It includes:
- Data preprocessing and feature engineering
- Model training with Logistic Regression, Random Forest, and XGBoost
- Imbalance handling with SMOTE
- REST API deployment using Flask
- End-to-end prediction demo with JSON payloads

## 📁 Project Structure

```
income_classifier_api/
├── app.py                  # Flask API script
├── income_model.pkl        # Trained machine learning model
├── model_features.pkl      # Feature names used during training
├── requirements.txt        # Python dependencies
├── test_payload.json       # Example payload for testing the API
├── Procfile                # Deployment config (e.g., for Render)
├── .gitignore              # Excludes virtual envs and cache files
├── deployment_guide.docx   # Student-friendly setup walkthrough
├── README.md               # This file
└── model_building.ipynb    # Full Jupyter Notebook for data cleaning, EDA, model training
```

## 🚀 How to Run Locally

### 1. Clone this repository
```bash
git clone https://github.com/YOUR_USERNAME/income-classifier-api.git
cd income-classifier-api
```

### 2. Create and activate virtual environment
```bash
python -m venv venv_income_api
venv_income_api\Scripts\activate  # On Windows
# OR
source venv_income_api/bin/activate  # On Mac/Linux
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Flask app
```bash
python app.py
```

## 🧪 How to Test the API

Once the server is running locally, test using `curl` or Postman:

```bash
curl -X POST http://127.0.0.1:5000/predict \
-H "Content-Type: application/json" \
-d @test_payload.json
```

You’ll get a response like:
```json
{ "prediction": ">50K" }
```

## 🧰 Notes and Resources

- **Notebook included:** `model_building.ipynb` shows EDA, SMOTE, model training, and cross-validation
- **Includes Flask deployment code** and guidance for hosting on [Render](https://render.com)
- Virtual environments are excluded via `.gitignore`
- Compatible with Python 3.8+  
- Based on the [UCI Adult Income dataset](https://archive.ics.uci.edu/dataset/2/adult)

## 📚 Related Skills Covered

- Data preprocessing and encoding
- Handling imbalanced data with SMOTE
- Stratified K-Fold CV and Grid Search
- Deployment-ready Python APIs
- Feature importance and model evaluation (ROC AUC = 0.86)
