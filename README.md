# 🌤️ Weather App - Kubernetes Microservices

A complete **microservices-based Weather Application** deployed on
Kubernetes. This project demonstrates how to deploy, configure, and
connect multiple services using Kubernetes resources such as
Deployments, Services, StatefulSets, Secrets, and Ingress.

------------------------------------------------------------------------

## 🏗️ Architecture

The application is built using a **Microservices Architecture** and
consists of the following services:

### 1️⃣ Weather UI (`weatherapp-ui`)

Frontend interface where users can: - Register - Login - Search for
weather by city

### 2️⃣ Auth Service (`weatherapp-auth`)

Backend service responsible for: - User registration - User
authentication - Managing credentials stored in the database

### 3️⃣ Weather Service (`weatherapp-weather`)

Backend API service that: - Receives weather requests from the UI -
Fetches real-time weather data from RapidAPI

### 4️⃣ Database (`mysql`)

A **StatefulSet MySQL database** used to store: - User accounts -
Authentication data

------------------------------------------------------------------------

## 🚀 Technologies Used

-   Kubernetes
-   Docker
-   NGINX Ingress Controller
-   MySQL Database
-   RapidAPI (Weather API)

Kubernetes resources used in this project:

-   Deployments
-   Services
-   StatefulSets
-   Secrets
-   Jobs
-   Ingress

------------------------------------------------------------------------

## 🛠️ Prerequisites

Before running this project, make sure you have:

-   A running Kubernetes cluster (Docker Desktop / Minikube / Kind)
-   `kubectl` installed and configured
-   NGINX Ingress Controller enabled
-   A valid Weather API key from RapidAPI

------------------------------------------------------------------------

# ⚙️ Deployment Steps

## 1️⃣ Create Required Secrets

Create Kubernetes secrets for MySQL credentials and the Weather API key.

``` bash
# MySQL Credentials
kubectl create secret generic mysql-secret   --from-literal=root-password=your_root_pass   --from-literal=auth-password=your_auth_pass   --from-literal=secret-key=your_secret_key

# Weather API Key
kubectl create secret generic weather   --from-literal=apikey=YOUR_RAPIDAPI_KEY
```

------------------------------------------------------------------------

## 2️⃣ Apply Kubernetes Resources

Deploy the database, backend services, frontend, and ingress routing.

``` bash
kubectl apply -f backend.yaml
kubectl apply -f weather.yaml
kubectl apply -f ui.yaml
kubectl apply -f ingress.yaml
```

------------------------------------------------------------------------

## 3️⃣ Configure Local DNS

Add the application domain to your local hosts file.

Example:

    127.0.0.1 weatherapp.local

Linux / Mac:

    /etc/hosts

Windows:

    C:\Windows\System32\drivers\etc\hosts

------------------------------------------------------------------------

## 4️⃣ Access the Application

Open your browser and go to:

    https://weatherapp.local

⚠️ You may see a **self-signed TLS certificate warning**. Accept the
warning to continue to the login page.

------------------------------------------------------------------------

# 📂 Project Structure

    kubernetes-lab/
    │
    ├── backend.yaml
    ├── weather.yaml
    ├── ui.yaml
    ├── ingress.yaml
    │
    └── README.md

------------------------------------------------------------------------

# 🎯 Project Goal

This project demonstrates how to:

-   Build a microservices architecture
-   Deploy applications using Kubernetes
-   Manage secrets and databases
-   Use Ingress for routing
-   Connect multiple services together

------------------------------------------------------------------------

# 👨‍💻 Author

Abdelrahman\
DevOps & Cloud Enthusiast
