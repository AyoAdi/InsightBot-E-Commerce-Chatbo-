# InsightBot - An E-Commerce Chatbot

This repository has the necessary files and instructions to set up and run the chatbot designed to answer questions about e-commerce data.

## Project Overview

This chatbot uses a Large Language Model (LLM) to analyze company data spread across three distinct datasets provided as a part of the assignemnt. When prompted with a relevant question, the chatbot:
* converts the natural language query into an SQL statement
* extracts the required information from the database
* presents both the generated SQL query and the human-readable answer.

## Installing and Running the Project

I have executed the entirety of this prpject in **Google Colab**, because of my familiarity with the platform, the fact that Google Collab uses Virtual Ennvironments, and direct integration with Google API Key system.

**Steps to set up and run the chatbot:**

1.  Open a new Google Colab Notebook

2.  Set up the Colab envionment:
    * Set the runtime for the file. This usually happens automatically
    * For much more complex queries,which can be more computaitonally intense, using GPU can be a much better option. Hence, change it to t4 in the runtime settings, which is much       preferable for this project
      
      <img src="https://github.com/user-attachments/assets/459f8ef5-1758-4e02-ac3d-ee1ce164c2ec" alt="image" width="500px"/>
      
    * Click `Save`.

3.  **Working with `run_agent.py` file:**
    * Load the run_agent.py script in the google collab.
    * Run the single cell that is in the file. The presence of `%%writefile run_agent.py` in the code means that it is saved to the temporary stsorage of the notebook, which is essential for terminal access
    * Run this cell. You will see `Writing run_agent.py` as output, and a `run_agent.py` file will appear in your Colab session's file browser (left sidebar).
      
      <img src="https://github.com/user-attachments/assets/63ba1f3e-c6c6-4cd4-a364-3cf4b04ca0f6" alt="image" width="500px">

4.  **Open the Colab Terminal:**
    * In the Colab menu, go to `Tools` > `Terminal` > `New terminal`. You can also access the terminal using the `terminal` button at the bottom.
      
      <img src="https://github.com/user-attachments/assets/251785fd-bd93-458c-906b-930de69ee9f5" alt="image" width="500px">
   
    * A new terminal window will open either at the bottom or towards the right.
      
      <img src="https://github.com/user-attachments/assets/8835d9cf-b40f-4f50-8897-b7370c693830" alt="image" width="500px">

5.  **Set your Gemini API Key as an Environment Variable:**
    * In the terminal, type the following command and press `Enter`. **Replace `{Insert your API key value here, within quotations only}` with your actual Gemini API key.**
        ```bash
        export GOOGLE_API_KEY="{Insert your API key value here, within quotations only}"
        ```
        
      <img src="https://github.com/user-attachments/assets/30105c9f-0b63-4b7d-86eb-7b09ecbbeff3" alt="image" width="500px">
      
    * Note that the API key should be set as your secret key in the google collab environment
      
      <img src="https://github.com/user-attachments/assets/1cb3b502-45d5-4ada-88cf-3414ca48307e" alt="image" width="500px">
      
    * This sets the API key for the current terminal session.
    * If you don't know how to generate your own API key, refer to the vidoe link I have provided down below:
      ```bash
      https://www.youtube.com/watch?v=6BRyynZkvf0
      ```

6.  **Run the Chatbot Script:**
    * In the **same terminal window**, type the following command and press `Enter`:
        ```bash
        python run_agent.py
        ```

## Interacting with the Chatbot

* Wait till all the installations and dependencies are run completely, till you see the `You:` prompt.

  <img src="https://github.com/user-attachments/assets/197aa19d-4c92-40c9-9d39-ae9b4c28e919" alt="image" width="500px">
  
* **Type your question** at that prompt and press `Enter`.
* The chatbot will process your request, generate an SQL query, get the answer, and display it in the terminal.
  
  <img src="https://github.com/user-attachments/assets/3d82faa3-24ff-47f3-b451-a2bff34bcdde" alt="image" width="500px">
  
* To **exit** the chatbot, type `exit` and press `Enter`. You can also use the keybinds `Ctrl+C`(`Cmd+C` if you are using a macbook)

## Sample Questions to Ask

You can try asking the following questions to test the chatbot's capabilities. The chatbot is, however, not limited to only the below questions.
* `What is my total sales?` (Provided in the assignment)
* `Calculate the RoAS (Return on Ad Spend).` (Provided in the assignment)
* `Which product had the highest CPC (Cost Per Click)?` (Provided in the assignment)
* `How many eligible products are there?`
* `What was the total units ordered on 2023-01-01?`
* `Show me the ad sales for item 12345 on 2023-01-05.`
* `What is the average total sales per eligible product?`
