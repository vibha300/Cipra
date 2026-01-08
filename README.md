# Cipra

# Signal Processing & Classification Demo

This notebook demonstrates **signal preprocessing, feature extraction, and classification** for 1D signals (e.g., ECG segments).

## Main Steps

1. **Load & Parse Data**
   - CSV file with columns: `id`, `signal`, `label`.
   - `signal` column is parsed into 1D NumPy arrays.

2. **Visualization**
   - Plot raw waveforms for random segments.
   - Plot raw vs filtered versions for comparison.

3. **Preprocessing**
   - **Band-pass filter**: 0.5–8 Hz (typical cardiac band).
   - **Detrend**: remove baseline drift.
   - **Normalization**: zero mean, unit variance.

4. **Feature Extraction**
   - Simple features per segment:
     - Mean
     - Standard deviation
     - Peak-to-peak amplitude
     - Approximate heart rate (via peak detection)
     - Signal energy

5. **Train / Validation Split**
   - 80/20 split for train and validation sets.

6. **Model Training**
   - Classical model: Logistic Regression (can be replaced with Random Forest, XGBoost, etc.)
   - Input: extracted features
   - Output: label (`clean` / `noisy`)

7. **Evaluation**
   - Metrics:
     - Accuracy
     - F1 score (macro-averaged for string labels)

8. **Interactive Demo**
   - Implemented with `ipywidgets` in Colab.
   - Features:
     - Select a random validation segment.
     - Enter a specific ID.
     - Display waveform (raw + filtered) and model prediction.

## Dependencies
- Python >= 3.8
- pandas
- numpy
- matplotlib
- scipy
- scikit-learn
- ipywidgets
