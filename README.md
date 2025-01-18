# LLM Fine-Tuning for Healthcare


### Dataset

We utilize the Doctor-HealthCare-100k dataset, a high-quality dataset of healthcare conversations. This dataset enables fine-tuning NLP models to generate empathetic, professional, and contextually accurate responses in the medical domain.

Link to dataset: https://www.kaggle.com/datasets/divyanshu2000/doctor-healthcare-100k


### Project Overview

This project focuses on fine-tuning a GPT-based language model using the Doctor-HealthCare-100k dataset. The goal is to create a model capable of simulating professional doctor-patient conversations. The model generates empathetic and informative responses to health-related queries while adhering to medical safety and ethical guidelines.

The notebook includes:

- Data Loading and Preprocessing: Handling missing values, selecting relevant columns, and converting the data into a Hugging Face Dataset.
- Model Fine-Tuning: Leveraging Hugging Face's Trainer API to fine-tune the distilgpt2 model.
- Example usage: Demonstrating the model's ability to generate responses to sample input.


### Workflow
Step 1: Import Libraries
- Following libraries were used:

  -  pandas and numpy for data handling
  - torch for leveraging GPU acceleration
  - transformers and datasets from Hugging Face for model training and dataset management

Step 2: Load and Preprocess the Dataset
- Loaded the dataset using Pandas.
- Retained only the input and output columns, which represent user queries and doctor responses.
- Handled missing values by removing incomplete records.
- Converted the cleaned dataset into a Hugging Face Dataset and split it into training and testing subsets (90%-10%).

Step 3: Tokenize and Prepare Data
- Tokenized the dataset using the GPT2 tokenizer with padding and truncation.
- Prepared inputs and outputs in a format compatible with GPT2 by appending end-of-sequence tokens (eos_token) and applying consistent padding.

Step 4: Fine-Tune the Model
- Used distilgpt2 (a lightweight GPT2 variant) as the base model.
- Configured training parameters.
- Enabled mixed-precision training (FP16) to speed up training on GPUs.

Step 5: Save Fine-Tuned Model
- Saved the fine-tuned model and tokenizer for future use.
  
Step 6: Generate Responses
- Reloaded the model and tokenizer.
- Developed a system prompt to guide the model in generating professional, empathetic responses.
- Tested the model using real examples from the test dataset.


### Example Usage

Generate a Response

To use the fine-tuned model, you can pass a query and receive a response:
```
# Sample Input
user_query = "Im constantly plagued with mouth ulcers and tongue ulcers and feel as if my tongue is swollen, when I lay down my mouth constantly fills with saliva and I constantly have to swallow its  most annoying and I have to try to sleep with my neck up in the air.  My ears are painful too, this is ongoing condition"

# Generate Response
response = generate_response(user_query)
print(response)
```
Expected output:
```
Thanks for your question on Chat Doctor. I can understand your concern. In my opinion, you should consult an ENT specialist and get done clinical examination of your mouth. If you require more of my help in this aspect, I will be happy to help you further. Please do not hesitate to ask in case of any further doubts. Wishing you good health.
```
