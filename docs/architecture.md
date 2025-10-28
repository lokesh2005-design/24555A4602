# System Architecture (Unified Build)

## Overview
DevOps Simulator follows a **microservices architecture** designed for high availability, scalability, and future AI integration.  
It includes both **stable production components** and **experimental AI-powered features** for predictive automation.

---

## Core Components

### 1. Application Server
- **Technology**: Node.js + Express (+ TensorFlow.js in experimental mode)
- **Ports**:
  - Production: 8080  
  - Development: 3000  
  - Experimental: 9000–9002 (AI API & metrics)
- **Scaling**:
  - Production: Horizontal auto-scaling
  - Experimental: AI-powered predictive scaling
- **Development Features**: Hot reload, debug mode
- **Event Queue (Experimental)**: Apache Kafka for event streaming

---

### 2. Database Layer
- **Database**: PostgreSQL 14  
- **Production**: Master-slave replication with automated backups  
- **Development**: Single local instance with seed data  
- **Experimental Extensions**:
  - Redis cluster for caching
  - AI-assisted query optimization and index suggestions
  - Multi-master replication with geo-redundant backup

---

### 3. Monitoring & Observability
- **Production**: Prometheus + Grafana with email alerts  
- **Development**: Console logging (verbose mode)  
- **Experimental Enhancements**:
  - Thanos for long-term metric storage  
  - ELK Stack + AI log analysis  
  - Real-time anomaly detection (LSTM-based models)

---

### 4. Multi-Cloud Deployment (Experimental)
- **Supported Clouds**: AWS, Azure, GCP, DigitalOcean  
- **Orchestration**: Kubernetes with custom CRDs  
- **Load Balancing**: GeoDNS with global failover  
- **Resilience**: Cross-cloud redundancy

---

### 5. Deployment Strategy

#### Production
- **Method**: Rolling updates  
- **Zero Downtime**: Yes  
- **Rollback**: Automated on failure  
- **Region**: us-east-1  

#### Development
- **Method**: Docker Compose  
- **Features**: Hot reload, instant feedback  
- **Testing**: Automated pre-deployment tests  

#### Experimental (AI Mode)
- **Strategy**: Canary + Predictive Scaling  
- **Learning Models**: LSTM (anomaly detection), XGBoost (load prediction)  
- **Pipeline Frameworks**: TensorFlow, PyTorch, Scikit-learn  

---

### 6. Security
- **Production**: SSL/TLS, strict IAM and access controls  
- **Development**: Relaxed for debugging  
- **Experimental**: AI-based anomaly detection for access patterns  

---

**Note:**  
Experimental components are optional and can be activated with:
```bash
export DEPLOY_ENV=experimental
