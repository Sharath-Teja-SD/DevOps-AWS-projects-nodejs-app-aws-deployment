# 🛠️ Project Setup Guide (Local + AWS EC2)

This guide walks you through setting up and running the Stripe-integrated Node.js app both locally and on an AWS EC2 instance.

---

## 🖥️ Local Development Setup

### ✅ Prerequisites

* Node.js (v18+ recommended)
* npm (comes with Node.js)
* Git
* A Stripe account with API keys

### 🔧 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/DevOps-AWS-projects-nodejs-app-aws-deployment.git
cd DevOps-AWS-projects-nodejs-app-aws-deployment
```

### 📦 2. Install Dependencies

```bash
npm install
```

### 🔐 3. Configure Environment Variables

Create a `.env` file in the root directory and add the following:

```env
DOMAIN=http://localhost:3000
PORT=3000
STATIC_DIR=./client
PUBLISHABLE_KEY=your_stripe_publishable_key
SECRET_KEY=your_stripe_secret_key
```

### ▶️ 4. Run the App Locally

```bash
npm start
```

> Navigate to `http://localhost:3000` to see the app in action.

---

## ☁️ AWS EC2 Deployment Setup

### ✅ EC2 Prerequisites

* AWS Account
* EC2 instance (Ubuntu 20.04 preferred)
* Inbound rules for port `22 (SSH)` and `3000`

### 🔐 1. Connect to EC2 via SSH

```bash
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```

### 🔧 2. Install Node.js, npm & Git

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install nodejs npm git -y
node -v
npm -v
```

### 📂 3. Clone Your Repository

```bash
git clone https://github.com/<your-username>/DevOps-AWS-projects-nodejs-app-aws-deployment.git
cd DevOps-AWS-projects-nodejs-app-aws-deployment
```

### 📦 4. Install Node Modules

```bash
npm install
```

### 🔐 5. Add Environment Variables

```bash
touch .env
nano .env
```

Paste your local `.env` content:

```env
DOMAIN=http://<your-ec2-public-ip>:3000
PORT=3000
STATIC_DIR=./client
PUBLISHABLE_KEY=your_stripe_publishable_key
SECRET_KEY=your_stripe_secret_key
```

> Press `Ctrl+O` to save and `Ctrl+X` to exit Nano.

### ▶️ 6. Run the App on EC2

```bash
npm start
```

> Visit `http://<your-ec2-public-ip>:3000` to test the deployed app.

---

