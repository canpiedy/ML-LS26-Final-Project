# ML-LS26-Final-Project

# IITB Insti-Assist


This project was developed as the final project for the WnCC Machine Learning Learner's Space 2026.

The goal of the project is to build a Retrieval-Augmented Generation (RAG) based assistant that can answer questions related to IIT Bombay academics using official institute documents instead of relying on the language model's general knowledge.

---

## What does it do?

The assistant allows users to ask questions about IIT Bombay academics, such as:

- Course registration
- Minor Programme
- IDDDP
- Academic rules
- Grading policies

Instead of answering from memory, it first searches the uploaded IIT Bombay documents, retrieves the most relevant information, and then asks Gemini to generate an answer using only that retrieved content.

If the required information is not present in the documents, the assistant simply replies:

> *"I don't know based on the available documents."*

---

## How the project works

The workflow is fairly simple:

1. Upload the IIT Bombay PDF documents.
2. Extract text from every document.
3. Split the extracted text into smaller overlapping chunks.
4. Convert every chunk into an embedding.
5. Store all embeddings in a FAISS index.
6. Retrieve the most relevant chunks for the user's question.
7. Send the retrieved context to Gemini.
8. Display the generated answer along with the document sources.

---

## Libraries Used

- PyPDF
- Sentence Transformers
- FAISS
- Google Gemini API
- Gradio

---

## Running the notebook

1. Open the notebook in Google Colab.
2. Install the required libraries.
3. Upload the IIT Bombay PDF documents.
4. Add your Gemini API key as a Colab Secret named `GEMINI_API_KEY`.
5. Run all the cells.
6. Open the generated Gradio link and start asking questions.

---

## Some example questions

- What is the eligibility criteria for IDDDP?
- What are the rules for the Minor Programme?
- What is the grading policy?
- Procedure for Registration?
- When can a student apply for IDDDP?

---
## Data Sources Used

The assistant uses official IIT Bombay academic documents as its knowledge base. The documents used in this project include:

- UG Rule Book
- Academic Calendar 2026–27
- Course Information Booklet
- Grading Rules
- IDDDP Guidelines 2025
- Minor Programme Guidelines

The assistant generates answers only from the information available in these documents.
## Current limitations

- The assistant only answers questions that are covered in the uploaded documents.
- It does not support scanned PDFs without extractable text.
- It currently handles one question at a time and does not remember previous conversations.

---

## Possible improvements

If I had more time, I would like to add:

- Conversation history
- Better citation highlighting
- Direct PDF upload from the interface
- Confidence score for every answer
- Support for more IIT Bombay domains such as hostel rules and Gymkhana information
