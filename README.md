# DTW-SVM-X: Evaluation of Different SVM Kernels with DTW on Time Series Classification
## Abstract

Support Vector Machine (SVM) is a powerful classifier for multidimensional data. This paper evaluates the effectiveness of different SVM kernels combined with Dynamic Time Warping (DTW) as a distance metric for time series classification. We compare several kernel functions (Cauchy, Gaussian, Inverse Multiquadric, Laplacian, Log, Rational Quadratic) incorporated with DTW to assess their performance on time series datasets such as ECG, FordA, and Human Activity Recognition (HAR).

## Keywords

- Kernel Function
- Support Vector Machine
- Time Series Classification
- Dynamic Time Wrapping

## 1. Introduction

SVM is a supervised learning method used for classification by finding an optimal hyperplane that separates data. Kernel functions in SVM transform input data into a higher-dimensional feature space where linear separation is possible. However, for time series data, the temporal ordering of sequences should be considered, making the choice of kernel function crucial.

DTW is widely used to measure similarity between time series data, especially when the sequences may differ in length or speed. This paper explores integrating DTW with different SVM kernels for improved time series classification.

## 2. The Aim of The Study

This study evaluates the performance of various SVM kernel functions with DTW in the task of time series classification.

## 3. Related Work

Various studies have explored using DTW for time series classification with SVM. For example, Chen et al. (2019) proposed a new DTW-based kernel for SVM, showing its superior performance on certain datasets. Other distance metrics like Euclidean and Cosine distances have also been explored in combination with SVM for time series classification.

## 4. Methodology

### 4.1 Problem Approach

The methodology involves:

1. **Data Preprocessing**: Cleaning, normalizing, and balancing datasets.
2. **Calculation of DTW Distances**: Compute DTW distances between time series.
3. **Calculation of Kernel**: Replace distance metrics in the kernel function with DTW.
4. **SVM Model Training**: Train SVM using the DTW-based kernel and optimize hyperparameters via cross-validation.
5. **Model Evaluation**: Assess the models using accuracy and confusion matrix metrics.

### 4.2 Chosen Kernel Functions

The kernels evaluated in this study are:

- **Cauchy Kernel**: 
  \[
  K(x, x') = \frac{1}{1 + \|x - x'\|^2}
  \]

- **Gaussian Kernel**: 
  \[
  K(x, x') = \exp\left(\frac{-\|x - x'\|^2}{\sigma}\right)
  \]

- **Inverse Multiquadric Kernel**: 
  \[
  K(x, x') = \frac{1}{\sqrt{2\sigma^2 \|x - x'\|^2 + c^2}}
  \]

- **Laplacian Kernel**: 
  \[
  K(x, x') = \exp\left(\frac{-\|x - x'\|}{\sigma}\right)
  \]

- **Log Kernel**: 
  \[
  K(x, x') = -\log(\|x - x'\| + c)
  \]

