# 🏦 Loan Eligibility Predictor - Streamlit App

This Streamlit application predicts whether a loan applicant is eligible for approval based on financial and personal data. It uses a trained Logistic Regression model and is designed to work interactively in Google Colab.

---

## 🚀 Live App

🔗 **Streamlit App URL**: [https://5944-34-133-131-12.ngrok-free.app](https://5944-34-133-131-12.ngrok-free.app)

> *Hosted using ngrok from Google Colab. The URL may change each time the Colab session restarts.*

---

## 📦 Features

- User-friendly input form for applicant details
- Real-time eligibility prediction
- Displays model’s confidence in rejection
- Runs fully from a Google Colab notebook

---

## 🛠 How to Run in Google Colab

1. **Train your model and save it**:

```python
import joblib
joblib.dump(model, "model.pkl")
joblib.dump(scaler, "scaler.pkl")
joblib.dump(X.columns.tolist(), "columns.pkl")
```

2. **Create the Streamlit app file**:

```python
%%writefile app.py
# (Insert the Streamlit code here — from app.py)
```

3. **Install Streamlit and pyngrok**:

```python
!pip install streamlit pyngrok --quiet
```

4. **Launch the app**:

```python
!streamlit run app.py &> /dev/null &
```

5. **Expose it with ngrok**:

```python
from pyngrok import ngrok
public_url = ngrok.connect(8501)
print(f"App is live at: {public_url}")
```

## 📊 Model Details
Algorithm: Logistic Regression
Trained On: Loan application data
Features Used:
- Annual Income
- CIBIL Score
- Loan Amount
- Loan Term
- Number of Dependents
- Education Level
- Self Employment Status
- Various Asset Values (residential, commercial, luxury, bank)
  
## ✅ Prediction Output
Result: "Approved" or "Rejected"

Confidence of Rejection:
- This is the model's probability that the applicant should be rejected.
- Example: Confidence = 87% → Model is 87% confident this is a risky applicant.
  
## 📎 Notes
- This app is intended for educational or demo purposes only.
- For production deployment:
  - Use secure ngrok authentication
  - Protect user data
  - Store model files securely
- App link will reset if Colab runtime is disconnected.
