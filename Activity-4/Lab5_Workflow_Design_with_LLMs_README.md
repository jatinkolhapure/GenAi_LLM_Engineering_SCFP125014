# Lab 5 - Workflow Design with LLMs (Prompt Templates & Output Parsers)

**Student:** Jatin Sandip Kolhapure  
**Roll Number:** SCFP125014  
**Program:** MCA  
**Subject:** Generative AI / LLM Engineering

## Overview

This lab demonstrates how to build multi-step LLM workflows with LangChain. Each workflow uses prompt templates to guide the model, output parsers to convert responses into usable values, and sequential steps that pass parsed results forward.

## Learning Objectives

- Use `PromptTemplate` and `ChatPromptTemplate` to structure LLM instructions.
- Use `PydanticOutputParser` to extract and validate structured data.
- Use `StrOutputParser` when the next output should be readable text.
- Connect prompt, model, and parser components into reusable pipelines.
- Pass structured results between steps rather than repeatedly processing the original input.
- Combine LLM workflows with external data, including weather information retrieved from the Open-Meteo API.

## Exercises Included

### Exercise 1 - Customer Review to Support Ticket
Extracts the complaint, product or feature, and sentiment from a customer review. The extracted information is then used to write a concise support ticket.

### Exercise 2 - Research Abstract to Layperson Summary
Extracts the research question, method, and key finding from an abstract, then turns those details into a plain-language summary while retaining important limitations.

### Exercise 3 - Interview Transcript to Candidate Scorecard
Extracts interview question-and-answer pairs, evaluates requested skills using evidence from the transcript, and produces a structured scorecard with an overall recommendation.

### Exercise 4 - Outdoor Event Plan to Weather-Adjusted Recommendation
Extracts event details, retrieves weather data from Open-Meteo, normalizes the weather information, and generates a recommendation that considers conditions and practical precautions.

### Exercise 5 - Support Chat Log to Escalation Report
Identifies the issue, customer tone, and resolution attempts; checks whether essential escalation details are missing; and prepares an evidence-based escalation report.

### Exercise 6 - Workout Goal to Weekly Plan
Extracts a person's goal, experience level, available days, and equipment access, then creates a structured seven-day plan using the extracted details.

## Tools and Libraries

- Python
- LangChain Core
- LangChain Groq integration
- Groq-hosted LLM (`openai/gpt-oss-20b`)
- Pydantic
- `python-dotenv`
- `requests`
- Open-Meteo geocoding and forecast APIs (Exercise 4)

## Setup

Use the Python environment associated with the project and install the required packages if they are not already installed:

```bash
pip install langchain-core langchain-groq pydantic python-dotenv requests
```

Create a `.env` file in the project root and add your own Groq API key:

```text
GROQ_API_KEY=your_groq_api_key_here
```

Replace the placeholder with your own key. **Do not commit or upload the `.env` file, API keys, or other credentials to GitHub.**

## Run the Notebook

1. Open `Lab5_Workflow_Design_with_LLMs.ipynb` in Jupyter Notebook or VS Code.
2. Ensure the required packages are installed and the `.env` file is configured.
3. Select **Restart Kernel and Run All Cells**.
4. Confirm that each exercise completes and that the structured outputs pass validation.
5. Review the generated outputs before submitting the notebook.

Exercise 4 requests current forecast data from Open-Meteo, so its result can vary depending on the event location, date, and API response. Weather forecasts are estimates and should be checked again when making real event decisions.

## Key Concepts Demonstrated

- Prompt templates and role-based chat prompts
- Structured extraction with Pydantic schemas
- Readable text generation with string output parsing
- Sequential, multi-step LLM pipelines
- Validation of model-generated structured data
- Evidence-based evaluation and recommendations
- Integration of an external API into an LLM workflow

## References

- [LangChain PromptTemplate reference](https://reference.langchain.com/python/langchain-core/prompts/prompt/PromptTemplate)
- [LangChain PydanticOutputParser reference](https://reference.langchain.com/python/langchain-core/output_parsers/pydantic/PydanticOutputParser)
- [Open-Meteo API documentation](https://open-meteo.com/en/docs)

---

**Notebook:** `Lab5_Workflow_Design_with_LLMs.ipynb`  
**Submission folder:** `Activity-4`
