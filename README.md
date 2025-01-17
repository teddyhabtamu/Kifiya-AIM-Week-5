# Kifiya-AIM-Week-5

## Overview

This project focuses on creating a centralized platform for EthioMart to consolidate real-time data from multiple e-commerce Telegram channels. The platform aims to provide a seamless experience for customers to explore and interact with multiple vendors in one place. The project involves two main tasks:

1. **Data Ingestion and Preprocessing**
2. **Labeling a Subset of Dataset in CoNLL Format**

## Task 1: Data Ingestion and Preprocessing

### Objective

Set up a data ingestion system to fetch messages from multiple Ethiopian-based Telegram e-commerce channels. Prepare the raw data (text, images) for entity extraction.

### Steps

1. **Identify and Connect to Telegram Channels**: Use the `telethon` library to connect to at least 5 relevant Telegram channels and fetch messages.
2. **Implement Message Ingestion System**: Collect text, images, and documents in real-time.
3. **Preprocess Text Data**: Tokenize, normalize, and handle Amharic-specific linguistic features.
4. **Clean and Structure Data**: Separate metadata from message content and store in a structured format.

## Task 2: Label a Subset of Dataset in CoNLL Format

### Objective

Label a portion of the provided dataset in the CoNLL format for Named Entity Recognition (NER) tasks. Identify and label entities such as products, prices, and locations in Amharic text.

### Entity Types

- **B-Product**: The beginning of a product entity.
- **I-Product**: Inside a product entity.
- **B-LOC**: The beginning of a location entity.
- **I-LOC**: Inside a location entity.
- **B-PRICE**: The beginning of a price entity.
- **I-PRICE**: Inside a price entity.
- **O**: Tokens that are outside any entities.

### Steps

1. **Load the Dataset**: Load the dataset containing the messages.
2. **Tokenize and Label**: Tokenize each message and label the tokens according to the specified entity types.
3. **Save in CoNLL Format**: Save the labeled data in a plain text file in the CoNLL format.

## Conclusion

This project sets up a data ingestion system to fetch and preprocess messages from Telegram channels and labels a subset of the dataset in CoNLL format for NER tasks. The labeled data can be used to fine-tune language models for extracting key business entities such as product names, prices, and locations from Amharic text.