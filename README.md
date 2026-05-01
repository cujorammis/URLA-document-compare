# URLA Document Compare

## Project Overview
Compare the data between two URLA documents using OpenAI’s GPT-4o and output the 
results as a two structured output files (one a markdown file and the second as a PDF document).  The URLA documents being uploaded to compare should be in PDF format.  Use a Web frontend UI to be able to upload the two URLA documents.   Also, provide the ability for the end user to choose to compare the entire URLA or just a section of the URLA.   The URLA document stands for Uniform Residential Loan Application.  It is a standard government form used in Mortgage Origination.  It contains Borrowers information for applying for a loan.   

## Use Case
At my company we have two separate Mortgage printing vendors who return this URLA document.  We are still in the process of validating the data the second vendor returns to us.  Currently to do this comparison of data we view each URLA pdf document side by side and manually look at each line of data to make sure the Borrowers’ information is the same. 
Our Team would greatly benefit if we could use AI to do this data compare for us.   We would just upload the two files and have the AI app return to us any differences in an output file for review.  This will save a lot of time.

## Prerequisites
  * Python 3.11 or higher
  * OpenAI Account and API Key (GPT-4 Access required)
  * Code Editor ( IDE ) I like to use Vscode, but others like Cursor is a good choice  

## AI Features to Be Implemented

  1. Prompt engineering - Two prompts in the UI.  1. Compare entire document.  Or  2. Compare only a section.
     - These prompts are requried because the App needs the two documents to do the compare.
  3. Structured outputs - The compare results are structured and returned in a JSON file
     - Output required and relevant because user needs to view the compare results.

## Installation / Setting up Enviornment

 1. Install required packages

    ```bash
    pip install -r requirements.txt
    ```

 2. Requirements.txt file: 

     ```
      Flask==3.0.0
      Werkzeug==3.0.0
      PyPDF2==4.0.1
      openai==1.3.0
      ```
     
4. Setup your OpenAI API Key

   ```bash
   export OPENAI_API_KEY='your-api-key-here'  # On Windows, use: set OPENAI_API_KEY=your-api-key-here
   ```  

## Technical Approach

  * UI / Front End
    1. Create a font end Web Interface to allow two URLA Documents to be uploaded for comparison.
    2. Also, ask if the user wants to compare the entire document or just one section of the URLA.
    3. Use Flask and Werkzeug to allow the Web Inteerface interact with Python
    4. See screen shot example in Example Prompts & Output 


  * BackEnd
    1.  Create python program(s) to compare the two uploaded URLA documents 
    2.  Using OpenAI and PyPDF2, do the File compares and return compare results in a JSON structured file
        
## Example Prompts & Output

   - Enter the first URLA pdf file in Documet A: Choose File and the second one to compare in Document B: Chosse in the UI web page
   - Choose to compare entire document OR just a section of the URLA Document
   - NOTE:  After uploading each URLA document it should show the file name to the right of the choose file button.

     <img width="300" height="350" alt="Mock-UI-1" src="https://github.com/user-attachments/assets/054f3fff-ba0d-4d76-9c9f-b54806a0d035" />

   - Example output

    ```json{
  "report_generated": "2026-05-01T14:32:18.456789",
  "document_a": "URLA_Form_1.pdf",
  "document_b": "URLA_Form_2.pdf",
  "comparison_results": {
    "compare_mode": "entire",
    "timestamp": "2026-05-01T14:32:18.456789",
    "document_a_pages": 5,
    "document_b_pages": 5,
    "gpt4_analysis": {
      "summary": "The two URLA documents contain 7 differences.",
      "total_differences": 7,
      "differences": [
        {
          "field_or_section": "Borrower Name",
          "document_a": "John Michael Smith",
          "document_b": "John M. Smith",
          "significance": "low",
          "explanation": "Minor formatting difference in the borrower's middle name - full name vs. initial. This is likely a data entry variation and does not affect the loan application substantively."
        },
        {
          "field_or_section": "Co-Borrower Present",
          "document_a": "Yes",
          "document_b": "No",
          "significance": "high",
          "explanation": "Critical difference: One document indicates a co-borrower is present while the other does not. This significantly affects loan qualification and documentation requirements."
        },
        {
          "field_or_section": "Property Street Address",
          "document_a": "1425 Oak Ridge Drive",
          "document_b": "1425 Oak Ridge Drive, Unit 4B",
          "significance": "medium",
          "explanation": "The second document includes unit information that is absent from the first. This could indicate updated or corrected property identification."
        },
        {
          "field_or_section": "Property Type",
          "document_a": "Single Family Home",
          "document_b": "Condominium",
          "significance": "high",
          "explanation": "The property type classification changed between documents. This affects appraisal requirements, insurance, and lending guidelines."
        },
        {
          "field_or_section": "Down Payment Percentage",
          "document_a": "20%",
          "document_b": "25%",
          "significance": "high",
          "explanation": "Significant change in down payment amount from 20% to 25%. This materially affects loan-to-value ratio and lending terms."
        },
        {
          "field_or_section": "Loan Amount",
          "document_a": "$400,000",
          "document_b": "$375,000",
          "significance": "high",
          "explanation": "Loan amount reduced by $25,000. This is a material change that affects monthly payments, debt-to-income calculations, and loan approval."
        },
        {
          "field_or_section": "Employment Status - Current",
          "document_a": "Employed",
          "document_b": "Self-Employed",
          "significance": "high",
          "explanation": "Employment status changed from employed to self-employed. This significantly affects income verification requirements and documentation needed."
        }
      ]
    },
  }
}
```     

## Evaluation Strategy

## Observability Plan 

