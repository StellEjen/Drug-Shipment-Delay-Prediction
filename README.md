# Drug-Shipment-Delay-Prediction
# 🚚 Drug Shipment Delay Prediction & SLA Optimization

This project builds a predictive model to identify drug shipments at risk of delay, enabling proactive interventions and SLA compliance in healthcare logistics. It incorporates machine learning, threshold tuning, and business intelligence outputs suitable for deployment or dashboarding in Power BI.

---

## 📌 Project Objective

To predict **delayed drug shipments** using pre-dispatch information (region, carrier, day, schedule), and enable:

- 📊 SLA performance tracking
- 🧠 High-risk shipment flagging
- ✅ Data-driven operational decisions

---

## 🧪 Dataset Overview

Simulated dataset (`drug_shipment_delays.csv`) with ~4000 rows and 10+ features:

- `region`, `carrier`, `ship_day`
- `scheduled_days`, `actual_days`, `delay_duration`
- `delayed` (target: 1 if delayed, 0 if on-time)

---

## 🧠 Key Steps & Methodology

### 1. **Data Preprocessing**
- Removed leakage features (`actual_days`, `delay_duration`)
- One-hot encoded categorical columns
- Scaled numerical features (for logistic regression)

### 2. **Modeling**
- Logistic Regression and Random Forest
- Tuned using `RandomizedSearchCV` for **max recall**
- Evaluated on test set using `classification_report`

### 3. **Threshold Optimization**
- Precision-Recall curve plotted
- Selected threshold = `0.3` to maximize recall
- Custom predictions generated using `predict_proba`

### 4. **Risk Flagging & Group Insights**
- Flagged high-risk shipments (logistic regression)
- Grouped delay rates by `region × carrier`
- Merged historical and predicted risks for dashboard use

---

## 📈 Dashboard-Ready Outputs

Exported:
- `high_risk_shipments_flagged.csv` — shipment-level risk
- `sla_risk_dashboard.csv` — region × carrier risk + SLA targets

**Visual mockup includes:**
- Heatmap of predicted delay risk by region & carrier
- SLA compliance gauge
- Shipment-level flags for proactive decisions

---

## 💡 Recommendations

- Proactively route or escalate shipments flagged ≥0.3 risk
- Focus on underperforming regions & carriers
- Reevaluate SLAs using model + historical risk side by side

---

## 🔧 Tech Stack

- Python (pandas, scikit-learn, seaborn, matplotlib)
- Power BI / Tableau (for dashboard visualization)
- Git & GitHub (version control)

---

## 📁 Project Structure


---

## 📣 Author

**Stella O. Ejenavi**  
Data Scientist | Healthcare & Operations Optimization  
📧 [LinkedIn](www.linkedin.com/in/stella-o-e-2a30b7195) · 🧠 Passionate about applying ML for decision intelligence

---

## 📜 License

This project is open-sourced for educational and demonstration purposes.
