# ActivityRecognition_From_LoW_Frequency_Accelerometer_Data
Evaluating the capability of activity detection from low-frequency accelerometer data coming from resource constrained devices.

This project demonstrates that **low-frequency accelerometer data (1Hz and 2Hz)** collected from **resource-constrained IoT devices** (BLE beacons, embedded sensors, battery-powered devices) can be used to recognize human activities effectively with classical machine learning algorithms.

---

## Dataset Overview

Used the refined WISDM_raw from https://www.kaggle.com/datasets/sosoyeong/wisdm-raw/data  
The dataset includes labeled human activities:
- Downstairs
- Jogging
- Sitting
- Standing
- Upstairs
- Walking

---

## Methodology

- **Downsampling** 
- **Feature extraction**
- **Classical ML model** (Random Forest)
- **Evaluation using confusion matrices**

---

## Results — 1Hz Sampling

> Even at **1Hz**, the model effectively distinguishes static and dynamic activities.

| Activity   | Precision | Recall | F1-Score | Support |
| ---------- | --------- | ------ | -------- | ------- |
| Downstairs | 0.84      | 0.45   | 0.58     | 991     |
| Jogging    | 0.91      | 0.94   | 0.92     | 3516    |
| Sitting    | 1.00      | 0.98   | 0.99     | 589     |
| Standing   | 0.98      | 0.96   | 0.97     | 477     |
| Upstairs   | 0.82      | 0.53   | 0.64     | 1174    |
| Walking    | 0.79      | 0.94   | 0.86     | 4235    |

![Confusion Matrix at 1Hz](https://github.com/Shakhawat-Fahim/ActivityRecognition_From_LoW_Frequency_Accelerometer_Data/blob/main/conf_Matrix_1Hz.png)

---

## Results — 2Hz Sampling

> At **2Hz**, performance improves further, especially for movement-based classes like **Jogging** and **Upstairs**.

| Activity   | Precision | Recall | F1-Score | Support |
| ---------- | --------- | ------ | -------- | ------- |
| Downstairs | 0.79      | 0.41   | 0.54     | 2073    |
| Jogging    | 0.92      | 0.94   | 0.93     | 6787    |
| Sitting    | 1.00      | 0.99   | 0.99     | 1195    |
| Standing   | 0.99      | 0.97   | 0.98     | 952     |
| Upstairs   | 0.78      | 0.51   | 0.62     | 2471    |
| Walking    | 0.79      | 0.95   | 0.86     | 8486    |

![Confusion Matrix at 2Hz](https://github.com/Shakhawat-Fahim/ActivityRecognition_From_LoW_Frequency_Accelerometer_Data/blob/main/conf_Matrix_2Hz.png)

---

## Insights

- **1Hz** is sufficient for posture and low-movement activities
- **2Hz** adds value for motion-intensive recognition
- **Classical ML** can perform well even without deep models

---

## Tools & Libraries

- Python (Pandas, NumPy)
- Scikit-learn
- Matplotlib / Seaborn
- Jupyter Notebook

---

## Notebook

See full implementation and plots in:
**[`ActivityRecognition_From_LoW_Frequency_ACCL_Data.ipynb`](ActivityRecognition_From_LoW_Frequency_ACCL_Data.ipynb)**



