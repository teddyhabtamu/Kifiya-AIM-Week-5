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

### Code Example

```python
import os
import asyncio
from telethon import TelegramClient

api_id = 'YOUR_API_ID'
api_hash = 'YOUR_API_HASH'
phone = 'YOUR_PHONE_NUMBER'

client = TelegramClient('EthioMartScraperSession', api_id, api_hash)

async def main():
    await client.start(phone)
    channel = 'channel1'  # Replace with the desired channel
    async for message in client.iter_messages(channel):
        if message.text:
            save_text(message)
        if message.media:
            save_media(message)

def save_text(message):
    with open('messages.txt', 'a') as f:
        f.write(f"{message.sender_id}\t{message.date}\t{message.text}\n")

def save_media(message):
    path = f"media/{message.sender_id}_{message.date}"
    os.makedirs(path, exist_ok=True)
    message.download_media(file=path)

# Run the main function
asyncio.run(main())