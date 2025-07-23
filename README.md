# InsightBot - An E-Commerce Chatbot

This repository contains the necessary files and instructions to set up and run an AI-powered chatbot designed to answer questions about e-commerce data. This project was developed as part of the recruitment process by Anarix AI.

## Project Overview

This chatbot uses a Large Language Model (LLM) to analyze hypothetical company data spread across three distinct datasets provided as a part of the assignemnt. When prompted with a relevant question, the chatbot:
* converts the natural language query into an SQL statement
* extracts the required information from the database
* presents both the generated SQL query and the human-readable answer.

## Important Features

* **Natural Language to SQL Conversion:** Utilizes an LLM to translate user questions into SQL queries.
* **Data Extraction:** Fetches relevant information from a SQLite database.
* **Human-Readable Responses:** Presents query results in an easy-to-understand format.
* **Data Analysis:** Includes proper data analysis of the provided data

## Installation and Running the Project (using Google Colab Terminal)

I have executed the entirety of this prpject in **Google Colab**, because of my familiarity with the platform, the fact that Google Collab uses Virtual Ennvironments, and direct integration with Google API key system.

**Steps to set up and run the chatbot:**

1.  **Open a new Google Colab Notebook:**

2.  **Configure Colab Runtime:**
    * In the Colab menu, go to `Runtime` > `Change runtime type`.
    * Under `Hardware accelerator`, select **`T4 GPU`**. This is because for much more complex queries, the presence of GPU can be more computationally efficient. Using the basic        terminal also works well
    * Click `Save`.

3.  **Create the `run_agent.py` file:**
    * Load the run_agent.py script in the google collab. 
    * Run the single cell that is in the file. The presence of `%%writefile run_agent.py` in the code means that it is saved to the temporary stsorage of the notebook, which is          essential for terminal access
    * Run this cell. You will see `Writing run_agent.py` as output, and a `run_agent.py` file will appear in your Colab session's file browser (left sidebar).

4.  **Open the Colab Terminal:**
    * In the Colab menu, go to `Tools` > `Terminal` > `New terminal`. You can also access the terminal using the `terminal` button at the bottom.
    * A new terminal window will open either at the bottom or towards the right.

5.  **Set your Gemini API Key as an Environment Variable:**
    * In the terminal, type the following command and press `Enter`. **Replace `{Insert your API key value here, within quotations only}` with your actual Gemini API key.**
        ```bash
        export GOOGLE_API_KEY="{Insert your API key value here, within quotations only}"
        ```
    * This sets the API key for the current terminal session.

6.  **Run the Chatbot Script:**
    * In the **same terminal window**, type the following command and press `Enter`:
        ```bash
        python run_agent.py
        ```

## Interacting with the Chatbot

Wait till all the installations are ran completely, till you see the `You:` prompt.
* **Type your question** at that prompt and press `Enter`.
* The chatbot will process your request, generate an SQL query, get the answer, and display it in the terminal.
* To **exit** the chatbot, type `exit` and press `Enter`. You can also use the keybinds Ctrl+C(Cmd+C if you are using a macbook)

## Sample Questions to Ask

You can try asking the following questions to test the chatbot's capabilities. The chatbot is, however, not limited to only the below questions.
* `What is my total sales?`
* `Calculate the RoAS (Return on Ad Spend).`
* `Which product had the highest CPC (Cost Per Click)?`
* `How many eligible products are there?`
* `What was the total units ordered on 2023-01-01?`
* `Show me the ad sales for item 12345 on 2023-01-05.`
* `What is the average total sales per eligible product?`
