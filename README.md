# E-commerce Data Chatbot

This repository contains the necessary files and instructions to set up and run an AI-powered chatbot designed to answer questions about e-commerce data. This project was developed as part of the recruitment process by Anarix AI.

## Project Overview

This chatbot leverages a Large Language Model (LLM) to analyze hypothetical company data spread across three distinct datasets (originally Excel sheets, now structured as SQL tables). When prompted with a relevant question, the chatbot intelligently converts the natural language query into an SQL statement, extracts the required information from the database, and presents both the generated SQL query and the human-readable answer.

## Key Features

* **Natural Language to SQL Conversion:** Utilizes an LLM to translate user questions into accurate SQL queries.
* **Data Extraction:** Fetches relevant information from a SQLite database.
* **Human-Readable Responses:** Presents query results in an easy-to-understand format.
* **Modular Design:** Code is structured for clarity and maintainability.

## Technologies Used

* **Python:** The primary programming language.
* **Google Colab:** Cloud-based Python environment for development and execution.
* **Gemini API (Google):** The Large Language Model used for natural language understanding and SQL generation.
* **SQLite:** Lightweight, file-based relational database for data storage.
* **Pandas:** Python library for data manipulation and loading into SQL.

## Installation and Running the Project (using Google Colab Terminal)

This project is designed to run seamlessly within **Google Colab**, leveraging its virtual environment and direct integration with the Gemini API.

**Before you begin:**

1.  Ensure you have a **Google Account** to access Google Colab.
2.  Obtain your **Gemini API Key** from [Google AI Studio](https://aistudio.google.com/apikey). Keep this key secure.

**Steps to set up and run the chatbot:**

1.  **Open a new Google Colab Notebook:**
    * Go to [colab.research.google.com](https://colab.research.google.com/) and create a new notebook.

2.  **Configure Colab Runtime:**
    * In the Colab menu, go to `Runtime` > `Change runtime type`.
    * Under `Hardware accelerator`, select **`T4 GPU`**.
    * Click `Save`. (Note: If you face GPU usage limits, you might need to wait for your quota to reset.)

3.  **Create the `run_agent.py` file:**
    * Copy the **entire content** of your `run_agent.py` script (which contains all the project's code from your Colab notebook) into a **single cell** in your Colab notebook.
    * Add `%%writefile run_agent.py` as the **very first line** of that cell.
    * Run this cell. You will see `Writing run_agent.py` as output, and a `run_agent.py` file will appear in your Colab session's file browser (left sidebar).

4.  **Open the Colab Terminal:**
    * In the Colab menu, go to `Tools` > `Terminal` > `New terminal`.
    * A new terminal window will open at the bottom of your screen.

5.  **Set your Gemini API Key as an Environment Variable:**
    * In the terminal, type the following command and press `Enter`. **Replace `{Insert your API key value here, within quotations only}` with your actual Gemini API key.**
        ```bash
        export GOOGLE_API_KEY="{Insert your API key value here, within quotations only}"
        ```
    * This sets the API key for the current terminal session, allowing the script to authenticate with Gemini.

6.  **Run the Chatbot Script:**
    * In the **same terminal window**, type the following command and press `Enter`:
        ```bash
        python run_agent.py
        ```

## Interacting with the Chatbot

Once the script starts running in the terminal, you will see various messages indicating package installations, database setup, data loading, and LLM initialization. Finally, you will see a `You:` prompt.

* **Type your question** at the `You:` prompt and press `Enter`.
* The chatbot will process your request, generate an SQL query, fetch the answer, and display it in the terminal.
* To **exit** the chatbot, type `exit` and press `Enter`.

## Sample Questions to Ask

You can try asking the following questions to test the chatbot's capabilities:

* `What is my total sales?`
* `Calculate the RoAS (Return on Ad Spend).`
* `Which product had the highest CPC (Cost Per Click)?`
* `How many eligible products are there?`
* `What was the total units ordered on 2023-01-01?`
* `Show me the ad sales for item 12345 on 2023-01-05.`
* `What is the average total sales per eligible product?`
