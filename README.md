# URLA-document-compare

## Project Overview
Compare the data between two URLA documents using OpenAI’s GPT-4o and output the 
results as a structured text output file.  The URLA documents to compare should be in PDF format.  Use a Web frontend UI to be able to upload the two URLA documents.   Also, provide the ability for the end user to choose to compare the entire URLA or just a section of the URLA.   The URLA document stands for Uniform Residential Loan Application.  It is a standard government form used in Mortgage Origination.  It contains Borrowers information for applying for a loan.   

## Use Case
At my company we have two separate Mortgage printing vendors who return this URLA document.  We are still in the process of validating the data the second vendor returns to us.  Currently to do this comparison of data we view each URLA pdf document side by side and manually look at each line of data to make sure the Borrowers’ information is the same. 
Our Team would greatly benefit if we could use AI to do this data compare for us.   We would just upload the two files and have the AI app return to us any differences in an output file for review.  This will save a lot of time.

## Prerequisites
  * Python 3.11 or higher
  * HERE! Any software needed to create front end web page ( React or similar )
  * OpenAI Account and API Key
  * Code Editor ( IDE ) I like to use Vscode, but others like Cursor is a good choice  

