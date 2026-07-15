# AI Projects on AWS

> This document maps my AI/LLM projects to AWS services and demonstrates how they can be deployed in production.

---

# About My AI Experience

Projects Built

- CV Sorting using LLMs
- Resume Generator
- Document Parsing
- LLM Applications

Technologies Used

- LangChain
- LlamaIndex
- Ollama
- Gemma
- PyMuPDF
- Python

This document shows how these projects can be implemented using AWS services.

---

# Project 1 – CV Sorting System

## Problem

Recruiters receive thousands of resumes.

Need to:

- Extract resume content
- Understand skills
- Match resumes
- Rank candidates

---

## Local Architecture

Resume

↓

PyMuPDF

↓

LLM

↓

Embeddings

↓

Ranking

---

## AWS Architecture

Candidate Upload

↓

S3

↓

Textract

↓

Bedrock

↓

Titan Embeddings

↓

OpenSearch Vector Engine

↓

Spring Boot API

↓

Recruiter Dashboard

---

## AWS Services

| Requirement | AWS Service |
|-------------|-------------|
| File Storage | S3 |
| OCR | Textract |
| LLM | Bedrock |
| Embeddings | Titan Embeddings |
| Vector Search | OpenSearch |
| Backend | ECS |
| Database | Aurora |

---

## Interview Explanation

If asked:

"How would you deploy your resume parser on AWS?"

Explain:

- Upload resumes to S3
- Extract text using Textract
- Generate embeddings using Bedrock
- Store vectors in OpenSearch
- Spring Boot queries vector index
- Return ranked candidates

---

# Project 2 – Resume Generator

## Problem

Generate professional resumes using LLMs.

---

## AWS Architecture

User

↓

API Gateway

↓

Spring Boot

↓

Bedrock

↓

Generated Resume

↓

S3

↓

Download Link

---

## AWS Services

- API Gateway
- ECS
- Bedrock
- S3

---

# Project 3 – Resume Chatbot (RAG)

## Problem

Allow recruiters to ask questions.

Example

"Show Java developers with Kafka."

---

## Architecture

PDF

↓

S3

↓

Textract

↓

Bedrock Embeddings

↓

OpenSearch Vector Database

↓

Spring Boot

↓

Bedrock LLM

↓

Answer

---

## Why RAG?

LLM retrieves only relevant chunks.

Improves accuracy.

Reduces hallucinations.

---

# Project 4 – Document Summarizer

Upload

↓

S3

↓

Textract

↓

Bedrock

↓

Summary

↓

Aurora

---

# Project 5 – Question Answering

User

↓

Spring Boot

↓

Bedrock

↓

Knowledge Base

↓

Answer

---

# Project 6 – AI Interview Assistant

Candidate

↓

Upload Resume

↓

S3

↓

Textract

↓

Bedrock

↓

Generate Questions

↓

Spring Boot

↓

Dashboard

---

# Project 7 – Intelligent Search

Documents

↓

S3

↓

Embeddings

↓

OpenSearch

↓

Bedrock

↓

Answer

Enterprise search similar to ChatGPT over company documents.

---

# Project 8 – Job Recommendation System

Resume

↓

Bedrock Embeddings

↓

OpenSearch

↓

Job Matching

↓

Spring Boot

---

# Project 9 – Resume Screening Pipeline

Resume Upload

↓

S3

↓

Lambda

↓

Textract

↓

Bedrock

↓

OpenSearch

↓

Aurora

↓

Dashboard

---

# Project 10 – AI Customer Support

User

↓

Lex

↓

Bedrock

↓

Spring Boot

↓

Aurora

↓

Response

---

# Mapping My Existing Projects

## CV Sorting

Current

PyMuPDF

↓

LLM

↓

Embeddings

↓

Ranking

AWS

↓

S3

↓

Textract

↓

Bedrock

↓

OpenSearch

↓

Spring Boot

---

## Resume Generator

Current

Gemma

↓

Resume

AWS

↓

Bedrock

↓

S3

↓

API Gateway

---

# Future Improvements

- Bedrock Knowledge Bases
- Amazon OpenSearch Serverless
- Amazon SageMaker
- Guardrails for Bedrock
- Multi-Agent AI
- Bedrock Agents

---

# Senior Backend Interview Questions

### How would you deploy your LLM project to AWS?

S3

↓

Textract

↓

Bedrock

↓

OpenSearch

↓

Spring Boot

↓

Aurora

---

### Why Bedrock instead of SageMaker?

Bedrock provides managed foundation models.

No infrastructure.

No model training.

Ideal for Generative AI applications.

---

### Where would you store vectors?

Amazon OpenSearch Vector Engine.

---

### Where would PDFs be stored?

Amazon S3.

---

### How would you make it scalable?

- ECS Fargate
- Auto Scaling
- Redis Cache
- S3
- OpenSearch
- Aurora
- CloudWatch

---

### How would you secure the application?

- IAM Roles
- Secrets Manager
- VPC
- Private S3 Bucket
- KMS Encryption

---

# Mapping to My Experience

| My Experience | AWS Equivalent |
|---------------|----------------|
| LangChain | Bedrock + SDK |
| LlamaIndex | Bedrock Knowledge Bases |
| Ollama | Bedrock Models |
| Gemma | Bedrock Foundation Models |
| PyMuPDF | Textract |
| Resume Parsing | Textract |
| Embeddings | Titan Embeddings |
| Vector Search | OpenSearch |
| Spring Boot Backend | ECS |
| GitHub | GitHub Actions |

---

# Production Architecture

Users

↓

Route53

↓

CloudFront

↓

ALB

↓

ECS (Spring Boot)

↓

Bedrock

↓

OpenSearch

↓

Aurora

↓

S3

↓

CloudWatch

---

# Key Takeaways

- Store documents in S3.
- Use Textract for document extraction.
- Use Bedrock for Generative AI.
- Store embeddings in OpenSearch Vector Engine.
- Deploy Spring Boot services on ECS/Fargate.
- Secure AI services with IAM Roles and Secrets Manager.
- Monitor requests using CloudWatch.

---

# One-Line Revision

My AI projects can be deployed on AWS using **S3 for storage, Textract for document extraction, Bedrock for Generative AI, OpenSearch for vector search, ECS for backend services, and Aurora for metadata**, resulting in a scalable, production-ready architecture.