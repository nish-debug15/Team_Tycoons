# Nyaya Sathi - System Design Document

## 1. System Overview
Nyaya Sathi is an AI-powered legal assistance platform designed to provide accessible legal guidance to Indian citizens. The system utilizes **Amazon Lex** for conversational intelligence and **AWS Lambda** for serverless orchestration, ensuring a scalable and responsive experience for users interacting via text or voice.

## 2. Architecture Diagram
*Note: This diagram represents the high-level architecture with a focus on component interaction.*

```mermaid
flowchart TD
    User["User"] <--> MobileApp["Mobile App"]
    
    subgraph Entry ["Entry Layer"]
        MobileApp -->|User Query| APIGateway["API Gateway"]
        APIGateway -->|Validated Request| Lambda["AWS Lambda Router"]
    end
    
    subgraph AI ["Conversational AI Layer"]
        Lambda <-->|Cleaned Query| Lex["Amazon Lex NLP"]
        Lex -.->|Legal Insights| Lambda
    end
    
    subgraph Data ["Data Persistence Layer"]
        Lambda <-->|Fetch Laws| RDS["Amazon RDS SQL"]
        Lambda <-->|Fetch Session| DynamoDB["DynamoDB History"]
    end
    
    subgraph Out ["Output Layer"]
        Lambda -->|Raw Data| Formatter["Response Formatter"]
        Formatter -->|Final Response| APIGateway
    end
