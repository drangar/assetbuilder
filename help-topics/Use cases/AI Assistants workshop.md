# Build an AI Assistant in watsonx.ai
In this lab you will learn how to build a simple AI Assistant in watsonx.ai. We will expand on the concepts that you learned in the Introduction to Generative AI lab. 

# AI Assistant Architecture
Most users are familiar with AI Assistants, applications that can perform a variety of generative AI tasks. Examples of general-purpose AI assistants include ChatGPT and Google Gemini. These assistants include several application layers and various components in addition to Large Language Models (LLMs). The development of these applications was completed by large teams over several months. However, despite the significant development effort required to create commercial general-purpose assistants, it’s also possible to build a prototype of an AI Assistant in a short timeframe.
To build a useful prototype, we need to clearly define its scope. Instead of creating a generic AI assistant, we can start with one that focuses on a few tasks, such as question answering within a specific domain, code generation, or content generation.
Even though we’re building a prototype, we should design an architecture that allows for easy addition of new features necessary for preparing the application for production deployment.
An AI Assistant application architecture should
•	Include at least 3 application layers: the UI layer, the business logic layer, and the data layer
•	Have an architecture that allows to replace LLMs without affecting the rest of the code
•	Have a prompt management strategy. 

<img width="273" alt="image" src="https://github.com/user-attachments/assets/d3b13ec4-9f2f-433a-98de-1826d1f776f9" />

Let’s take a closer look at each one of the requirements. 

The UI application layer of an AI Assistant can be written in several programming languages using different frameworks. The most popular programming languages for implementation of an AI Assistant UI are Python and JavaScript. In Python, developers often choose Streamlit and Chainlit frameworks, and for our prototype of AI Assistant we will use Streamlit. 

The business logic layer of the application should implement the following tasks:
•	Invocation of LLMs
•	Invocation of machine learning models
•	Business rules
•	Validation
•	Orchestration of the application flow.

In our prototype we will implement invocation of LLMs and orchestration. 

Finally, the data layer should perform all tasks that are related to working with data, for example:
•	Saving user prompts and LLM responses
•	Retrieving data from a vector database for RAG use cases
•	Retrieving structured data from a database.

# AI Assistant Prototype
In this lab we will build a general purpose IT professional AI Assistant with the following features:

•	UI layer: Streamlit
•	Business logic:
o	LLMs: llama3 and codellama
o	Tasks:
	Request (prompt) classification: determine if the prompt is a general question or a programming question
	General purpose content generation
	Programming tasks
o	Basic memory management

# Part 1: Review and test the UI layer
1.	Execute the "AI assistants workshop: UI echo check" task.
2.	Let’s review code. 
•	In the get_credentials() function we retrieve variables from the .env file which we will pass to the business logic layer. 
 <img width="400" alt="image" src="https://github.com/user-attachments/assets/f1d63315-ee7f-4667-a5b7-c65249e685b9" />

•	In the main() function we set up the UI and have a placeholder for invoking LLM inference. We will uncomment this code later in the lab. 
<img width="424" alt="image" src="https://github.com/user-attachments/assets/c365d7da-af19-47b4-9684-9a7d25f02537" />

3.	Test the AI Assistant by sending a few prompts. Notice that in our test we simply echo the input.
<img width="334" alt="image" src="https://github.com/user-attachments/assets/feae776b-9fc2-4327-a0ab-183e86919bd8" />

# Part 2: Develop and Deploy Prompts 
1.	Execute the "AI assistants workshop: Generic question prompt" task.
Since we already developed and deployed prompt templates in the Introduction to Generative AI hands-on lab, we will provide high-level steps in this section.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/eb2d3d26-dcff-4817-8d61-351f37c15db6" />

10.	Load the following watsonx_engine.py from the lab repo/Scripts folder into your Python IDE.
Let’s review the code. 
In this module, we encapsulated the code to invoke prompt templates. Since we parameterized the invoke_prompt_template() function, it can be used from many layers of the application. All variables required by this function will be retrieved by the UI layer of the application and passed in. In our AI Assistant, all user prompts captured from the UI are passed in as the task variable. As you’ve seen during prompt testing, the "task" is attached to the default prompt instructions.
<img width="408" alt="image" src="https://github.com/user-attachments/assets/77d81572-9c11-4a88-8f34-59238d01fb1f" />



