# ⚖️ Nyaya Sathi: AI Legal Companion for Bharat

> **"Democratizing access to justice by translating complex laws into simple, actionable steps for every Indian citizen."**

[![Hackathon](https://img.shields.io/badge/Hackathon-AWS%20AI%20for%20Bharat-orange)](https://aws.amazon.com/)
[![Status](https://img.shields.io/badge/Status-Prototype-green)]()
[![License](https://img.shields.io/badge/License-MIT-blue)]()

---

## 🚩 Problem Statement

For the common Indian citizen, the legal system is often intimidating and inaccessible.
* **Complex Jargon:** Laws are written in complicated English that many cannot understand.
* **Lack of Awareness:** Most people don't know their fundamental rights or where to file a complaint.
* **High Costs:** Consulting a lawyer for basic queries is expensive.
* **Fear:** The "Police/Court" ecosystem induces fear rather than confidence.

## 💡 Our Solution

**Nyaya Sathi** is a conversational AI platform designed specifically for "Bharat" (rural and semi-urban India). It acts as a bridge between the citizen and the justice system.

Instead of just quoting sections of the law, Nyaya Sathi provides **actionable guidance**. It tells users exactly *what to do*, *where to go*, and *what documents they need*.

---

## ✨ Key Features

* **🗣️ Voice-First & Multilingual:** Interact in Hindi, English, and regional languages via voice or text.
* **🏛️ Actionable Legal Roadmaps:** Don't just learn the law; get a step-by-step plan (e.g., "Step 1: Send this Notice, Step 2: Visit District Forum").
* **📄 Automated Document Drafting:** Instantly generate legal notices, RTI applications, and complaint letters.
* **📍 Jurisdiction Finder:** Automatically maps the user's location to the correct Police Station or Court jurisdiction.
* **🛡️ Privacy First:** All user data is anonymized and encrypted.

---

## 🏗 System Architecture

The system follows a **Serverless Microservices Architecture** powered by AWS.

*(See [design.md](design.md) for the detailed architectural breakdown and data flow diagram.)*

1.  **Frontend:** Flutter Mobile App (iOS/Android).
2.  **API Layer:** AWS API Gateway for secure routing.
3.  **Orchestration:** AWS Lambda handles business logic and routing.
4.  **AI Engine:** **Amazon Lex** for Natural Language Understanding (Intent & Entity Recognition).
5.  **Knowledge Base:** **Amazon RDS** (PostgreSQL) stores Indian Laws, Acts, and Templates.
6.  **Session Store:** **Amazon DynamoDB** maintains user conversation history.

---

## 🛠 Tech Stack

| Component | Technology |
| :--- | :--- |
| **Frontend** | Flutter (Dart) |
| **Backend Logic** | Python 3.9 (AWS Lambda) |
| **API Management** | AWS API Gateway |
| **NLP & AI** | Amazon Lex |
| **Database (Relational)** | Amazon RDS (PostgreSQL) |
| **Database (NoSQL)** | Amazon DynamoDB |
| **Infrastructure** | AWS CloudFormation / SAM |

---

## 🚀 Getting Started

Follow these steps to set up the project locally.

### Prerequisites
* Node.js & NPM
* Python 3.9+
* Flutter SDK
* AWS CLI configured with appropriate permissions
