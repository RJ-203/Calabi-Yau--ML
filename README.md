# Calabi-Yau--ML
This project predicts Hodge numbers (h11, h21) and the Euler characteristic of Calabi Yau threefolds from combinatorial and weight vector data. It also explores candidate geometries via inverse design using machine learning and investigates the performance of a quantum kernel regression model.

Key components 
- Regression modeling
-- Classical: Linear Regression, RBF SVR, Gradient Boosting Regressor (GBR)
-- Quantum-inspired: Quantum Kernel Regression using ZZFeatureMap or PauliFeatureMap with SVR. Includes PCA for dimensionality reduction.
- Inverse design
-- Generate candidate weight vectors (random or near dataset entries).
-- Apply approximate physical constraints: reflexivity and quasi-smoothness.
-- Predict Hodge invariants using trained regressors and select candidates close to target values.

Results & Interpretation
-Regression: 
-- Classical RBF SVR achieves high R² on small subsets.
-- Quantum kernels perform well on training data (R² on subset) but often drop on test data.
  This is likely due to overfitting on small training subsets, sensitivity of quantum kernels to feature   scaling, and limited generalization of small quantum kernels
-- Gradient boosting provides feature importance and interpretable SHAP values.
-Inverse design:
-- ML generates candidate geometries satisfying approximate physical constraints.
-- Some generated candidates differ from entries in the original dataset 
-- Candidates are ranked by fitness relative to target h11, h21, and euler number.
-- Caution: Physical constraints like quasi-smoothness and reflexivity are applied approximately. Generated candidates should be verified for full mathematical consistency.

Note: Small subsets are recommended for quantum kernel evaluation due to computational cost.
