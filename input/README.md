# Input Data Guide for Personalized Recommendation

This directory contains the template file `new_subject_input_template.xlsx` used for generating personalized carbohydrate (CHO) and protein (PRO) intake recommendations for new subjects.

## How to Use

1.  **Open Template:** Open `new_subject_input_template.xlsx`.
2.  **Input Data:** Fill in the physiological and anthropometric data for the new subject(s). Each row represents one subject.
3.  **Save:** Save the file (do not change the filename or extension).
4.  **Run Model:** Execute the prediction module in the `modeling/` directory. The script will read this file, simulate different CHO intake rates, and output the optimal strategy.

## ⚠️ Important Constraints

* **Do Not Change Column Order:** The XGBoost model relies on the specific order of columns. **Do not add, delete, or reorder any columns.**
* **Units Matter:** Ensure all input values strictly follow the units specified in the column headers (e.g., kg, cm, min).
* **Auto-Calculated Fields:** You do **NOT** need to fill in the nutritional columns (CHO, Fat, Sodium, Magnesium, Calcium) or the target column (Rowing distance). The algorithm will automatically generate these values during the simulation process.

## Required Input Fields

Please ensure the following **39 indicators** are filled for each subject:

### 1. Basic Information & Anthropometry
* **Previous meal time (min)**: Time elapsed since the last meal.
* **Age (years)**
* **Height (cm)**
* **Weight (kg)**: *Crucial for calculating relative nutrient intake.*
* **Body water percentage** (e.g., 0.60 for 60%)
* **Body fat percentage** (e.g., 0.15 for 15%)
* **Triceps skinfold (mm)**
* **Subscapular skinfold (mm)**
* **Suprailiac skinfold (mm)**
* **Abdominal skinfold (mm)**
* **Upper arm circumference (cm)**
* **Waist circumference (cm)**
* **Hip circumference (cm)**
* **Subgluteal thigh circumference (cm)**
* **Mid-thigh circumference (cm)**
* **Calf circumference (cm)**

### 2. Sleep & Lifestyle
* **Deep sleep duration (min)**
* **Light sleep duration (min)**
* **REM sleep duration (min)**
* **IES-2 (score)**: Intuitive Eating Scale-2 score.
* **PSQI (score)**: Pittsburgh Sleep Quality Index score.
* **PARS-3 (score)**: Physical Activity Rating Scale-3 score.
* **Total cigarettes in last 30 days (cigarettes)**
* **Total alcohol units in last 30 days (units)**

### 3. Physiological State (Baseline)
* **Resting heart rate (bpm)**
* **Systolic blood pressure (mmHg)**
* **Diastolic blood pressure (mmHg)**
* **Blood glucose (mmol/L)**
* **Blood lactate (mmol/L)**
* **Hemoglobin (g/dL)**

### 4. Physical Capacity & CNS Function
* **Left-hand grip strength (kg)**
* **Right-hand grip strength (kg)**
* **Average countermovement jump before exercise (cm)**
* **DC potential (mV)**
* **HF (ms2)**: High Frequency HRV.
* **LF (ms2)**: Low Frequency HRV.
* **Total power (ms2)**
* **SDNN (ms)**
* **RMSSD (ms)**
* **SDSD (ms)**

---
**Note:** The columns for nutritional intake (CHO, Fat, etc.) and performance (Rowing distance) can be left blank or as default 0, as they will be overwritten by the optimization algorithm.