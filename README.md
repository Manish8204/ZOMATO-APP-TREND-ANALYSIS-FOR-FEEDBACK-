# 📊 Agentic AI Trend Analysis of Zomato Google Play Reviews

This project implements an **Agentic AI based trend analysis system** that consumes Google Play Store reviews in daily batches and generates a **T-30 to T topic frequency trend report** for the Zomato mobile application.

It addresses the key challenge of **semantic topic duplication** using **high-recall agentic topic deduplication** instead of traditional LDA or BERT topic models.

---

## 🧠 Problem Statement

Product teams receive thousands of user reviews daily, but:

- Similar feedback is written differently  
- Duplicate topics distort trends  
- Emerging issues are missed  

Example:
- “Delivery guy was rude”  
- “Rider misbehaved”  
- “Delivery person behaved badly”  

All of these must map to the same topic → **Delivery partner rude**

---

## 🎯 Solution Overview

The system uses:

| Component | Description |
|--------|-------------|
| Google Play Scraper | Fetches real user reviews daily |
| Sentence Transformers | Converts text into semantic embeddings |
| Agentic Topic Engine | Merges similar topics dynamically |
| High Recall Deduplication | Prevents duplicate categories |
| Trend Matrix Generator | Creates T-30 → T topic frequency table |

---

## 🗓 Input / Output

### Input
- Google Play App ID  
- Target Date (T)

### Output
A trend report table:

| Topic | Aug02 | Aug03 | ... | Aug31 |
|------|------|------|------|------|
| Delivery issue | 32 | 35 | ... | 95 |
| Food stale | 12 | 14 | ... | 49 |
| Refund delay | 8 | 9 | ... | 43 |

Saved as CSV.

---

## 📁 Folder Structure

├── zomato_trend_analyzer.ipynb
├── output/
│ └── zomato_trend_aug_31.csv
├── README.md

---

## ⚙️ How It Works

### Step 1: Fetch Daily Reviews  
Reviews are fetched from Google Play Store for Zomato between **T-30 and T**.

### Step 2: Semantic Topic Deduplication  
Each review is embedded using Sentence Transformers.  
It is matched with existing topic embeddings using cosine similarity.

If similarity < threshold → **new topic is created dynamically**.

### Step 3: Trend Table Generation  
Rows = Topics  
Columns = Dates  
Cells = Topic frequency per day

---

## 🧪 Technologies Used

- Python  
- google-play-scraper  
- sentence-transformers  
- scikit-learn  
- pandas  
- numpy  

---

## ▶️ Video Demonstration

https://drive.google.com/file/d/1Zra4rX3Tzkg8fpSd2TVlvifnoprHULNF/view?usp=sharing

