# Airline Customer Satisfaction Prediction

## 📌 Project Overview
Passenger retention is a critical differentiator in the aviation industry. This project implements an end-to-end predictive machine learning pipeline using **Python** and **Scikit-learn** to analyze passenger survey data, build a **Binomial Logistic Regression** model, evaluate classifications, and isolate the operational touchpoints that structurally dictate positive or negative customer experiences.

Using a dataset of over 129,000 passenger survey records, the converged model achieves an overall **83% classification accuracy** on unseen test data. The project provides transparent, data-driven recommendations for corporate resource allocation.

## 🎯 Project Goals
- Perform data ingestion, cleaning, and multicollinearity mitigation.
- Encode categorical predictors (dummy variables, one-hot encoding) and scale numerical features.
- Build and refine a **Binomial Logistic Regression** model using `scikit-learn`.
- Validate classification performance using **Confusion Matrices**, **Precision**, **Recall**, and **F1-Scores**, moving beyond simple accuracy metrics.
- Interpret standardized model coefficients to identify key drivers of customer satisfaction.
- Translate statistical outputs into actionable, strategic business intelligence.

## 📊 Dataset
The dataset (`Invistico_Airline.csv`) contains 129,880 historical survey evaluations across 22 baseline operational, demographic, and flight-specific features. The target classification is highly balanced (approx. **54.7% Satisfied** and **45.3% Dissatisfied**).

- **Target Variable**: `satisfaction` (Satisfied vs. Dissatisfied)
- **Passenger Demographics & Travel Type**: `Customer Type`, `Age`, `Type of Travel`, `Class`, `Flight Distance`
- **Core Service Touchpoints (0-5 Scale)**: Pre-flight logistics (e.g., `Ease of Online booking`, `Online boarding`), Cabin comfort (`Seat comfort`, `Cleanliness`), On-board performance (`Inflight entertainment`, `Leg room service`)
- **Flight Delays**: `Departure Delay in Minutes` (Note: `Arrival Delay in Minutes` dropped due to high correlation with departure delays).

## 🛠️ Tools & Libraries
- **Python**: Primary programming language.
- **Jupyter Notebook**: Primary development environment.
- **Pandas**: Data manipulation and cleaning operations.
- **Matplotlib & Seaborn**: Data visualization and correlation analysis.
- **Scikit-learn**: Machine learning pipeline (preprocessing, model building, and evaluation).

## 🗂️ Repository Structure
```text
├── README.md                                  # Project Overview and Analytical Findings
├── Invistico_Airline.csv                      # Raw airline passenger survey dataset
├── logistic_regression_analysis.ipynb         # Analysis Notebook
```

## 💻 Environment Setup & Installation

To execute this analysis locally, follow these steps:

### Clone repository
> `git clone [Your Repository URL]`

### Install necessary libraries
> `pip install pandas numpy matplotlib seaborn scikit-learn jupyter`

### Start Jupyter
> `jupyter notebook`

This will open the Jupyter environment in your default browser. Navigate to `logistic_regression_analysis.ipynb` and run the cells sequentially to begin the analysis.

## 📈 Key Findings
1. **Model Performance**: The Logistic Regression model achieved an overall classification accuracy of **83%**.
2. **Balanced Evaluation**: The F1-scores for both 'Satisfied' and 'Dissatisfied' classes were highly balanced (> 0.80), demonstrating robust predictive capability without significant class bias.
3. **Primary Positive Drivers**:
   - **Inflight Entertainment (+0.973)** is the strongest statistical predictor of satisfaction. High-quality media ecosystems heavily offset other negative experiences.
   - **Ease of Online Booking (+0.332)** demonstrates that frictionless digital logistics before the flight significantly elevate overall satisfaction.
4. **Primary Structural Friction Points**:
   - **Eco Class (-0.354)** establishes a strong negative baseline compared to premium cabins.
   - **Personal Travel (-0.350)** indicates that leisure travelers paying out-of-pocket are fundamentally harder to satisfy than corporate travelers.
   - **Inconvenient Departure/Arrival Times (-0.326)** remain a significant driver of dissatisfaction.

## ⚠️ Model Limitations
This model operates under several structural limitations:
- **Assumption of Linearity**: Logistic Regression assumes a linear relationship between features and the log-odds of the target. It does not automatically capture non-linear behaviors or complex feature interactions.
- **Subjective Survey Scales**: The data relies on subjective ordinal ratings (0-5), where the threshold between scores can vary significantly based on individual passenger psychology.
- **Cross-Sectional Constraints**: The survey provides a snapshot in time and lacks temporal or macroeconomic contexts (e.g., holiday rushes vs. off-seasons).

## 💡 Strategic Recommendations
- **Modernize Inflight Entertainment (IFE)**: Given its dominant positive impact, allocate capital to upgrade screen hardware and expand content libraries; this yields the highest ROI for customer retention.
- **Optimize Digital Pre-Flight Logistics**: Streamline mobile app workflows and online booking processes. Reducing friction early in the customer journey creates a protective halo over the remainder of the flight experience.
- **Design Targeted Upgrades**: Since leisure travelers in economy seats are at high risk for dissatisfaction, implement automated upgrade logic or offer minor operational perks to this segment to structurally boost retention rates.
