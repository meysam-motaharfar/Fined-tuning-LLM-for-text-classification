Fine tuning LLM for text classification
===============================================

AUTHORS: Meysam Motaharfar 

# Table of Contents
1. [Project Overview](#Project-Overview)
3. [Dataset](#Dataset-Source-And-Overview)
4. [Models Fine-Tuned](#Models-Fine-Tuned)
6. [Evaluation Metric](#Evaluation-Metric)
7. [Results & Summary](#Results-&-Summary)

# Project Overview

The goal of this project is to evaluate the performance of several large language models (LLMs) on multi-class text classification tasks using subsets of the GoEmotions dataset. The study explores how model performance varies with:

The number of emotion labels (2, 4, 8, 16),

The number of training samples per dataset (800, 1600, 2400), and

The choice of pre-trained language models.

# Dataset

The base dataset is GoEmotions — a human-annotated dataset of 58k Reddit comments labeled for 27 emotion categories.
For this project:

A total of 12 balanced subsets were created.

Each subset represents a specific configuration of:

Label classes: 2, 4, 8, or 16

Training samples: 800, 1600, or 2400 samples

This results in a systematic grid of classification tasks to evaluate model generalization in low- to mid-resource regimes.

# Models Fine-Tuned

Four different pre-trained LLMs were fine-tuned for each dataset configuration:

Qwen 2.5

LLaMA 3.2

GPT-2 XL

Gemma 3

Each model was fine-tuned using standard supervised training with appropriate tokenization, classification heads, and early stopping based on validation performance.

# Evaluation Metric

The primary evaluation metric was accuracy, calculated on held-out validation sets for each dataset. The metric offers insight into how well each model differentiates between varying numbers of emotional categories.

# Results & Summary

As expected, accuracy decreases as the number of label classes increases, due to increased classification difficulty.

LLaMA 3.2 and Qwen 2.5 generally outperform GPT-2 XL across most settings, especially in high-label/low-sample regimes.

Model performance stabilizes with more data (2400 samples), but degradation is still observed for 16-class classification.

A heatmap of model performance across datasets reveals the relative robustness of models under varying levels of complexity and training data.

![performance](performance.png)


