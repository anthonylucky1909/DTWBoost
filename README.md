# DTWBoost: A Dynamic Time Warping Enhanced SVM Classifier for Time Series Data

[![PyPI version](https://img.shields.io/pypi/v/dtwboost.svg)](https://pypi.org/project/dtwboost/)
[![PyPI downloads](https://img.shields.io/pypi/dm/dtwboost.svg)](https://pypi.org/project/dtwboost/)
[![Python versions](https://img.shields.io/pypi/pyversions/dtwboost.svg)](https://www.python.org/)
[![Open issues](https://img.shields.io/github/issues/huangjunxiang/DTWBoost.svg)](https://github.com/huangjunxiang/DTWBoost/issues)
[![License](https://img.shields.io/github/license/huangjunxiang/DTWBoost.svg)](https://github.com/huangjunxiang/DTWBoost/blob/main/LICENSE)
[![Coverage](https://codecov.io/gh/huangjunxiang/DTWBoost/branch/main/graph/badge.svg)](https://codecov.io/gh/huangjunxiang/DTWBoost)

---

## 📌 Abstract
This project evaluates the use of **Support Vector Machine (SVM)** with different **kernel functions** combined with **Dynamic Time Warping (DTW)** for classifying time series data.  
We assess performance on datasets such as **ECG**, **FordA**, and **HAR**.

---

## 🔑 Keywords
- Support Vector Machine (SVM)  
- Dynamic Time Warping (DTW)  
- Kernel Functions  
- Time Series Classification  

---

## 🎯 Objective
Evaluate the effectiveness of various DTW-based SVM kernels on different time series datasets.

---

## 📚 Related Work
Past research explored DTW-SVM combinations. Kernels like Gaussian, Polynomial, and custom DTW-based ones have shown varying success.

---

## ⚙️ Methodology

### Steps
1. **Preprocessing** – Normalize and balance data  
2. **DTW Distance Calculation**  
3. **Kernel Application** – Replace Euclidean distance with DTW in kernel  
4. **SVM Training** – With cross-validation  
5. **Evaluation** – Accuracy and confusion matrix  

### Kernels Used
- **Cauchy**  
- **Gaussian**  
- **Inverse Multiquadric**  
- **Laplacian**  
- **Logarithmic**  
- **Rational Quadratic**  

---

## 📊 Datasets
- **ECG** – Heartbeat signal classification  
- **FordA** – Engine fault detection  
- **HAR** – Human activity recognition via smartphone sensors  

---

## 🔧 Experimental Settings

### Metrics
- **Accuracy**  
- **Confusion Matrix**

### Sample Results (ECG)
| Kernel       | Hyperparameter | Time (s) |
|--------------|----------------|----------|
| Cauchy       | sigma=500000   | 213.1    |
| Gaussian     | sigma=1        | 310.7    |
| Inverse MQ   | c=0.4          | 346.7    |

### Accuracy Comparison
| Kernel            | ECG (%) | FordA (%) | HAR (%) |
|-------------------|---------|-----------|---------|
| Cauchy            | 89.0    | 60.5      | 70.0    |
| Gaussian          | 76.0    | 45.0      | 57.1    |
| Inverse MQ        | 85.0    | 60.0      | 80.3    |
| Laplacian         | 83.0    | 53.5      | 82.7    |
| Logarithmic       | 38.0    | 53.0      | 85.6    |
| Rational Quadratic| 84.0    | 54.0      | 87.0    |

---

## 💬 Insights
- **Inverse Multiquadric** performs best across datasets.  
- DTW improves SVM accuracy but increases computation time.  
- FordA is harder due to signal variance.  

---

## 🧠 Discussion
- **DTW** is effective but slow; use **FastDTW** or parallelism for scalability.  
- DTW kernels help with noisy, irregular-length time series.  

---

## ✅ Conclusion
Combining DTW with flexible SVM kernels significantly improves time series classification.  
**Rational Quadratic** and **Inverse Multiquadric** performed best overall.  

---

## 📖 References
1. Lei & Sun, *Dynamic Time Warping in Kernel Machines*  
2. Hofmann et al., *Kernel Methods in ML*  
3. Zhang, *List of SVM Kernels*  
4. Reyes-Ortiz, *HAR Dataset*  
5. Bagnall, *FordA Dataset*  
6. Kachuee et al., *ECG Classification*  
7. [NCBI DTW Paper](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4120293/)  

---

<!-- Badge References -->
[pypi-badge]: https://img.shields.io/pypi/v/dtwboost.svg
[pypi-url]: https://pypi.org/project/dtwboost/
[downloads-badge]: https://img.shields.io/pypi/dm/dtwboost.svg
[downloads-url]: https://pypi.org/project/dtwboost/
[python-badge]: https://img.shields.io/pypi/pyversions/dtwboost.svg
[python-url]: https://www.python.org/
[issues-badge]: https://img.shields.io/github/issues/huangjunxiang/DTWBoost.svg
[issues-url]: https://github.com/huangjunxiang/DTWBoost/issues
[license-badge]: https://img.shields.io/github/license/huangjunxiang/DTWBoost.svg
[license-url]: https://github.com/huangjunxiang/DTWBoost/blob/main/LICENSE
[coverage-badge]: https://codecov.io/gh/huangjunxiang/DTWBoost/branch/main/graph/badge.svg
[coverage-url]: https://codecov.io/gh/huangjunxiang/DTWBoost
