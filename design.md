# Nyaya Sathi - System Design Document

## 1. System Overview
Nyaya Sathi is an AI-powered legal assistance platform designed to provide accessible legal guidance to Indian citizens. The system utilizes **Amazon Lex** for conversational intelligence and **AWS Lambda** for serverless orchestration, ensuring a scalable and responsive experience for users interacting via text or voice.

## 2. Architecture Diagram
*Note: This diagram represents the "Lex + Lambda" architecture shown in the project presentation.*

```mermaid
graph TD
    User["User"] <--> MobileApp["Mobile App"]
    
    subgraph "Entry Layer"
        MobileApp -->|User Query (Text/Voice)| APIGateway["API Gateway"]
        APIGateway -->|Validated Request| Lambda["AWS Lambda (Central Router)"]
    end
    
    subgraph "Conversational AI Layer"
        Lambda <-->|Cleaned Query + Context| Lex["Amazon Lex (Intent & NLP)"]
        Lex -.->|Legal Insights + Next Steps| Lambda
    end
    
    subgraph "Data Persistence Layer"
        Lambda <-->|Fetch Laws & Templates| RDS["Amazon RDS (Law Knowledge Base)"]
        Lambda <-->|Fetch Session Context| DynamoDB["DynamoDB (Conversation History)"]
    end
    
    subgraph "Output Layer"
        Lambda -->|Raw Data| Formatter["Response Formatter"]
        Formatter -->|Formatted Response| APIGateway
    end
