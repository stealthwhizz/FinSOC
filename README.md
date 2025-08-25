# FinSoc: Unified Financial Fraud Intelligence Platform

![FinSoc Logo](https://img.shields.io/badge/FinSoc-Fraud%20Prevention-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3.9+-yellow?style=for-the-badge)
![React](https://img.shields.io/badge/React-18+-blue?style=for-the-badge)

## 🚀 Overview

FinSoc is an AI-driven, unified fraud prevention platform designed to protect retail investors and regulators in the securities market. Acting as a Financial Security Operations Center (SOC), FinSoc combines cutting-edge technologies—Artificial Intelligence, Natural Language Processing, Blockchain, and robust Cybersecurity—to detect and prevent multi-channel fraud threats in real-time.

**Built for SEBI Hackathon 2025** - Addressing the critical need for investor protection in India's growing securities market.

---

## 🎯 Problem Statement

Retail investors face multi-channel fraud threats that erode trust in financial markets:
- Fake advisors & trading apps promising guaranteed returns
- Pump-and-dump scams on WhatsApp/Telegram groups
- Deepfake videos & forged SEBI letters misleading investors
- Misleading corporate announcements causing false stock movements

**Existing solutions are fragmented, reactive, and narrow. FinSoc provides a unified, proactive approach.**

---

## ✨ Key Features

### 🔍 **Deepfake & Document Forensics**
- AI-powered detection of synthetic videos and audios
- Verification of regulatory letters and corporate documents
- Real-time authenticity scoring

### 📱 **Social Media Surveillance**
- Monitors WhatsApp, Telegram, Twitter, and other platforms
- Flags pump-and-dump stock tips using NLP
- Links suspicious chatter to abnormal trading activity

### ✅ **Advisor & App Verification**
- Cross-verifies advisor credentials against SEBI registries
- Detects phishing or fake trading applications
- Real-time credential validation

### 📊 **Corporate Announcement Integrity**
- AI-powered credibility scoring of corporate disclosures
- Cross-verification with historical filings
- Blockchain-backed immutable record keeping

### 📲 **Dual Interface System**
- **Investor App**: Verify tips, advisors, and apps instantly
- **Regulator Dashboard**: Centralized fraud intelligence for SEBI

---

## 🏗️ System Architecture

```
┌─────────────────────────┐
│     Data Sources        │
│ Social Media (TG, WA, X)│
│ Stock Exchanges (NSE,BSE)│
│ SEBI Registry          │
│ News, Docs, Videos      │
└─────────────────────────┘
            │
            ▼
┌─────────────────────────┐
│  Data Ingestion Layer   │
│ (Kafka, Scrapy, APIs)   │
└─────────────────────────┘
            │
            ▼
┌────────────────────────────────────┐
│   Fraud Detection Engines          │
│ - NLP Pump/Dump Detector           │
│ - Trading Volume Anomaly Detection │
│ - Deepfake/Document Forensics      │
│ - Advisor/App Authenticity Checker │
│ - Blockchain Filing Validator      │
└────────────────────────────────────┘
            │
            ▼
┌─────────────────────────┐
│   Risk Scoring Engine   │
│ (Fraud Probability %)   │
└─────────────────────────┘
            │
            ▼
┌───────────────────────────────┐
│ Dashboards & Interfaces       │
│ - Investor Web/Mobile App     │
│ - Regulator Control Dashboard │
└───────────────────────────────┘
```

---

## 🛠️ Technology Stack

### Backend
- **Framework**: Python (FastAPI)
- **Data Processing**: Apache Spark, Pandas
- **Message Queue**: Apache Kafka
- **Database**: PostgreSQL, Redis (caching)
- **AI/ML**: HuggingFace Transformers, Scikit-learn, TensorFlow

### Frontend
- **Web**: React 18, TypeScript, Tailwind CSS
- **Mobile**: React Native
- **UI Components**: ShadCN UI, Recharts

### Blockchain & Security
- **Blockchain**: Hyperledger Fabric / Ethereum
- **Security**: JWT Authentication, HTTPS, Rate Limiting
- **Data Protection**: AES-256 Encryption

### DevOps & Deployment
- **Containerization**: Docker, Docker Compose
- **Orchestration**: Kubernetes
- **CI/CD**: GitHub Actions
- **Monitoring**: Prometheus, Grafana

---

## 📋 Prerequisites

Before you begin, ensure you have the following installed on your system:

- **Python 3.9 or higher** ([Download Python](https://python.org/downloads/))
- **Node.js 16 or higher** ([Download Node.js](https://nodejs.org/))
- **Git** ([Download Git](https://git-scm.com/downloads))
- **Docker** (optional, for containerized deployment) ([Download Docker](https://docker.com/))

### For Windows Users:
- Install Python from Microsoft Store or python.org
- Use Windows Terminal or PowerShell for commands
- Consider using WSL2 for better Linux compatibility

### For macOS Users:
- Install via Homebrew: `brew install python node git`

### For Linux Users:
- Ubuntu/Debian: `sudo apt update && sudo apt install python3 nodejs npm git`
- CentOS/RHEL: `sudo yum install python3 nodejs npm git`

---

## 🚀 Installation Guide

### Step 1: Clone the Repository

```bash
# Clone the repository
git clone https://github.com/yourusername/finsoc.git

# Navigate to project directory
cd finsoc

# Check the project structure
ls -la
```

### Step 2: Backend Setup

```bash
# Navigate to backend directory
cd backend

# Create a virtual environment (recommended)
python -m venv finsoc_env

# Activate virtual environment
# On Windows:
finsoc_env\Scripts\activate
# On macOS/Linux:
source finsoc_env/bin/activate

# Install Python dependencies
pip install --upgrade pip
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env file with your configuration
```

**Required Environment Variables:**
```bash
# Database Configuration
DATABASE_URL=postgresql://username:password@localhost:5432/finsoc_db

# SEBI API Configuration
SEBI_API_KEY=your_sebi_api_key
SEBI_BASE_URL=https://api.sebi.gov.in

# AI/ML Configuration
HUGGINGFACE_API_KEY=your_huggingface_key
OPENAI_API_KEY=your_openai_key

# Security
JWT_SECRET_KEY=your_jwt_secret_key
ENCRYPTION_KEY=your_encryption_key

# Social Media APIs
TELEGRAM_BOT_TOKEN=your_telegram_bot_token
TWITTER_API_KEY=your_twitter_api_key
```

### Step 3: Database Setup

```bash
# Install and start PostgreSQL (if not already installed)
# On Windows: Download from postgresql.org
# On macOS: brew install postgresql
# On Ubuntu: sudo apt install postgresql

# Create database
createdb finsoc_db

# Run database migrations
python manage.py migrate

# Create superuser (optional)
python manage.py createsuperuser
```

### Step 4: Frontend Setup

```bash
# Open new terminal and navigate to frontend directory
cd frontend

# Install Node.js dependencies
npm install

# Install additional UI libraries
npm install @shadcn/ui recharts lucide-react

# Copy environment configuration
cp .env.example .env.local
```

**Frontend Environment Variables:**
```bash
NEXT_PUBLIC_API_URL=http://localhost:8000
NEXT_PUBLIC_WS_URL=ws://localhost:8000/ws
NEXT_PUBLIC_APP_NAME=FinSoc
```

### Step 5: Mobile App Setup (Optional)

```bash
# Navigate to mobile directory
cd mobile

# Install dependencies
npm install

# Install React Native CLI (if not installed)
npm install -g @react-native-community/cli

# For iOS (macOS only)
cd ios && pod install && cd ..

# For Android, ensure Android Studio is installed
```

---

## 🎮 Usage Guide

### Starting the Application

#### Method 1: Development Mode (Recommended for beginners)

**Terminal 1 - Backend:**
```bash
cd backend
source finsoc_env/bin/activate  # On Windows: finsoc_env\Scripts\activate
python manage.py runserver
# Backend will start at http://localhost:8000
```

**Terminal 2 - Frontend:**
```bash
cd frontend
npm run dev
# Frontend will start at http://localhost:3000
```

**Terminal 3 - AI Services (Optional):**
```bash
cd ai_services
python fraud_detector.py
# AI services will start processing
```

#### Method 2: Docker (Advanced)

```bash
# Build and start all services
docker-compose up --build

# Run in background
docker-compose up -d

# Stop services
docker-compose down
```

### Accessing the Application

1. **Investor App**: Open browser to `http://localhost:3000`
2. **Regulator Dashboard**: Navigate to `http://localhost:3000/admin`
3. **API Documentation**: Visit `http://localhost:8000/docs`

### Basic Usage Workflow

#### For Investors:

1. **Register/Login**:
   - Open the investor app
   - Create account or login
   - Verify email if required

2. **Verify Stock Tips**:
   - Go to "Verify Tip" section
   - Paste WhatsApp/Telegram message
   - Click "Analyze"
   - Review risk score and recommendations

3. **Check Advisor Credentials**:
   - Navigate to "Advisor Verification"
   - Enter advisor name or registration number
   - View SEBI registration status
   - See historical ratings and complaints

4. **Validate Trading Apps**:
   - Upload app screenshot or enter app name
   - System checks against known scam database
   - Receive safety rating and recommendations

#### For Regulators:

1. **Access Dashboard**:
   - Login with admin credentials
   - View real-time fraud alerts
   - Monitor market sentiment trends

2. **Review Alerts**:
   - Click on high-priority alerts
   - Investigate fraud patterns
   - Export reports for action

3. **Generate Reports**:
   - Select date range and fraud type
   - Generate compliance reports
   - Schedule automated alerts

---

## 📊 API Documentation

### Authentication

All API requests require authentication via JWT tokens:

```bash
# Login to get token
curl -X POST "http://localhost:8000/auth/login" \
  -H "Content-Type: application/json" \
  -d '{"username": "your_username", "password": "your_password"}'

# Use token in subsequent requests
curl -X GET "http://localhost:8000/api/verify-tip" \
  -H "Authorization: Bearer YOUR_JWT_TOKEN"
```

### Key Endpoints

#### Tip Verification
```bash
POST /api/verify-tip
{
  "message": "Buy XYZ stock now! 500% returns guaranteed!",
  "source": "telegram",
  "timestamp": "2025-08-24T18:30:00Z"
}
```

#### Advisor Verification
```bash
GET /api/verify-advisor/{advisor_id}
POST /api/verify-advisor
{
  "name": "John Doe",
  "registration_number": "INH000001234",
  "claimed_credentials": ["Investment Advisor", "Research Analyst"]
}
```

#### Document Verification
```bash
POST /api/verify-document
{
  "document_url": "https://example.com/document.pdf",
  "document_type": "sebi_letter",
  "claimed_authenticity": true
}
```

---

## 🧪 Testing

### Unit Tests

```bash
# Backend tests
cd backend
python -m pytest tests/ -v

# Frontend tests
cd frontend
npm test

# Run specific test file
npm test -- VerifyTip.test.js
```

### Integration Tests

```bash
# Run full integration test suite
python -m pytest tests/integration/ -v

# Test API endpoints
python test_api.py
```

### Performance Tests

```bash
# Load testing with locust
pip install locust
locust -f tests/performance/locustfile.py
```

---

## 🐛 Troubleshooting

### Common Issues

#### 1. **Backend won't start**
```bash
# Check Python version
python --version  # Should be 3.9+

# Reinstall dependencies
pip install -r requirements.txt --force-reinstall

# Check database connection
python manage.py check --database default
```

#### 2. **Frontend compilation errors**
```bash
# Clear node modules and reinstall
rm -rf node_modules package-lock.json
npm install

# Check Node.js version
node --version  # Should be 16+
```

#### 3. **Database connection issues**
```bash
# Check PostgreSQL status
sudo service postgresql status

# Reset database
dropdb finsoc_db
createdb finsoc_db
python manage.py migrate
```

#### 4. **AI model loading errors**
```bash
# Install additional ML dependencies
pip install torch torchvision torchaudio
pip install transformers[torch]

# Download required models
python scripts/download_models.py
```

### Getting Help

- **Issues**: Create an issue on GitHub
- **Discussions**: Join our Discord community
- **Documentation**: Check `/docs` directory
- **Email Support**: finsoc-support@example.com

---

## 🤝 Contributing

We welcome contributions from the community! Here's how to get started:

### Development Workflow

1. **Fork the repository**
2. **Create feature branch**:
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Make changes and commit**:
   ```bash
   git commit -m "Add amazing feature"
   ```
4. **Push to branch**:
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Create Pull Request**

### Code Standards

- **Python**: Follow PEP 8, use Black formatter
- **JavaScript**: Use ESLint and Prettier
- **Documentation**: Update README for new features
- **Testing**: Include tests for new functionality

### Contribution Areas

- 🔧 **Backend Development**: API endpoints, ML models
- 🎨 **Frontend Development**: UI/UX improvements
- 📱 **Mobile Development**: React Native features
- 🧪 **Testing**: Unit tests, integration tests
- 📖 **Documentation**: Tutorials, API docs
- 🔐 **Security**: Vulnerability assessments
- 🌐 **DevOps**: Deployment, monitoring

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 FinSoc Team

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 📞 Contact & Support

### Team Members
- **Project Lead**: [Your Name](mailto:lead@finsoc.dev)
- **Backend Lead**: [Backend Dev](mailto:backend@finsoc.dev)
- **Frontend Lead**: [Frontend Dev](mailto:frontend@finsoc.dev)
- **AI/ML Lead**: [ML Engineer](mailto:ml@finsoc.dev)

### Community
- **Website**: [https://finsoc.dev](https://finsoc.dev)

### Business Inquiries
- **Email**: ash56pokemon@gmail.com
- **Phone**: +91-7349130318

---

## 🙏 Acknowledgments

- **SEBI** for hosting the hackathon and providing the problem statement
- **Hack2Skill** for organizing the event
- **Open Source Community** for the amazing tools and libraries
- **Indian Stock Exchanges** for market data access
- **Security Researchers** for fraud pattern insights

---

## 📈 Project Status

![GitHub last commit](https://img.shields.io/github/last-commit/yourusername/finsoc)
![GitHub issues](https://img.shields.io/github/issues/yourusername/finsoc)
![GitHub pull requests](https://img.shields.io/github/issues-pr/yourusername/finsoc)

**Current Version**: v1.0.0-beta
**Development Status**: Active
**Deployment**: Production Ready
**Last Updated**: August 24, 2025

---

**Built with ❤️ for SEBI Hackathon 2025**
