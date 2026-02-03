This file outlines the functional and non-functional requirements, ensuring clarity on what the solution offers and how it addresses the problem statement[cite: 2, 9].

```markdown
# Nyaya Sathi - Requirements Specification

## 1. Problem Statement [cite: 2]
The common Indian citizen faces significant barriers to justice due to:
* Lack of awareness regarding legal rights.
* Language barriers and complex legal jargon.
* High costs of legal consultation.
* Fear of the formal judicial process.

## 2. Proposed Solution [cite: 4, 7]
Nyaya Sathi acts as a digital legal companion that democratizes access to justice. It provides instant, accurate, and actionable legal guidance free of cost, bridging the gap between a citizen's grievance and legal resolution.

## 3. Functional Requirements (Features) [cite: 9]

### 3.1 Legal Issue Identification
* **Input:** System must accept inputs via text and voice in English and major Indian languages (Hindi, etc.).
* **Processing:** System must classify the user's input into a legal category (e.g., Consumer Dispute, Labor Issue, Civil Dispute).
* **Output:** System must confirm understanding of the issue to the user.

### 3.2 Rights & Law Mapping
* The system must map the identified issue to specific Indian Laws (e.g., *Consumer Protection Act, 2019*).
* The system must explain the user's rights in simple, non-legal language.

### 3.3 Actionable Guidance & Jurisdiction
* The system must provide a step-by-step roadmap for resolution (e.g., "Step 1: Write to the Nodal Officer").
* The system must identify the correct authority/court based on the user's geolocation (e.g., "Your nearest Consumer Forum is in [District Name]").

### 3.4 Document Drafting
* The system must be able to generate basic legal templates (e.g., Legal Notice, RTI Application, Police Complaint).
* Users must be able to download these drafts as PDF or Word documents.

## 4. Non-Functional Requirements

### 4.1 Performance
* Response time for legal query resolution should be under 5 seconds.
* Voice-to-text transcription accuracy should exceed 90% for supported languages.

### 4.2 Security & Privacy
* **Data Privacy:** All user data (PII) must be anonymized before being processed by the LLM.
* **Encryption:** Data must be encrypted at rest (S3/DB) and in transit (SSL/TLS).

### 4.3 Scalability
* The architecture must support auto-scaling (via AWS Lambda) to handle spikes in traffic during hackathon demos.

## 5. Tech Stack & Prerequisites 
To run this project locally, the following are required:

* **Programming Language:** Python 3.9+
* **Frameworks:** FastAPI / Flask, LangChain
* **Cloud Provider:** AWS Account (with access to Bedrock, Lambda, S3)
* **API Keys:**
    * AWS Access Key & Secret Key
    * OpenAI API Key (Optional fallback)
* **Frontend:** Flutter SDK (for mobile app build)
