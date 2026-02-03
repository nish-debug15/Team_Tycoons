This file outlines the functional and non-functional requirements, ensuring clarity on what the solution offers and how it addresses the problem statement.

```markdown
# Nyaya Sathi - Requirements Specification

## 1. Problem Statement
The common Indian citizen faces significant barriers to justice due to:
* Lack of awareness regarding legal rights.
* Language barriers and complex legal jargon.
* High costs of legal consultation.
* Fear of the formal judicial process.

## 2. Proposed Solution
Nyaya Sathi acts as a digital legal companion that democratizes access to justice. It provides instant, accurate, and actionable legal guidance free of cost, bridging the gap between a citizen's grievance and legal resolution.

## 3. Functional Requirements (Features)

### 3.1 Legal Issue Identification
* **Input:** System must accept inputs via text and voice in English and major Indian languages.
* **Processing:** System must utilize **Amazon Lex** to classify intents (e.g., Consumer Dispute, Labor Issue).
* **Output:** System must confirm understanding of the issue to the user.

### 3.2 Rights & Law Mapping
* The system must map the identified issue to specific Indian Laws stored in **Amazon RDS**.
* The system must explain the user's rights in simple, non-legal language.

### 3.3 Actionable Guidance
* The system must provide a step-by-step roadmap for resolution.
* The system must allow users to download generated templates (e.g., Legal Notice).

## 4. Non-Functional Requirements

### 4.1 Performance
* Response time for legal query resolution should be under 5 seconds.
* The system should handle concurrent users via **AWS Lambda's** auto-scaling capabilities.

### 4.2 Security & Privacy
* **Data Privacy:** User session data in **DynamoDB** must be encrypted.
* **Encryption:** All API communication must happen over HTTPS.

## 5. Tech Stack
* **Frontend:** Flutter / React Native
* **Backend Logic:** AWS Lambda (Python/Node.js)
* **API Management:** AWS API Gateway
* **NLP & AI:** Amazon Lex
* **Databases:**
    * **Amazon RDS** (PostgreSQL/MySQL) for Legal Knowledge Base.
    * **Amazon DynamoDB** for User Session History.
