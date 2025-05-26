# -Heart-_Attack_Prediction
# Heart Attack Prediction: Dimensionality Reduction Analysis

## Project Overview

This project explores the application of various dimensionality reduction techniques to a clinical dataset related to cardiac health. The primary goal is to visualize high-dimensional patient data, assess the separability of patient outcomes (e.g., 'positive' or 'negative' for a cardiac event), and understand the unique insights each dimensionality reduction method provides.

The dataset (`dataset_1.csv`) contains anonymized patient information, including demographic details, vital signs, and crucial cardiac biomarkers like CK-MB and Troponin.

**Techniques Explored:**
1.  **Principal Component Analysis (PCA)**
2.  **Linear Discriminant Analysis (LDA)**
3.  **Multidimensional Scaling (MDS)**
4.  **Locally Linear Embedding (LLE)**

## Dataset

*   **Filename:** `dataset_1.csv`
*   **Source:** Provided for the assignment.
*   **Number of Samples:** 100
*   **Number of Features:** 8 predictor features + 1 target variable
    *   **Predictor Features:** Age, Gender, Heart rate, Systolic blood pressure, Diastolic blood pressure, Blood sugar, CK-MB, Troponin.
    *   **Target Variable:** `Result` (Categorical: 'positive', 'negative')
*   **Class Distribution:** Relatively balanced (Positive: 52, Negative: 48).

## Methodology

1.  **Data Loading & Preprocessing:**
    *   The dataset was loaded using Pandas.
    *   An outlier in the 'Heart rate' feature (value of 1111 bpm) was identified and replaced with the median heart rate of the dataset.
    *   The categorical target variable `Result` was label encoded ('negative': 0, 'positive': 1).
    *   All 8 numerical predictor features were standardized using `StandardScaler` from Scikit-learn to have zero mean and unit variance. This is crucial for distance-based algorithms and PCA.

2.  **Dimensionality Reduction:**
    *   Each of the four techniques (PCA, LDA, MDS, LLE) was applied to the preprocessed (scaled) data.
    *   The data was reduced to 2 dimensions for visualization (except for LDA, which reduces to 1 dimension for a 2-class problem).
    *   Key parameters for each algorithm were set (details in the code and report/presentation).

3.  **Visualization:**
    *   The reduced-dimension data was plotted using Matplotlib.
    *   Different colors/markers were used to distinguish between the 'positive' and 'negative' classes in the visualizations.

4.  **Analysis & Comparison:**
    *   The results of each method were compared based on:
        *   Visual separation of classes.
        *   Metrics like explained variance (PCA), stress (MDS), and reconstruction error (LLE).
        *   The type of data structure preserved by each technique.
    *   Insights were drawn from the visualizations regarding the dataset's characteristics and the effectiveness of each method.

## Project Structure

*   `dataset_1.csv`: The raw input dataset.
*   `cardiac_dimensionality_reduction.ipynb` (or `.py`): Jupyter Notebook or Python script containing the full code for data loading, preprocessing, dimensionality reduction, visualization, and analysis.
*   `README.md`: This file.
*   `presentation.ppt` (Optional): Slides summarizing the project, methodology, results, and conclusions.
*   `report.pdf` (Optional): Detailed report of the assignment.

## Requirements / Environment

*   **Python:** 3.9+ (e.g., 3.10.5)
*   **Core Libraries:**
    *   Pandas (e.g., 1.5.x)
    *   NumPy (e.g., 1.23.x)
    *   Scikit-learn (e.g., 1.2.x)
    *   Matplotlib (e.g., 3.7.x)
    *   Seaborn (Optional, e.g., 0.12.x, if used for advanced plots like density plots for LDA)

You can install these dependencies using pip:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn

How to Run
1.  Ensure you have Python and the required libraries installed (see Requirements).
2.  Clone this repository or download the files.
3.  Place dataset_1.csv in the same directory as the script/notebook.
4.  Run the Jupyter Notebook cardiac_dimensionality_reduction.ipynb or execute the Python script cardiac_dimensionality_reduction.py.
# If it's a .py script
python cardiac_dimensionality_reduction.py
5.  The script will output descriptive statistics, print progress for each DR method, and display the visualization plots.

Key Findings (Summary)
*  LDA was the most effective method for visually separating the 'positive' and 'negative' cardiac outcome classes due to its supervised nature.
*  PCA captured a significant portion of the dataset's variance in two dimensions but showed moderate overlap between classes.
*  MDS provided a global view of patient similarity, with its stress value indicating a fair preservation of original inter-patient distances.
*  LLE attempted to uncover non-linear manifold structures, and its effectiveness varied (dependent on dataset characteristics and parameter tuning).
*  Data preprocessing, particularly outlier handling and feature scaling, was crucial for obtaining meaningful and comparable results across different techniques.
*  The choice of dimensionality reduction technique is highly dependent on the specific analytical goal (e.g., class separation, variance preservation, distance      preservation, or manifold learning).

Future Work / Potential Extensions
*  Tune hyperparameters for LLE (e.g., n_neighbors) more extensively.
*  Explore other non-linear dimensionality reduction techniques like t-SNE or UMAP.
*  Investigate which original features contribute most to the dimensions found by PCA and LDA.
*  Use the reduced dimensions as features for building predictive classification models for heart attack risk.

Author(s)
[Sreeya Dora]
