# Nyaya Sathi - System Design Document

## 1. System Overview
Nyaya Sathi is an AI-powered legal assistant designed to bridge the gap between Indian citizens and the justice system. It utilizes Generative AI and Natural Language Processing (NLP) to demystify legal jargon, map grievances to specific Indian laws, and generate actionable legal documents.

## 2. Architecture Diagram
[cite_start]*Note: This text description corresponds to the visual architecture required for the hackathon presentation[cite: 14].*

The system follows a **Microservices Architecture** hosted on AWS.

```mermaid
graph TD
    User[User (Mobile/Web)] -->|Voice/Text Input| API[API Gateway]
    API --> Lambda[AWS Lambda (Controller)]
    
    subgraph "AI Processing Layer"
        Lambda --> Comprehend[Amazon Comprehend (Intent & PII Redaction)]
        Lambda --> Bedrock[Amazon Bedrock (LLM Inference)]
        Bedrock <--> RAG[RAG Engine]
    end
    
    subgraph "Knowledge Base"
        RAG <--> VectorDB[Vector DB (Pinecone/OpenSearch)]
        VectorDB <--> S3[AWS S3 (Indian Law Statutes/Gazettes)]
    end
    
    subgraph "Data Persistence"
        Lambda --> Dynamo[DynamoDB (User Sessions & Logs)]
    end
    
    Lambda -->|Actionable Output| API
    API --> User
