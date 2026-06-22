<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=00f2fe&height=200&section=header&text=Task%2003:%20Computer%20Vision%20Classifier&fontSize=40&animation=fadeIn&fontAlignY=38&desc=Prodigy%20Infotech%20ML%20Internship&descAlignY=60&descAlign=50" alt="Task 3 Banner" />
</div>

<div align="center">
  <img src="https://img.shields.io/badge/Algorithm-Support_Vector_Machine-013243?style=for-the-badge&logo=scikit-learn" alt="SVM" />
  <img src="https://img.shields.io/badge/Computer_Vision-HOG_Feature_Extraction-D00000?style=for-the-badge" alt="HOG" />
  <img src="https://img.shields.io/badge/Python-Data_Science-F7931E?style=for-the-badge&logo=python" alt="Python" />
</div>

<br/>

## 🎯 Project Objective
The objective of this project is to build an end-to-end **Computer Vision Pipeline** capable of classifying images (Cats vs. Dogs). Instead of relying on black-box deep learning models, this project demonstrates a strong fundamental understanding of classical computer vision by utilizing mathematical **HOG (Histogram of Oriented Gradients)** feature extraction paired with a highly optimized **Support Vector Machine (SVM)**.

---

## 👁️ Computer Vision Pipeline

To process raw image data into machine-readable mathematical vectors, the following preprocessing pipeline was engineered:
1.  **Dimensionality Reduction**: All images are mathematically standardized to a `128x128` pixel resolution to ensure matrix uniformity.
2.  **Grayscale Conversion**: Images are converted to a single-channel `L` (luminance) format to reduce computational overhead while preserving structural data.
3.  **HOG Feature Extraction**: Utilized `skimage.feature.hog` to extract gradient orientations (9 orientations, 8x8 pixels per cell). This converts complex visual structures (like fur or ears) into a flattened mathematical feature vector.
4.  **Standardization**: Passed the extracted feature vectors through a `StandardScaler` to normalize the data for the SVM optimizer.

---

## 🤖 Machine Learning Architecture
*   **Algorithm**: Support Vector Classification (`SVC`).
*   **Kernel Strategy**: Implemented an **RBF (Radial Basis Function)** kernel to project the HOG features into a higher-dimensional space, successfully mapping the non-linear boundaries between the visual features of cats and dogs.
*   **Regularization ($C$)**: Hyperparameter $C$ was set to `10` to heavily penalize misclassifications during the margin-maximization phase.

---

## 📈 Model Performance Metrics
The SVM model was evaluated on an unseen test split, achieving the following results:

| Metric | Score | Detail |
| :--- | :--- | :--- |
| **Overall Accuracy** | `85.0%` | High baseline accuracy for a non-neural network computer vision model. |
| **Cat Precision** | `90.0%` | Out of all images predicted as "Cat", 90% were actually Cats. |
| **Dog Recall** | `88.0%` | Successfully identified 88% of all actual Dog images in the dataset. |
| **F1-Score (Macro)** | `0.85` | Perfectly balanced harmonic mean between precision and recall. |

*Visual diagnostics (Confusion Matrix Heatmaps, Random Sampling Checks, and Misclassification Visualizers) are included in the Jupyter Notebook.*

---

## 💻 Interactive Predictive Widget
To make the model production-ready and accessible, I engineered an interactive graphical interface directly within the Jupyter Notebook using `ipywidgets`. 

Users can actively upload custom images (`.jpg`, `.png`) from their local machine. The widget automatically processes the image through the established HOG extraction pipeline, scales the features, and utilizes the pre-trained `model.pkl` to render a real-time prediction on the screen.

---

## 🛠️ Tools & Libraries Used
*   **Computer Vision**: `skimage.feature.hog`, `skimage.color`, `PIL.Image`.
*   **Machine Learning**: `scikit-learn` (`SVC`, `StandardScaler`, `train_test_split`).
*   **Data Visualization**: `matplotlib`, `seaborn` (Heatmaps & Residuals).
*   **Interactive UI**: `ipywidgets`, `IPython.display`.

<br>
<div align="center">
  <i>Part of the Prodigy Infotech Internship Portfolio by Md Huzaifa Ansari</i>
</div>
