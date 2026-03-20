# Multimodel_strbks_finance

Multimodal RAG for Financial Analysis (Starbucks Case Study)
About this project

I built this project to explore how we can use GenAI with multiple data types (audio, text, and images) to answer real-world financial questions.

The idea was simple:
Instead of just reading a report, can we combine:

earnings call audio
financial documents
and an LLM

to get smarter, context-aware answers?

So I created a multimodal RAG pipeline that pulls relevant information from both text and images and uses it to generate answers.

What it does
Takes an earnings call audio file and transcribes it using Whisper
Extracts content from financial PDFs and converts them into images
Creates embeddings for both text and images using CLIP
When a question is asked:
Finds the most relevant text + images
Sends them to an LLM
Generates a final answer

Tech stack

I tried to keep this practical and close to real-world tools:

Python
OpenAI (Whisper + GPT)
LangChain
SentenceTransformers (CLIP)
Scikit-learn (cosine similarity)
pdf2image + PIL

How the pipeline works
Audio → Text
Used Whisper to transcribe the earnings call
Broke it into smaller chunks for better retrieval
PDF → Images
Converted financial report pages into images
This helps capture charts/visual data
Embeddings
Used CLIP to embed both text and images into the same space
Retrieval
Converted the user query into an embedding
Compared it with stored embeddings
Picked the most relevant results
Answer generation
Combined retrieved text + images
Passed them to GPT
Generated a contextual answer

Example

Question:

What are the short-term risks for Starbucks?

The system pulls:

Relevant parts of the earnings call
Supporting visuals from the report

And then generates a grounded answer instead of hallucinating.

What I learned

This project helped me understand a lot of things beyond just coding:

How RAG actually works in practice, not just theory
Handling multimodal data (text + images)
Why retrieval quality matters more than the LLM sometimes
How to structure an end-to-end AI pipeline

Skills this project reflects
Building RAG systems
Working with LLMs (prompting + integration)
Using Whisper for speech-to-text
Embeddings and similarity search
Basic computer vision with CLIP
Designing scalable ML pipelines
