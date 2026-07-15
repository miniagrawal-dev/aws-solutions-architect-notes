# AWS Machine Learning Services

# Overview

AWS provides a wide range of Artificial Intelligence (AI) and Machine Learning (ML) services that allow developers to build intelligent applications without creating ML models from scratch.

This section covers:

- Amazon Rekognition
- Amazon Comprehend
- Amazon Transcribe
- Amazon Polly
- Amazon Translate
- Amazon Lex
- Amazon Kendra
- Amazon Personalize
- Amazon Textract
- Amazon Forecast
- Amazon Fraud Detector
- Amazon SageMaker
- Amazon Bedrock

---

# AI vs Machine Learning

Artificial Intelligence

↓

Broad field of creating intelligent systems.

Machine Learning

↓

Subset of AI where systems learn patterns from data.

Deep Learning

↓

Subset of ML using neural networks.

---

# Amazon Rekognition

Image and video analysis service.

Features:

- Object Detection
- Face Detection
- Face Comparison
- Text Detection
- Celebrity Recognition
- Content Moderation

Use Cases

- Face verification
- Photo tagging
- Security surveillance
- Identity verification

---

# Amazon Comprehend

Natural Language Processing (NLP).

Features

- Sentiment Analysis
- Entity Detection
- Language Detection
- Key Phrase Extraction

Use Cases

- Customer Reviews
- Social Media Analysis
- Ticket Classification

---

# Amazon Transcribe

Speech-to-text service.

Converts:

Audio

↓

Text

Supports:

- Speaker identification
- Custom vocabulary
- Real-time transcription

---

# Amazon Polly

Text-to-speech service.

Converts:

Text

↓

Natural Voice

Supports multiple languages.

---

# Amazon Translate

Neural machine translation.

Converts:

English

↓

French

↓

German

↓

Hindi

Supports many languages.

---

# Amazon Lex

Conversational AI service.

Builds:

- Chatbots
- Voice Bots
- Virtual Assistants

Powered by:

Automatic Speech Recognition

Natural Language Understanding

---

# Amazon Kendra

Enterprise search engine.

Searches:

- PDFs
- Word documents
- SharePoint
- S3
- Websites

Provides intelligent search results.

---

# Amazon Personalize

Recommendation engine.

Uses user behavior to recommend:

- Products
- Movies
- Music
- Content

Similar to recommendation systems used by Amazon and Netflix.

---

# Amazon Textract

Extracts text and structured information from scanned documents.

Recognizes:

- Tables
- Forms
- Handwritten text

Use Cases

- Invoice Processing
- Resume Parsing
- Bank Statements

---

# Amazon Forecast

Time-series forecasting.

Predicts:

- Demand
- Sales
- Inventory
- Revenue

---

# Amazon Fraud Detector

Detects fraudulent activities.

Examples

- Credit Card Fraud
- Fake Accounts
- Insurance Fraud

Uses historical data and ML models.

---

# Amazon SageMaker

End-to-end Machine Learning platform.

Supports:

- Data Preparation
- Model Training
- Model Deployment
- Monitoring

Used by ML Engineers and Data Scientists.

---

# Amazon Bedrock

Managed Generative AI service.

Provides access to foundation models from providers such as:

- Anthropic
- Meta
- Amazon
- AI21 Labs
- Cohere

Use Cases

- Chatbots
- AI Assistants
- Document Summarization
- Question Answering
- Code Generation

---

# Service Selection Guide

| Requirement | AWS Service |
|-------------|-------------|
| Image Analysis | Rekognition |
| NLP | Comprehend |
| Speech to Text | Transcribe |
| Text to Speech | Polly |
| Translation | Translate |
| Chatbot | Lex |
| Enterprise Search | Kendra |
| Recommendations | Personalize |
| OCR | Textract |
| Forecasting | Forecast |
| Fraud Detection | Fraud Detector |
| ML Platform | SageMaker |
| Generative AI | Bedrock |

---

# Best Practices

- Use managed AI services before building custom ML models.
- Use Bedrock for GenAI applications.
- Use SageMaker only when custom model training is required.
- Store training data in S3.
- Secure models using IAM roles.
- Monitor inference with CloudWatch.

---

# Hands-On Summary

- Explored AWS AI services
- Compared managed AI APIs
- Learned Bedrock fundamentals
- Reviewed SageMaker workflow
- Understood common ML use cases