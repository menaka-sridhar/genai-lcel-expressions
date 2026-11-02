## Design and Implementation of LangChain Expression Language (LCEL) Expressions

### AIM:
To design and implement a LangChain Expression Language (LCEL) expression that utilizes at least two prompt parameters and three key components (prompt, model, and output parser), and to evaluate its functionality by analyzing relevant examples of its application in real-world scenarios.

### PROBLEM STATEMENT:
To develop a Python program using LangChain LCEL that accepts two user inputs, processes them through a prompt template, generates a response using an LLM, and displays the result using an output parser.

### DESIGN STEPS:

## STEP 1:
Import the required libraries and load the OpenAI API key using the dotenv package.
## STEP 2:
Create a prompt template with two parameters, such as topic and language.
## STEP 3:
Initialize the ChatOpenAI model with a suitable temperature value.
## STEP 4:
Create an output parser using StrOutputParser to convert the model response into plain text.
## STEP 5:
Connect the prompt, model, and output parser using the LCEL pipe operator (|).
## STEP 6:
Pass the input values to the chain using invoke() and display the final output.

### PROGRAM:
```
import os
from dotenv import load_dotenv
load_dotenv()

from langchain_core.prompts import ChatPromptTemplate
from langchain_openai import ChatOpenAI
from langchain_core.output_parsers import StrOutputParser

# Prompt
prompt = ChatPromptTemplate.from_template(
    "Explain {topic} for {audience} with an example."
)

# Model
model = ChatOpenAI(model="gpt-4o-mini", temperature=0)

# Output Parser
output_parser = StrOutputParser()

# LCEL Chain
chain = prompt | model | output_parser

# Input
topic = input("Enter topic: ")
audience = input("Enter audience: ")

# Execute
result = chain.invoke({
    "topic": topic,
    "audience": audience
})

# Output
print(result)

```
### OUTPUT:
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/3712e383-86bc-47d7-b775-b5153727c822" />

### RESULT:
Thus, the LangChain Expression Language (LCEL) program was successfully implemented using two prompt parameters and three components: Prompt, Model, and Output Parser. The system generated responses successfully using the LLM.
