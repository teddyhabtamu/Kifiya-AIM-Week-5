# Notebooks Folder

This folder contains key resources and scripts related to the **EthioMart** project. The goal of the project is to create a centralized e-commerce hub by extracting and processing data from Telegram channels. The contents of this folder are critical for data ingestion, preprocessing, and labeling tasks.

---

## Contents

### 1. `EthioMartScraperSession.session`
- **Purpose**:  
  This file contains session data for the **Telegram Scraper** used to connect to and interact with Telegram channels. It is essential for maintaining an authenticated connection to Telegram.

- **Usage**:  
  - This session file allows the scraper to fetch data without requiring re-authentication on every run.
  - Ensure this file is stored securely and not shared publicly to prevent unauthorized access to the Telegram API.

---

### 2. `data_ingestion_and_preprocessing.ipynb`
- **Purpose**:  
  This notebook implements the **data ingestion and preprocessing pipeline** for the project.

- **Key Features**:
  1. **Data Ingestion**:
     - Connects to Telegram channels using the `Telethon` library.
     - Fetches messages, images, and metadata in real-time.
     - Channels targeted include:
       - `@ZemenExpress`
       - `@sinayelj`
       - `@modernshoppingcenter`
       - `@Shewabrand`
       - `@helloomarketethiopia`
  2. **Preprocessing**:
     - Tokenizes, normalizes, and handles Amharic-specific linguistic features.
     - Structures raw messages into a clean format, separating metadata (e.g., sender, timestamp) from content.
  3. **Output**:
     - Processes and saves the cleaned data in a structured format for further analysis.

---

### 3. `Label_subset_of_data.ipynb`
- **Purpose**:  
  This notebook is responsible for **labeling a subset of the dataset** in the **CoNLL format**, which is a standard for Named Entity Recognition (NER) tasks.

- **Key Features**:
  1. **Entity Labeling**:
     - Identifies and labels entities such as:
       - **B-Product**: Beginning of a product entity.
       - **I-Product**: Inside a product entity.
       - **B-LOC**: Beginning of a location entity.
       - **I-LOC**: Inside a location entity.
       - **B-PRICE**: Beginning of a price entity.
       - **I-PRICE**: Inside a price entity.
       - **O**: Outside any entity.
  2. **Output**:
     - Labels at least 30-50 messages in the dataset.
     - Saves the results in a plain text file formatted in CoNLL style.

---

## How to Use

1. **Data Ingestion**:
   - Run `data_ingestion_and_preprocessing.ipynb` to connect to the specified Telegram channels and fetch real-time messages.
   - Process the data into a clean, structured format for analysis.

2. **NER Labeling**:
   - Open `Label_subset_of_data.ipynb` to label a subset of the dataset.
   - Save the labeled data for fine-tuning NER models.

3. **Session Authentication**:
   - The `EthioMartScraperSession.session` file ensures smooth reconnection to Telegram during data scraping.
   - Do not delete or modify this file unless re-authentication is required.

---

## Future Work
- Expand the data ingestion system to support more channels and formats (e.g., images).
- Automate the labeling process using a pre-trained NER model to accelerate dataset creation.
- Integrate the labeled dataset into fine-tuning pipelines for Amharic-specific LLMs.

---

## Notes
- Always ensure that sensitive session files like `EthioMartScraperSession.session` are not shared publicly.
- Use labeled data to improve the performance of downstream tasks such as NER and entity extraction.

---

## License
This project is under the [MIT License](../LICENSE).

