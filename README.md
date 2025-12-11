# 📊 PredictionCovid
### Plateforme avancée d’analyse & de prédiction des données COVID-19  
![Status](https://img.shields.io/badge/status-active-brightgreen)  
![Docker](https://img.shields.io/badge/Docker-Enabled-blue)  
![FastAPI](https://img.shields.io/badge/API-FastAPI-009688)  
![React](https://img.shields.io/badge/Frontend-React-61DAFB)  
![Python](https://img.shields.io/badge/ML-Python-yellow)  

## 🧩 Présentation du projet
PredictionCovid est une plateforme complète permettant l’analyse, la visualisation et la prédiction des données COVID-19.

## 🏗️ Architecture
```
PredictionCovid/
│── Client/           
│── Server/           
│── docker-compose.yaml
│── init.sql
│── requirements.txt
│── .github/workflows
```

## 🚀 Démarrage rapide
### 1️⃣ Prérequis
- Docker & Docker Compose  
- Node.js 20+  
- Python 3.11  

### 2️⃣ Variables d'environnement
Créer un fichier `.env` :
```
DB_HOST=mysql
DB_PORT=3306
DB_USER=mouha
DB_PASSWORD=your_password
DB_NAME=Data
DATABASE_URL=mysql+pymysql://mouha:your_password@mysql:3306/Data

JWT_SECRET_KEY=change_me
ACCESS_TOKEN_EXPIRE_MINUTES=30
CORS_ORIGINS=http://localhost:5173
API_PREFIX=/api/v1
```

### 3️⃣ Lancement
```
docker compose up --build
```

### 4️⃣ Importation des données COVID
```
docker cp Server/insert_covid_stats.sql mysql:/tmp/
docker exec -it mysql mysql -u root -p Data -e "SOURCE /tmp/insert_covid_stats.sql;"
```

## 🔐 Authentification
Le backend utilise JWT + bcrypt.

Créer un admin :
```
INSERT INTO users (username, email, hashed_password, role, is_active)
VALUES ('admin','admin@mail.com','<hashed_password>','admin',1);
```

## 📡 API
Documentation Swagger : **http://localhost:8000/docs**

## 🤖 Machine Learning
Modèles :
- RandomForest  
- XGBoost  

## 🧪 CI/CD
- Build Frontend  
- Tests d’accessibilité  
- Build Backend  
- Packaging de déploiement  

## 📦 Production
```
docker compose -f docker-compose.prod.yaml up --build -d
```

## 📘 Licence
Usage interne professionnel.

## 🤝 Contributeurs
Mohamed Ali Jammaa
Youness Manyani
Mohawmad Dawood
