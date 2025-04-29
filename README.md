# Build-a-QA-System-Using-In-Context-Learning
Develop a Question-Answering (QA) system using  OpenAI’s LLMs that can respond to queries based on a given document. You will  utilize in-context learning, where the entire document is provided as input to the  model, and no external retrieval (RAG) is used. 


Problem Statement 
You have been provided with a Company Annual Report. Your task is to load this 
document, extract its text, and use OpenAI’s Chat Completion API to answer 
questions based on its content. 
Dataset 
Company Annual Report - 2024 
This PDF contains structured sections such as the Company Overview, Financial 
Highlights, Key Strategies, and Leadership Messages. You will use this data to 
build a QA system. 
Instructions 
Step 1: Load the Document 
● Read the PDF file and extract the text content. 
● Store the extracted text in a variable to use as input for the LLM. 
Sample Code for PDF Extraction: 
# Install PyPDF2 if you haven't already 
# !pip install PyPDF2 
import PyPDF2 
def extract_text_from_pdf(pdf_path): 
    """Extract text from a PDF file.""" 
    text = "" 
    try: 
        with open(pdf_path, 'rb') as file: 
            reader = PyPDF2.PdfReader(file) 
            for page in reader.pages: 
                text += page.extract_text() + "\n" 
        return text 
    except Exception as e: 
        print(f"Error extracting text from PDF: {e}") 
        return None 
 
# Example usage 
pdf_path = "Company_Annual_Report_2024.pdf" 
document_text = extract_text_from_pdf(pdf_path) 
print(f"Extracted {len(document_text)} characters from the PDF.") 
Step 2: Configure OpenAI’s Chat Completion API 
● Use OpenAI’s GPT-4o-mini (or GPT-3.5) model for generating responses. 
 
● Ensure the model’s prompt includes the full document content as context. 
 
Step 3: Implement In-Context Learning 
   
● Provide the entire document as input to the model in a single prompt. 
● The model should only answer questions based on this document (not 
external knowledge). 
Important Notes 
● No RAG (Retrieval-Augmented Generation) should be used. 
● The entire document should be passed as context in the prompt. 
● This assignment focuses on in-context learning. RAG will be covered in later 
modules. 
Sample Questions to Try 
Once your QA system is ready, try asking:  
● What were the company’s total revenues in 2024? 
● What are the key strategic initiatives mentioned in the report? 
● Who is the CEO of the company? 
● What are the company’s plans for sustainability? 
● How did the company perform in terms of research and development 
investment? 
Any other questions that come to your mind.
