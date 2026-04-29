# URLA Document Compare

## Project Overview
Compare the data between two URLA documents using OpenAI’s GPT-4o and output the 
results as a two structured output files (one a markdown file and the second as a PDF document).  The URLA documents being uploaded to compare should be in PDF format.  Use a Web frontend UI to be able to upload the two URLA documents.   Also, provide the ability for the end user to choose to compare the entire URLA or just a section of the URLA.   The URLA document stands for Uniform Residential Loan Application.  It is a standard government form used in Mortgage Origination.  It contains Borrowers information for applying for a loan.   

## Use Case
At my company we have two separate Mortgage printing vendors who return this URLA document.  We are still in the process of validating the data the second vendor returns to us.  Currently to do this comparison of data we view each URLA pdf document side by side and manually look at each line of data to make sure the Borrowers’ information is the same. 
Our Team would greatly benefit if we could use AI to do this data compare for us.   We would just upload the two files and have the AI app return to us any differences in an output file for review.  This will save a lot of time.

## Prerequisites
  * Python 3.11 or higher
  * Software needed to create front end web page ( React or similar )
  * OpenAI Account and API Key (GPT-4 Access required)
  * Code Editor ( IDE ) I like to use Vscode, but others like Cursor is a good choice  

## Installation / Setting up Enviornment

 1. Install required packages

    ```bash
    pip install -r requirements.txt
    ```

 2. Requirements.txt file: 

     ```Flask==3.0.0
      Werkzeug==3.0.0
      PyPDF2==4.0.1
      openai==1.3.0
      markdown==3.5.1
      weasyprint==60.0
      ```
     
3. Setup your OpenAI API Key

   ```bash
   export OPENAI_API_KEY='your-api-key-here'  # On Windows, use: set OPENAI_API_KEY=your-api-key-here
   ```  

## AI Features to Be Implemented


## User Interface

<img width="541" height="561" alt="Mock-UI-1" src="https://github.com/user-attachments/assets/054f3fff-ba0d-4d76-9c9f-b54806a0d035" />

<img width="551" height="639" alt="Mock-UI-2" src="https://github.com/user-attachments/assets/869908b0-2cff-4746-99eb-f6e130e4a435" />

## BackEnd

## App Usuage


## Technical Approach

## Examples
 ### testing
   - Screen shots
     
## Evaluation Strategy

## Observability Plan 


