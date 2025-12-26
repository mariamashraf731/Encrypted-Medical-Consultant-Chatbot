# 🔒 SecureMed Connect: Encrypted Medical Chat System

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Security](https://img.shields.io/badge/Security-SSL%2FTLS-red)
![Protocol](https://img.shields.io/badge/Protocol-TCP%2FIP%20Sockets-orange)
![GUI](https://img.shields.io/badge/GUI-PyQt5-green)

## 📌 Project Overview
**SecureMed Connect** is a secure Client-Server application designed for confidential medical consultations. Unlike standard chatbots, this system prioritizes data privacy by establishing an **Encrypted SSL/TLS Channel** between the doctor (Server) and the patient (Client).

The application is built using raw **Python Sockets** to demonstrate a deep understanding of network protocols, multi-threading, and secure communication standards required in the healthcare industry (HIPAA compliance simulation).

## ⚙️ Key Technical Features
* **Secure Communication (SSL/TLS):**
    * Uses `ssl` module to wrap standard TCP sockets.
    * Implements Public Key Infrastructure (PKI) using Self-Signed Certificates.
    * Ensures end-to-end encryption to prevent Man-in-the-Middle (MITM) attacks.
* **Client-Server Architecture:**
    * **Multi-threaded Server:** Handles multiple patients simultaneously using Python `threading`.
    * **Stateful Connections:** Maintains session context for each connected client.
* **Authentication & Integrity:**
    * Server authenticates using a customized Root CA certificate.
    * Verifies data integrity during transmission.
* **Interactive GUI:**
    * User-friendly interface built with **PyQt5** (`.ui` files integrated).

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Networking:** Socket Programming (TCP/IP), SSL/TLS Context.
* **Concurrency:** Threading.
* **GUI:** PyQt5.
* **Data:** JSON (Lightweight medical knowledge base).

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone [https://github.com/mariamashraf731/SecureMed-Connect.git](https://github.com/mariamashraf731/SecureMed-Connect.git)
```
### 2. Generate Security Certificates (Critical Step)
Since private keys are sensitive, they are not included in the repo. You must generate them:
```bash
# Generate Root Key
openssl genrsa -out RootCA.key 2048
# Generate Root Certificate
openssl req -x509 -new -nodes -key RootCA.key -sha256 -days 1024 -out RootCA.pem
# Place these files in the 'certs/' directory
```
### 3. Run the System
Start the Server first:
```bash
python src/server/server.py
```
Start a Client (Patient):
```bash
python src/client/main.py
```
### 📂 Project Structure
* src/server: Handles encrypted connections and queries the medical database.
* src/client: GUI application for patients to interact securely.
* data: Contains medical_db.json with symptom-disease mappings.