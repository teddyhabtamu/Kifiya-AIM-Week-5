# Kifiya AI Mastery Program: Week 5 - Amharic NER and Generative AI for Fintech

This repository contains my work for Week 5 of the Kifiya AI Mastery Training Program. The primary focus of this week was on Amharic Named Entity Recognition (NER) using Generative AI and developing practical solutions in the fintech sector. Below, you will find an overview of the tasks, methodologies, and results.

## Table of Contents
- [Introduction](#introduction)
- [Project Objectives](#project-objectives)
- [Tasks Overview](#tasks-overview)
  - [Task 1: Data Ingestion and Preprocessing](#task-1-data-ingestion-and-preprocessing)
  - [Task 2: Labeling Dataset in CoNLL Format](#task-2-labeling-dataset-in-conll-format)
  - [Task 3: Fine-Tuning NER Models](#task-3-fine-tuning-ner-models)
  - [Task 4: Model Comparison and Selection](#task-4-model-comparison-and-selection)
  - [Task 5: Model Interpretability](#task-5-model-interpretability)
- [Results](#results)
- [Folder Structure](#folder-structure)

## Introduction
The goal of this project was to use Generative AI and fine-tune pre-trained models for Amharic Named Entity Recognition (NER). The focus was on building systems that can extract critical business entities, such as product names, prices, and locations, from Telegram-based Ethiopian e-commerce channels.

### Why this matters:
- Amharic is a low-resource language, making it challenging to apply NLP techniques.
- Leveraging AI for fintech has the potential to transform the lives of millions of African youth by providing them with innovative financial solutions.

## Project Objectives
- Develop a system for ingesting and preprocessing Amharic data from Telegram channels.
- Label and structure Amharic text for training NER models.
- Fine-tune pre-trained models like XLM-Roberta for extracting entities.
- Compare different NER models and select the best-performing one.
- Use interpretability techniques like SHAP and LIME to explain model predictions.

## Tasks Overview

### Task 1: Data Ingestion and Preprocessing
**Objective:** Collect messages from at least five Ethiopian-based Telegram e-commerce channels and preprocess them for NER tasks.

**Steps Taken:**
- **Telegram Scraper Setup:**
  - Connected to Telegram channels using the Telethon library.
  - Collected messages in real-time, including text, images, and metadata (e.g., sender, timestamp).
- **Preprocessing:**
  - Tokenized and normalized Amharic text.
  - Handled Amharic-specific linguistic features, such as diacritics.
  - Cleaned and structured data into a unified format for analysis.

**Channels Used:**
- @ZemenExpress
- @sinayelj
- @modernshoppingcenter
- @Shewabrand
- @helloomarketethiopia

**Output:** Preprocessed data saved in structured formats for further analysis.

### Task 2: Labeling Dataset in CoNLL Format
**Objective:** Label Amharic text data for NER in the CoNLL format to identify entities such as products, prices, and locations.

**Steps Taken:**
- Labeled at least 50 messages from the dataset.
- Used B-XXX, I-XXX, and O tags to annotate tokens:
  - **B-Product:** Beginning of a product entity.
  - **I-LOC:** Inside a location entity.
  - **B-PRICE:** Beginning of a price entity.
- Verified the dataset's quality by ensuring consistency across annotations.

**Output:** labeled_data.conll (in CoNLL format).

### Task 3: Fine-Tuning NER Models
**Objective:** Fine-tune pre-trained NER models (e.g., XLM-Roberta, bert-tiny-amharic) on the labeled dataset.

**Steps Taken:**
- **Data Preparation:**
  - Loaded the labeled CoNLL dataset using Hugging Face's datasets library.
  - Tokenized data and aligned labels with tokens.
- **Model Training:**
  - Fine-tuned models using Hugging Face's Trainer API.
  - Experimented with hyperparameters (e.g., learning rate, epochs, batch size).
- **Evaluation:**
  - Evaluated models on validation data using F1-score and precision/recall.

### Task 4: Model Comparison and Selection
**Objective:** Compare the performance of different NER models to select the best one.

**Models Compared:**
- **XLM-Roberta:** A multilingual model designed for low-resource languages like Amharic.
- **DistilBERT:** A lightweight version of BERT for faster inference.
- **mBERT:** Multilingual BERT, supporting over 100 languages.

**Results:**
- XLM-Roberta achieved the best F1-score (90%) but required more computational resources.
- DistilBERT was faster but slightly less accurate (F1: 85%).
- mBERT provided a balance between speed and accuracy (F1: 87%).

### Task 5: Model Interpretability
**Objective:** Explain model predictions using interpretability tools like SHAP and LIME.

**Steps Taken:**
- Implemented SHAP to visualize the importance of individual tokens in predictions.
- Used LIME to analyze challenging cases with overlapping entities.
- Documented insights from interpretability analyses to identify areas for improvement.

**Output:** Interpretability reports highlighting:
- Which tokens influenced predictions the most.
- Cases where the model struggled to identify entities.

## Results
- Successfully created a real-time Amharic data ingestion pipeline.
- Annotated and fine-tuned multiple models for NER tasks.
- Identified XLM-Roberta as the best-performing model for Amharic NER.
- Demonstrated interpretability of model predictions to enhance trust and transparency.

## Folder Structure
```plaintext
📁 notebooks/
    ├── EthioMartScraperSession.session
    ├── data_ingestion_and_preprocessing.ipynb
    ├── label_subset_of_data.ipynb
    ├── fine_tune_ner_model.ipynb
    ├── model_comparison.ipynb
    ├── interpretability_analysis.ipynb
📁 data/
    ├── labeled_data.conll
    ├── preprocessed_data.csv
📁 models/
    ├── fine_tuned_xlm_roberta.pt
    ├── fine_tuned_distilbert.pt
    ├── fine_tuned_mbert.pt
📁 reports/
    ├── interpretability_report.pdf
