## Design and Implementation of LangChain Expression Language (LCEL) Expressions

### AIM:
To design and implement a LangChain Expression Language (LCEL) expression that utilizes at least two prompt parameters and three key components (prompt, model, and output parser), and to evaluate its functionality by analyzing relevant examples of its application in real-world scenarios.

### PROBLEM STATEMENT:
To develop a Tamil Music Recommendation Bot using LCEL that suggests songs based on the user's preferred genre and mood.


### DESIGN STEPS:

#### STEP 1:Import the required libraries and load the OpenAI API key.

#### STEP 2:Create a prompt template with two parameters: genre and feel.

#### STEP 3:Initialize the model and output parser, connect them using LCEL, and execute the chain to generate song recommendations.

### PROGRAM:
```
Name: Sairam V
Reg No:212225230237
import os
import openai

from dotenv import load_dotenv, find_dotenv
_ = load_dotenv(find_dotenv()) # read local .env file
openai.api_key = os.environ['OPENAI_API_KEY']
from langchain.prompts import ChatPromptTemplate
from langchain.chat_models import ChatOpenAI
from langchain.schema.output_parser import StrOutputParser

# 1. Prompt Template
prompt = ChatPromptTemplate.from_template(
    "You are a song recondemmention bot {genre} and based on the  {feel} of the person suggest top 3 tamil musics "

)

# 2. Model
model = ChatOpenAI(model="gpt-4.1-mini")

# 3. Output Parser
output_parser = StrOutputParser()

# 4. LCEL Expression
chain = prompt | model | output_parser

# 5. Execute
response = chain.invoke({
    "genre": "classic 90's",
    "feel": "very happy"
})

print(response)
```
### OUTPUT:
<img width="1486" height="423" alt="image" src="https://github.com/user-attachments/assets/d47fc55e-2fd9-43c7-8de9-720bb37afd21" />

### RESULT:
Thus, the Tamil Music Recommendation Bot was successfully designed and implemented using LangChain Expression Language (LCEL). The program uses two prompt parameters (genre and feel) and three key components (Prompt Template, Language Model, and Output Parser) to generate personalized Tamil song recommendations based on the user's preferences
