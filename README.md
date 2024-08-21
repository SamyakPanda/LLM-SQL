# TinyLlama Text2SQL Project

## Introduction

In the realm of Natural Language Processing (NLP), the transformation of natural language queries into SQL statements stands as a captivating challenge known as Text2SQL. The ability to seamlessly convert English questions into complex SQL queries holds immense promise for database management and data analysis. Enter TinyLlama, a variant of the renowned Llama model, poised to tackle this challenge head-on.

This project delves into the fine-tuning of TinyLlama for the generation of SQL statements from natural language queries. Drawing inspiration from the capabilities and versatility of the TinyLlama model, we embark on a journey to harness its power for the realm of database querying.

Our goal is to explore the intricate process of fine-tuning TinyLlama, from setting up the Python environment to downloading and initializing the model. We aim to dissect the nuances of preparing and formatting datasets for training, and delve deep into the fine-tuning process itself. By leveraging TinyLlama, we seek to unlock the potential of generating SQL queries from natural language, paving the way for enhanced data querying experiences and unlocking new avenues for data-driven decision-making.

## Related Work

The field of Natural Language Processing (NLP) has witnessed significant advancements, particularly in the domain of Text-to-SQL (Structured Query Language) conversion. Several works have contributed to this area, aiming to improve the accuracy and efficiency of converting natural language queries into SQL statements.

- **Xiong et al. (2020)** introduced the LLM SQL model, demonstrating promising results in generating SQL queries from natural language questions using large language models pre-trained on extensive text data.
- **Wang et al. (2019)** explored techniques for enhancing Text-to-SQL models through various architectural improvements and training strategies.
- **Zhang et al. (2022)** investigated the application of reinforcement learning techniques to train Text-to-SQL models, aiming to optimize query generation accuracy and efficiency.

While these works have made significant strides, there remains a need for further research to address challenges such as handling complex queries, improving model generalization, and enhancing real-time performance in practical applications.

## Objective

The objective of our project is to build a LLM for generating SQL queries from natural language questions. Users ask questions in natural language, and the system generates answers by converting those questions into SQL queries and executing them on a PostgreSQL database. We use TinyLlama as our open-source LLM for this project.

## Methodology

### 1. SQL Generation with TinyLlama’s LLM Fine-tuning

TinyLlama, a variant of the larger Llama model, is fine-tuned for specialized tasks like generating SQL queries from natural language.

### 2. Setting Up the Environment

- Install necessary libraries using pip or conda.
- Enable GPU acceleration using the CUBLAS library.

### 3. Downloading and Initializing TinyLlama

Download the 8-bit quantized GGUF model of TinyLlama 1.1B from the HuggingFace hub and store the model path.

### 4. Preparing the Dataset for Fine-tuning

Use the `sql-create-context` dataset from Hugging Face. Format the dataset with context (CREATE TABLE statements) and questions.

### 5. Loading the Model in 4-bit Quantization

Convert TinyLlama to a 4-bit quantized format to fit within GPU memory constraints on platforms like Google Colab.

### 6. Fine-tuning TinyLlama

Apply the QLoRA (Quantized Low Rank Adaption) technique for fine-tuning.

### 7. Loading the Trained Model

Combine the fine-tuned PEFT model with the base model for inference.

## Using Our Pretrained Model

### 1. Running Flask App with Google Colab

Expose the Flask app to a public URL from Google Colab.

### 2. Mounting Google Drive and Accessing Files

Mount Google Drive in Colab to access templates and model files.

### 3. Installing Required Libraries For PostgreSQL

Install PostgreSQL on Google Colab using package management commands.

### 4. Configuring PostgreSQL Users and Permissions

Create and configure PostgreSQL user roles for database access.

### 5. Connecting to the Database and Filling It

Connect to the PostgreSQL database, execute SQL commands from files to set up the schema and data.

### 6. Starting Website

Load the dataset and start the Flask website.

### 7. Submitting the Question on the Website

Submit natural language queries via the Flask web interface. The backend processes these queries, generates SQL statements, and executes them against the database.

### 8. Sending the Generated Query to the Database

Execute the generated SQL query and display the result or error message.

### 9. Displaying to the User

Show the query results or error messages to the user.

## Future Improvements

- **Scale and Deployment:** Deploy the website and fine-tune the model with more epochs and a larger dataset using better hardware resources.
- **Resource Optimization:** Address limitations related to running the website on platforms with constrained resources like Google Colab.

## References

- [Running Flask App with Google Colab — by Devesh Surve — Medium](https://deveshsurve.medium.com/running-flask-app-with-google-colab-c9f0c078fb53)
- [Leveraging Google Colab to run Postgres: A Comprehensive Guide](https://dev.to/0xogpg/leveraging-google-colab-to-run-postgres-a-comprehensive-guide-3kpn)
