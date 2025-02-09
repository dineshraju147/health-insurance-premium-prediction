# Predictive Health Insurance Model for Shield Insurance

## Project Overview

AtliQ AI is developing a **predictive model** for **Shield Insurance** to estimate **health insurance premiums**. This model is designed to assist underwriters by predicting premiums based on factors such as age, smoking habits, BMI, and medical history.

### Phases of the Project
1. **Phase 1 (MVP):**
   - Develop and deploy a predictive model with a **Streamlit application**.
   - Achieve a model accuracy of >97%, with 95% of the errors within a 10% margin.
   
2. **Phase 2:**
   - Develop infrastructure for **straight-through processing (STP)** of insurance quotes.

---

## Project Approach

### Initial Model Development:
The project began with data cleaning, feature engineering, and initial model training using **XGBoost**, which achieved an impressive **R² score of 98%**. However, after performing error analysis, it was found that the model exhibited significant error margins (ranging from -25% to +80%).

### Error Analysis & Insights:
Upon further analysis, it was identified that the **age feature** was the primary source of errors. The **under 25 age group** had the highest error rate, which prompted the decision to **segregate the model into two segments**:
- **Model A** for individuals aged ≤25
- **Model B** for individuals aged >25

#### Model A (Young Age Group):
- In **ml_premium_health_insurance_prediction_young**, the model was trained on individuals under 25, but additional features such as **genetic factors** were found to be critical for improving the model's accuracy. Therefore, **Model A** was retrained with this additional feature in **ml_premium_health_insurance_prediction_young_with_gr**.
- This version of the model performed significantly better after including the **genetic factor**.

#### Model B (Age >25):
- The **ml_premium_health_insurance_prediction_rest_with_gr** notebook is dedicated to individuals aged over 25, and it was also trained with **genetic factor** data (if available).

---

## Future Improvements

To enhance the model further, the following **potential features** could be considered if the necessary data becomes available:
1. **Genetic Factor** (Already included)
2. **Lifestyle Factors**
3. **Past Insurance Claims**

Including these additional features, particularly **lifestyle factors** and **past insurance claims**, could improve model performance and provide a more comprehensive risk profile.

---

## Project Details

### Scope of Work:
- **Phase 1:**
  - Data Collection and Preprocessing
  - Model Development
  - Model Deployment
  - Streamlit Application Development
  - Testing, Validation, Documentation, and Training
  
- **Phase 2:**
  - Development of infrastructure for straight-through processing (STP) of insurance quotes.

---

## Conclusion

By segmenting the model based on age and incorporating critical features such as **genetic factors**, the model's performance has significantly improved. Future work will focus on integrating additional data features to further optimize predictions for health insurance premiums.

---
## Try the Application

You can interact with the **Streamlit application** for predicting health insurance premiums by clicking the link below:

[**Check out the Health Premium Prediction Application**](#)  <!-- Replace "#" with the actual link to the Streamlit app -->

## How to Use

1. Clone this repository.
2. Install required dependencies (e.g., via `requirements.txt`).
3. Run the Jupyter notebooks to see the model development and training process.
4. Deploy the model using Streamlit for interactive premium predictions.

