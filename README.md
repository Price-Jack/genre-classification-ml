# Genre Classification Using Machine Learning Methods

Automatic Music Genre Classification (AMGC) using the **Spotify Tracks Dataset** (tabular track metadata/features).  
This project compares multiple ML architectures to predict a track’s genre and evaluate which model family performs best for this kind of **tabular** classification task.

**Course:** CAP5610 (Spring 2025)  
**Team:** Group 8 (Fort Knight) — Natalie Nguyen, Jack Price, Jeovani Overstreet, Vicente Sosa L.

---

## Project Overview

Music “genre” labeling can be ambiguous and inconsistent across platforms. This project evaluates how well different machine learning architectures classify genres using track-level features from the Spotify Tracks Dataset.

We compare four approaches:

- **MLP (Multi-Layer Perceptron)**
- **1D CNN**
- **LSTM**
- **Transformer**

---

## Dataset

- **Spotify Tracks Dataset** (Kaggle) by Maharshi Pandya (2022)
- Input: tabular features/metadata (not raw audio)
- Labels: genres (reduced to a smaller set for practical classification)

> Note: The original dataset contained many genres; we reduced the number of genres down to a smaller set to make the classification task more stable and meaningful.

---

## Methodology

### Evaluation Metrics
Models are evaluated using:
- Accuracy
- Loss
- Precision / Recall / F1-score (including genre-wise F1)
- Confusion matrices
- Training/validation curves (where applicable)

### Models Implemented
- **MLP:** strong baseline for tabular data
- **1D CNN:** treats feature vectors with convolutional layers
- **LSTM:** sequence-style architecture (applied to structured features)
- **Transformer:** attention-based model applied to the same feature set

---

## Results Summary (Test Set)

| Model        | Test Accuracy | Test Loss | Avg F1  | Avg Precision |
|-------------|---------------|----------:|--------:|--------------:|
| Transformer | 80.09%        | 0.5958    | 0.795   | 0.80          |
| **LSTM**    | **82.81%**    | 0.5010    | 0.79    | 0.80          |
| **MLP**     | **86.63%**    | 0.4295    | 0.8250  | 0.8273        |
| 1D CNN      | 80.34%        | 0.5744    | 0.795   | 0.80          |

**Key takeaway:** The **MLP performed best overall**, which aligns with expectations for tabular feature classification.

---

## LSTM Configuration (My Contribution)

My primary contribution to the group project was the **LSTM model** and its evaluation.

LSTM setup included:
- Learning rate: **0.002**
- Dropout: **0.1**
- Batch size: **32**
- Training: **100 epochs** with **early stopping**
- Architecture: **2 Bidirectional LSTM layers** (128 units then 64 units), followed by Dense(32), Softmax output

---

## Visualizations

This repo includes:
- Confusion matrices (per model)
- Performance curves / comparison plots
- Genre-wise metric summaries (best/worst classes)

If you add images to the repo, a good pattern is:
- `assets/` for plots and figures  
- Embed them here like:

```md
![LSTM Confusion Matrix](assets/lstm_confusion_matrix.png)
