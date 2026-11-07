# Breast Cancer Histopathology Image Classification Using KNN

## Project Overview

This project focuses on classifying breast cancer histopathology images using the **K-Nearest Neighbors (KNN)** machine learning algorithm.

The project uses the Breast Histopathology Images (IDC) dataset to classify image patches into two categories: Non-Cancerous and Cancerous.

Histogram of Oriented Gradients (HOG) is used for feature extraction, followed by feature scaling and KNN-based classification.

The objective is to explore the effectiveness of traditional Machine Learning techniques in medical image classification.

## Objectives

- Classify breast histopathology images into cancerous and non-cancerous categories.
- Extract meaningful image features using HOG.
- Implement the K-Nearest Neighbors algorithm.
- Compare different K values to identify the best-performing model.
- Evaluate model performance using standard classification metrics.
- Analyze the potential of traditional ML approaches for medical image analysis.

## Dataset Information

**Dataset:** Breast Histopathology Images (IDC)

**Source:** Kaggle  
https://www.kaggle.com/datasets/paultimothymooney/breast-histopathology-images

The dataset contains histopathology image patches of size 50 × 50 pixels.

### Classification Labels

| Label | Class |
|---|---|
| 0 | Non-Cancerous |
| 1 | Cancerous |

Dataset statistics from this experiment:

- Total Images: 277,524
- Non-Cancerous Images: 198,738
- Cancerous Images: 78,786

## Technologies and Libraries

- Python
- NumPy
- Pandas
- OpenCV
- Scikit-image
- Scikit-learn
- Matplotlib
- Seaborn
- Joblib
- Jupyter Notebook

## Methodology

The project follows these steps:

### 1. Data Loading
The IDC histopathology dataset is loaded, and image paths, labels, and patient IDs are extracted.

### 2. Data Visualization
Sample histopathology images and class distributions are visualized to understand the dataset.

### 3. Patient-Wise Data Splitting
The dataset is divided into training, validation, and testing sets using GroupShuffleSplit.

Patient-wise splitting helps prevent images from the same patient appearing in multiple data partitions.

### 4. Balanced Training Dataset
A balanced subset of 4,000 images is selected:
- 2,000 Non-Cancerous images
- 2,000 Cancerous images

### 5. HOG Feature Extraction
Histogram of Oriented Gradients (HOG) is applied to extract image features based on gradients, edges, and texture patterns.

### 6. Feature Scaling
StandardScaler is used to normalize the extracted features before KNN classification.

### 7. KNN Model Training
The KNN classifier is trained using different neighborhood values:

- K = 3
- K = 5
- K = 7
- K = 9

The best K value is selected based on validation F1-score.

### 8. Model Evaluation
The final model is evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- ROC-AUC Score

## Experimental Configuration

| Parameter | Value |
|---|---|
| Algorithm | K-Nearest Neighbors |
| Feature Extraction | HOG |
| Image Size | 64 × 64 |
| Training Samples | 4,000 |
| Validation Samples | 2,000 |
| Testing Samples | 2,000 |
| Feature Scaling | StandardScaler |
| Distance Metric | Euclidean |
| K Values | 3, 5, 7, 9 |
| Weighting | Distance-based |

## Results

The model performance is evaluated using a balanced test sample containing 2,000 images.

### Final Performance Metrics

Update the following values using your actual notebook output.

| Metric | Result |
|---|---|
| Best K Value | YOUR_RESULT |
| Accuracy | YOUR_RESULT |
| Precision | YOUR_RESULT |
| Recall | YOUR_RESULT |
| F1-Score | YOUR_RESULT |
| ROC-AUC | YOUR_RESULT |

### Model Evaluation Visualizations

**Confusion Matrix**

![KNN Confusion Matrix](KNN_Confusion_Matrix.png)

**ROC Curve**

![KNN ROC Curve](KNN_ROC_Curve.png)

## Repository Structure

```text
Breast-Cancer-Classification-KNN/
│
├── Breast_Cancer_KNN.ipynb
├── best_knn_model.pkl
├── knn_scaler.pkl
├── KNN_Confusion_Matrix.png
├── KNN_ROC_Curve.png
├── KNN_K_Comparison.csv
├── KNN_Final_Results.csv
├── requirements.txt
└── README.md
```

## Installation and Usage

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/Breast-Cancer-Classification-KNN.git
```

### 2. Navigate to the Project Directory

```bash
cd Breast-Cancer-Classification-KNN
```

### 3. Install Required Libraries

```bash
pip install -r requirements.txt
```

### 4. Download the Dataset

Download the Breast Histopathology Images dataset from Kaggle and extract it locally.

### 5. Configure Dataset Path

Update the dataset path in the Jupyter Notebook according to your system.

### 6. Run the Notebook

```bash
jupyter notebook Breast_Cancer_KNN.ipynb
```

Execute the notebook cells sequentially to reproduce the experiment.

## Requirements

Create a `requirements.txt` file containing:

```text
numpy
pandas
opencv-python
scikit-image
scikit-learn
matplotlib
seaborn
joblib
jupyter
Pillow
```

## Limitations

- KNN performance depends on the quality of extracted features.
- HOG captures gradient and texture information but may not represent all complex histopathological patterns.
- The experiment uses a balanced subset rather than the complete dataset for model training and evaluation.
- KNN can become computationally expensive as the training dataset grows.
- This experimental model is not validated for clinical diagnosis.

## Future Scope

- Compare KNN with CNN and other Machine Learning algorithms.
- Explore alternative feature extraction techniques such as LBP and GLCM.
- Perform hyperparameter optimization.
- Investigate dimensionality reduction using PCA.
- Explore hybrid feature extraction and classification approaches.
- Evaluate performance on larger and independently sourced datasets.

## Conclusion

This project demonstrates the implementation of a traditional Machine Learning approach for breast cancer histopathology image classification using HOG feature extraction and the KNN algorithm.

It provides practical insights into image preprocessing, feature engineering, distance-based classification, and model evaluation.

The experiment also creates a foundation for comparing traditional Machine Learning methods with Deep Learning architectures such as Convolutional Neural Networks (CNN).

**Note:** This project is intended strictly for educational and research purposes and should not be used as a medical diagnostic system.

## Author

**Utkrisht Patel**

M.Tech – Computer Science and Engineering  
Research & Development | Machine Learning | Deep Learning | IoT

GitHub: https://github.com/UTKRISHT-ICS52

LinkedIn: www.linkedin.com/in/utkrisht-patel2007

---
⭐ If you find this project useful, consider giving the repository a star!
