

# 🏥 WellNest

### Blockchain & AI-Based Electronic Health Records (EHR) Management System

WellNest is a **secure, scalable, and patient-centric Electronic Health Record (EHR) platform** that leverages **permissioned blockchain (Hyperledger Fabric)** and **AI-driven intelligence** to ensure **data integrity, controlled access, and improved clinical usability**.

---

## 📌 Overview

Modern healthcare systems face critical challenges such as:

* Data fragmentation across institutions
* Lack of patient control over medical records
* Vulnerability to data breaches in centralized systems

**WellNest addresses these issues through:**

* **Decentralized blockchain infrastructure** for trust and immutability
* **Hybrid storage architecture** (on-chain + off-chain) for scalability
* **AI integration** for patient assistance and clinical decision support

The system ensures that **every medical transaction is verifiable, traceable, and tamper-proof**, while maintaining **high performance and usability**. 

---

## ✨ Key Features

### 🔐 Secure & Tamper-Proof Records

* Blockchain-backed immutability
* Cryptographic hash verification
* Transparent audit trails

### 👤 Patient-Centric Data Ownership

* Patients control access to their records
* Fine-grained permission management
* Real-time access approval/revocation

### 🤖 AI-Powered Healthcare Assistance

* Medical report simplification
* AI chatbot for patient queries
* Clinical Decision Support System (CDSS) for doctors

### ⚡ Scalable Hybrid Architecture

* Large files stored off-chain (MongoDB)
* Blockchain stores secure hashes for integrity
* Optimized for real-world healthcare environments

---

## 🏗️ System Architecture

WellNest follows a **modular multi-layer architecture**:

```
Frontend (React)
        ↓
Backend API (Node.js / Spring Boot)
        ↓
Hyperledger Fabric Network
        ↓
MongoDB (Off-chain Storage)
        ↓
AI Modules (Chatbot + CDSS)
```

### Core Components

* **Blockchain Layer**: Hyperledger Fabric (2 organizations, peers, orderer, CA)
* **Backend Layer**: REST APIs, authentication, blockchain interaction
* **Frontend Layer**: Responsive dashboards for users
* **AI Layer**: NLP-based chatbot + decision support system

---

## 🛠️ Technology Stack

| Layer      | Technology             |
| ---------- | ---------------------- |
| Blockchain | Hyperledger Fabric     |
| Backend    | Node.js   |
| Frontend   | React (Vite)           |
| Database   | MongoDB                |
| AI         | NLP, RAG, CDSS         |
| DevOps     | Docker, Docker Compose |

---

## 👥 User Roles

### 🏥 Healthcare Providers (Org1MSP)

* Create and update EHR records
* Request access to patient data
* View authorized records

### 🧑 Patients (Org2MSP)

* View personal medical records
* Grant/revoke access permissions
* Monitor access history

---

## 📁 Project Structure

```
wellnest_project/
│
├── blockchain/        # Fabric network & chaincode
├── backend/           # API & blockchain integration
├── frontend/          # React application
├── chatbot-service/   # AI services
└── docker-compose     # Container orchestration
```

---

## 🚀 Getting Started

### Prerequisites

* Docker & Docker Compose
* Node.js (v22+)
* Hyperledger Fabric binaries

---

### Installation

#### 1. Clone the Repository

```bash
git clone <repository-url>
cd wellnest_project
```

#### 2. Start Blockchain Network

```bash
cd blockchain/artifacts/channel
./create-artifacts.sh

cd ../
docker compose -f docker-compose-persistance.yaml up -d
```

#### 3. Deploy Chaincode

```bash
cd ../../blockchain
./createChannel.sh
./deployChaincode.sh
./ccp-generate.sh
```

#### 4. Run Backend

```bash
cd backend
docker compose up -d mongodb
npm install
npm run dev
```

#### 5. Run Frontend

```bash
cd frontend
npm install
npm run dev
```

#### 6. Run AI Service

```bash
cd chatbot-service
pip install -r requirements.txt
uvicorn app.main:app --reload
```

---

## 🔌 API Endpoints

| Method | Endpoint         | Description        |
| ------ | ---------------- | ------------------ |
| POST   | /fabric/login    | Authenticate user  |
| POST   | /fabric/register | Register new user  |
| POST   | /fabric/submit   | Submit transaction |
| GET    | /fabric/query    | Query blockchain   |

---

## 📜 Smart Contract Capabilities

The system includes chaincode for:

* EHR creation and updates
* Secure record retrieval
* Role-based access control
* Access grant and revocation
* Audit trail tracking

---

## ⚙️ Configuration

Create a `.env` file in backend:

```env
PORT=8080
MONGODB_URI=mongodb://admin:password@localhost:27017/test
JWT_SECRET=your_secret_key
FABRIC_CONNECTION_PROFILE_PATH=./connection-profiles
ENCRYPTION_SECRET_KEY=your_key
```

---

## 🔍 Key Design Highlights

* **Hybrid Storage Model**: Ensures scalability while maintaining blockchain integrity
* **RBAC with Smart Contracts**: Enforces secure access policies
* **Auditability**: Every action is permanently recorded
* **AI + Blockchain Integration**: Combines trust with intelligence

---

## 🚧 Future Enhancements

* Mobile application support
* Integration with healthcare standards (FHIR, HL7)
* Advanced AI diagnostics
* Multi-hospital interoperability
* Insurance and billing modules

---

## 👨‍💻 Contributors

* Theertha Santhosh
* Abhishek S
* Mohammed Shifan C P
* Vishnu M

**Guide:**

* Usha K

---

## 📄 License

This project is developed for academic and research purposes.

---

## 📢 Summary

WellNest represents a **next-generation healthcare platform** that integrates:

* **Blockchain for trust and security**
* **AI for intelligence and usability**
* **Patient-centric design for control and transparency**

