# **🛒 eMartApp Microservices - Containerization Project**

A fully containerized microservices-based e-commerce application using Docker. This project demonstrates how to package and orchestrate multiple microservices, each built with different technologies (Node.js, Java), integrated with multiple databases (MongoDB, MySQL), and exposed via an Nginx API Gateway.

## 🧩 Architecture Overview


![image](https://github.com/user-attachments/assets/4b45c6fc-d40e-4846-90c2-d382ce07732a)


## 🔧 Tech Stack

| Component         | Technology Used                  | Notes                                |
|------------------|----------------------------------|--------------------------------------|
| API Gateway       | **Nginx**                        | Reverse proxy to route requests      |
| Backend Service 1 | **Node.js + Express**            | eMart API, handles `/api` route      |
| Backend Service 2 | **Java Spring Boot**             | Books API, handles `/webapi` route   |
| Database 1        | **MongoDB**                      | Used by Node.js eMart API            |
| Database 2        | **MySQL**                        | Used by Java Books API               |
| Containerization  | **Docker & Docker Compose**      | Multi-service container orchestration|


## 📁 Project Structure
```text
emartapp/
│
├── client/                  # Angular frontend microservice
│   └── Dockerfile           # Dockerfile for building Angular app
│
├── javaapi/                 # Java Spring Boot backend microservice (Books API)
│   └── Dockerfile           # Dockerfile for Java app
│
├── nodeapi/                 # Node.js backend microservice (eMart API)
│   └── Dockerfile           # Dockerfile for Node.js app
│
├── nginx/                   # Nginx API Gateway
│   └── default.conf         # Nginx reverse proxy config
│
├── docker-compose.yaml      # Compose file to run all services
```


## 🚀 Getting Started

### Prerequisites

Docker

Docker Compose

## Running the Application
```
git clone https://github.com/yourusername/emartapp.git
cd emartapp
docker-compose up --build
```

This will start the following containers:

- nginx on port 80

- emart-api on internal port 3000

- books-api on internal port 8080

- mongo and mysql as data services

## 🌐 Access Points

| Service       | URL / Route          | Description                          |
|---------------|----------------------|--------------------------------------|
| Client (Angular) | `http://localhost/`     | Frontend served via Nginx             |
| eMart API (Node.js) | `http://localhost/api`  | Handles product & user operations     |
| Books API (Java) | `http://localhost/webapi` | Java-based book service               |
| MongoDB        | `localhost:27017`        | NoSQL database for Node.js API        |
| MySQL          | `localhost:3306`         | SQL database for Java Books API       |


## 🛠 Key Concepts Demonstrated

- Containerizing multiple microservices

- Using different databases per service (Polyglot persistence)

- API Gateway pattern via Nginx

- Docker Compose for multi-container orchestration

- Environment isolation for each microservice

