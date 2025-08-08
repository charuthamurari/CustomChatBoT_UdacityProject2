# Build Your Own Custom Chatbot

## 📌 Project Overview
This project demonstrates how to build a **custom OpenAI-powered chatbot** using only basic packages like `openai` and `pandas`—without relying on frameworks such as LangChain. The goal is to gain a deeper understanding of how chatbots work **"under the hood"** by manually integrating a dataset into a chatbot workflow.

## 🎯 What You Will Build
- A chatbot powered by OpenAI that answers questions based on a **custom dataset**.
- A fully manual retrieval + prompt injection system.
- Two Q&A demonstrations: **before** and **after** dataset integration.

## 📂 Dataset Selection
For this project, we use `character_descriptions.csv` from the provided dataset directory.  
- **Why this dataset?** It contains fictional character descriptions from theater, TV, and films, making it ideal for context-based Q&A where character details matter.
- Each row includes: `name`, `description`, `medium`, `setting`.

This dataset allows the chatbot to provide **rich, specific answers** that the base model might not know, ensuring visible improvement when custom context is applied.

## 🛠 Data Wrangling
- Loaded CSV data using **pandas**.
- Cleaned unnecessary whitespace and normalized column names.
- Stored descriptions in a **searchable list** for retrieval.
- Created a basic keyword-based search function to match queries with relevant dataset entries.

## 🔍 Custom Context-Based Retrieval Logic
1. **Keyword Matching:** Extract keywords from the user query.
2. **Dataset Search:** Match keywords with `name` and `description` fields.
3. **Context Injection:** Pass the matched dataset row as context into the OpenAI prompt.
4. **Response Generation:** OpenAI generates a response enriched with dataset-specific information.

## 🧪 Sample Q&A Tests

### Without Context
**Q:** Who is Arion Velasquez?  
**A:** Sorry, I don't have information about that character.

### With Context
**Q:** Who is Arion Velasquez?  
**A:** Arion Velasquez is a fearless skyship captain from the steampunk city of Aetherfall, known for her tactical genius and mechanical expertise in airship battles.

## 📜 Requirements
- Python 3.8+
- `openai`
- `pandas`

## 🚀 How to Run
```bash
pip install openai pandas
python chatbot.py
