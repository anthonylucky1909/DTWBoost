# DTW-SVM-X: Evaluating SVM Kernels with DTW for Time Series Classification

## 📌 Abstract
This project evaluates the use of **Support Vector Machine (SVM)** with different **kernel functions** combined with **Dynamic Time Warping (DTW)** for classifying time series data. We assess performance on datasets like **ECG**, **FordA**, and **HAR**.

## 🔑 Keywords
- SVM
- DTW
- Kernel Function
- Time Series Classification

## 🎯 Objective
Evaluate the effectiveness of various DTW-based SVM kernels on different time series datasets.

## 📚 Related Work
Past research explored DTW-SVM combinations. Kernels like Gaussian, Polynomial, and custom DTW-based ones have shown varying success.

## ⚙️ Methodology

### Steps:
1. **Preprocessing** – Normalize and balance data
2. **DTW Distance Calculation**
3. **Kernel Application** – Replace Euclidean distance with DTW in kernel
4. **SVM Training** – With cross-validation
5. **Evaluation** – Accuracy and confusion matrix

### Kernels Used:
- **Cauchy**: \( K(x,x') = \frac{1}{1 + \|x - x'\|^2} \)
- **Gaussian**: \( K(x,x') = e^{-\|x - x'\|^2 / \sigma} \)
- **Inverse Multiquadric**: \( K(x,x') = \frac{1}{\sqrt{2\sigma^2\|x - x'\|^2 + c^2}} \)
- **Laplacian**: \( K(x,x') = e^{-\|x - x'\| / \sigma} \)
- **Log**: \( K(x,x') = -\log(\|x - x'\| + c) \)
- **Rational Quadratic**: \( K(x,x') = 1 - \frac{\|x - x'\|^2}{\|x - x'\|^2 + c} \)

## 📊 Datasets
- **ECG** – Heartbeat signal classification
- **FordA** – Engine fault detection
- **HAR** – Human activity via smartphone sensors

## 🔧 Experimental Settings

### Metrics:
- **Accuracy**
- **Confusion Matrix**

### Sample Results (ECG)
| Kernel | Hyperparameter | Time (s) |
|--------|----------------|----------|
| Cauchy | sigma=500000   | 213.1    |
| Gaussian | sigma=1     | 310.7    |
| Inverse MQ | c=0.4      | 346.7    |

### Accuracy Comparison
| Kernel | ECG (%) | FordA (%) | HAR (%) |
|--------|---------|-----------|---------|
| Cauchy | 89.0    | 60.5      | 70.0    |
| Gaussian | 76.0  | 45.0      | 57.1    |
| Inverse MQ | 85.0 | 60.0      | 80.3    |
| Laplacian | 83.0 | 53.5      | 82.7    |
| Log     | 38.0   | 53.0      | 85.6    |
| RQ      | 84.0   | 54.0      | 87.0    |

## 💬 Insights
- **Inverse Multiquadric** performs best across datasets.
- DTW improves SVM accuracy but increases computation.
- FordA is harder due to signal variance.

## 🧠 Discussion
- **DTW** is effective but slow; use **FastDTW** or parallelism for scalability.
- DTW kernels help with noisy, irregular-length time series.

## ✅ Conclusion
Combining DTW with flexible SVM kernels significantly improves time series classification. **Rational Quadratic** and **Inverse Multiquadric** performed best.

## 📖 References
1. Lei & Sun, Dynamic Time Warping in Kernel Machines
2. Hofmann et al., Kernel Methods in ML
3. Zhang, List of SVM Kernels
4. Reyes-Ortiz, HAR Dataset
5. Bagnall, FordA Dataset
6. Kachuee et al., ECG Classification
7. [NCBI DTW Paper](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4120293/)

