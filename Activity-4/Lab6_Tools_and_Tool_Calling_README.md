# Lab 6: Tools and Tool Calling with LLMs

## Objective
To understand how Large Language Models interact with tools, execute functions, validate structured inputs, and use tool results to generate responses.

## Technologies Used
- Python 3.12
- LangChain Core
- LangChain Groq
- Pydantic
- JSON
- Open-Meteo weather API
- Jupyter Notebook

## Exercises

1. **Order Status Lookup:** Retrieve a simulated order status using an order ID.
2. **Loan EMI Calculator:** Calculate monthly EMI and total loan payment using structured inputs.
3. **Unit Converter Toolkit:** Convert temperatures and distances using dedicated tools.
4. **Weather Outfit Recommendation:** Use weather information to recommend suitable clothing.
5. **Async Product Stock Checker:** Demonstrate synchronous and asynchronous tool invocation.
6. **Expense Splitter:** Calculate equal expense shares and compare with a manual calculation.
7. **Trip Cost Estimator:** Estimate flights, hotel costs, and food budgets using three tools.
8. **Health Metrics Toolkit:** Calculate BMI and estimate daily calorie requirements.
9. **Smart Meeting Scheduler:** Check simulated availability, retrieve timezone information, and demonstrate a simulated booking.
10. **Restaurant Assistant:** Search a demo restaurant dataset and check ratings, opening schedules, and estimated costs.

## Key Concepts
- LangChain tool definition using `@tool`
- StructuredTool and Pydantic validation
- Binding tools to an LLM
- Inspecting suggested tool calls
- Executing tool functions and using their results
- Synchronous and asynchronous invocation
- Grouping tools into reusable toolkits
- Multi-tool workflows and result verification

## Results
All ten exercises were executed in the notebook. The exercises demonstrate tool execution, structured validation, calculations, and responses based on tool results.

## Limitations
- Order, stock, travel, restaurant, and calendar information is simulated where specified.
- Travel costs and restaurant prices are illustrative, not live quotations.
- The meeting scheduler does not access or modify a real calendar.
- Weather information depends on the external weather API request.
- BMI and calorie results are educational estimates, not medical advice.

## Conclusion
This lab demonstrates how LLMs can use tools to retrieve information, perform calculations, validate inputs, and coordinate functions to answer user requests.
