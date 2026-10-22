# Lab 3 - Prompt Engineering

**Student:** Jatin Kolhapure  
**Roll Number:** SCFP125014  
**Course:** MCA  
**Repository:** `GenAi_LLM_Engineering_SCFP125014`

## Overview

This lab explores practical prompt engineering techniques using a Large Language Model (LLM) through the Groq API.

## Technologies Used

- Python
- Jupyter Notebook
- Groq API
- python-dotenv
- JSON

## Exercises Covered

| Exercise | Topic | Key Work |
|---|---|---|
| 1 | Doctor Summary Generator | Generates structured summaries from patient notes. |
| 2 | Review Classifier | Classifies reviews as Positive, Negative, or Mixed. |
| 3 | Resume Field Extractor | Extracts requested fields in JSON format. |
| 4 | Customer Support Reply Generator | Generates replies within a specified word limit. |
| 5 | Multi-language Translator | Translates text according to the requested formality. |
| 6 | Iterative Content Refiner | Refines a draft over three rounds. |

## How to Run

1. Install the required dependencies:

   `pip install groq python-dotenv`

2. Create a `.env` file in the project root and add your Groq API key:

   `GROQ_API_KEY=your_groq_api_key`

3. Open `Lab3_Prompt_Engineering.ipynb` in Jupyter Notebook.
4. Run the cells sequentially.

## Security Note

Never commit your `.env` file or expose your Groq API key.

## Result

All six exercises were executed and tested using the Groq API with the `openai/gpt-oss-20b` model.
