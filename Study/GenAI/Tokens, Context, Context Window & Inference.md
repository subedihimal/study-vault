
# Tokens

Smallest unit of text that the model processes like a word or a text.
A *Tokenizer* is used to convert input into tokens. It decides what words or combination of letters that could be half a word is considered as a token.

---
# Context

Surrounding text or information the model uses to understand and generate relevant response. 
ALSO called RAG (Retrieval-Augmented Generation)
Example of Context: 
- User input 
- Instructions
- Additional Information
- Message History
---
# Context Window

A **context window** is the **maximum amount of information an LLM can consider at one time** while generating a response.
This includes **everything** the model sees for a request:

- Your current prompt.
- Previous messages in the conversation (that are included).
- Documents or web pages you provide.
- Any system instructions.
- The model's own generated output (which also counts toward the limit).

---
# Inference 

The process of generating an output. *Inference* is just a technical term for generating an output.