- **Rational Quadratic Kernel**: 
  \[
  K(x, x') = 1 - \frac{\|x - x'\|^2}{\|x - x'\|^2 + c}
  \]


## 5. Experimental Settings

### 5.1 Data Descriptions

- **ECG Heartbeat Categorization Dataset**: Consists of ECG heart rate signals for normal and arrhythmic cases.
- **FordA Dataset**: Contains engine noise measurements for diagnosing subsystems in vehicles.
- **Human Activity Recognition with Smartphones Dataset**: Includes data collected from smartphone sensors for classifying human activities.

### 5.2 Preprocessing

The preprocessing steps involved resampling to handle class imbalance and normalization to ensure consistent data scaling.

### 5.3 Evaluation Metrics

- **Accuracy**: The percentage of correctly classified instances.
- **Confusion Matrix**: A matrix to summarize the performance of a classifier, showing correct and incorrect predictions.

### 5.4 Hyperparameter Settings and Runtime

#### ECG Dataset

| Kernel Function    | Hyperparameter   | Compute Time (s) |
|--------------------|------------------|------------------|
| Cauchy            | sigma = 500000   | 213.1            |
| Gaussian          | sigma = 1        | 310.7            |
| Inverse Multiquadric | c = 0.4        | 346.7            |
| Laplacian         | sigma = 1.4      | 405.2            |
| Log               | c = 1            | 444.4            |
| Rational Quadratic| c = 1            | 506.4            |

#### FordA Dataset

| Kernel Function    | Hyperparameter   | Compute Time (s) |
|--------------------|------------------|------------------|
| Cauchy            | sigma = 500000   | 771.9            |
| Gaussian          | sigma = 4        | 832.5            |
| Inverse Multiquadric | c = 1          | 847.0            |
| Laplacian         | sigma = 18       | 846.9            |
| Log               | c = 1            | 839.2            |
| Rational Quadratic| c = 100          | 826.4            |

#### HAR Dataset

| Kernel Function    | Hyperparameter   | Compute Time (s) |
|--------------------|------------------|------------------|
| Cauchy            | sigma = 600000   | 1219.1           |
| Gaussian          | sigma = 90000    | 1323.3           |
| Inverse Multiquadric | c = 0.4        | 1363.6           |
| Laplacian         | sigma = 700      | 1375.3           |
| Log               | c = 1            | 1398.1           |
| Rational Quadratic| c = 9000         | 1390.3           |

The experiments were conducted on a MacBook Pro 2020 with an M1 chip.

## 6. Experimental Results

### 6.1 Accuracy of Different Kernels

| Kernel Function    | ECG (%) | FordA (%) | HAR (%) |
|--------------------|---------|-----------|---------|
| Cauchy             | 89.0    | 60.5      | 70.0    |
| Gaussian           | 76.0    | 45.0      | 57.1    |
| Inverse Multiquadric | 85.0  | 60.0      | 80.3    |
| Laplacian          | 83.0    | 53.5      | 82.7    |
| Log                | 38.0    | 53.0      | 85.6    |
| Rational Quadratic | 84.0    | 54.0      | 87.0    |

### 6.2 Analysis of Results

- The **Inverse Multiquadric** kernel performs well across all datasets.
- Some kernels, like **Cauchy** and **Log**, perform inconsistently across datasets.
- **DTW** may struggle with datasets like FordA due to patterns appearing at different frequencies across samples.

## 7. Discussion

### 7.1 Related Issues

DTW, while powerful for time series data, can be computationally expensive and memory-intensive. Approximations such as **FastDTW** or parallel computing can help alleviate these issues.

### 7.2 Insights

Using **DTW** as a distance metric within SVM kernels allows for more accurate classification of time series with varying lengths and irregular sampling rates. This improves performance, especially in datasets with noisy signals and differing time scales.

## 8. Conclusions

Using **DTW** with various kernel functions for time series classification is effective, especially for datasets with varying sequence lengths. The **Inverse Multiquadric** kernel showed consistently good performance. Proper hyperparameter tuning is crucial for optimizing model performance.

## References

1. Hansheng Lei and Bingyu Sun, A Study on the Dynamic Time Warping in Kernel Machines
2. Thomas Hofmann, Bernhard Scholkopf, and Alexander J. Smola, **Kernel Methods in Machine Learning**
3. Jiapu Zhang, **A Complete List of Kernels Used in Support Vector Machines**
4. Vincent Wan and James Carmichael, **Polynomial Dynamic Time Warping Kernel Support Vector Machines**
5. Charu C. Aggarwal, **Data Mining**
6. Jorge L. Reyes-Ortiz et al., **Human Activity Recognition Using Smartphones Data Set**
7. A. Bagnall, **FordA Dataset**
8. Mohammad Kachuee et al., **ECG Heartbeat Classification: A Deep Transferable Representation**
9. [NCBI Article](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4120293/)
