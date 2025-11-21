# DA5401-2025-Data-Challenge

Sudha Sarraf
Roll Number: NS25Z247
This repository contains the complete pipeline for the DA5401-2025 Data Challenge. The challenge required designing a model that predicts a numerical fitness score (0 to 10) reflecting how well an AI assistant's response adheres to a given evaluation metric in a multilingual setting.
Final Approach Summary
Architecture: Attention-based regressor with cross-attention between prompt-response and metric embeddings.
Embeddings:
MiniLM (all-MiniLM-L6-v2) for encoding full prompt-response-metric text.
Pre-computed 384-dim embeddings for metric names.

Augmentation:
Pseudo-labeling using a MiniLM-based baseline for high-confidence test predictions.

Training:
Combined supervised + pseudo-labeled data.
Trained using cosine LR scheduler, AdamW optimizer, early stopping.

Evaluation:
RMSE used as the primary metric.
Post-prediction calibration using bin-based score offset correction.
