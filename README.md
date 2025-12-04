# Bank Microservices Application

This project is a **Microservices Architecture (MSA)** implementation for a simplified banking platform. It was developed as part of a class TP (Travail Pratique) for learning Spring Boot and Spring Cloud concepts.

---

## Overview

The application is composed of the following services:

1. **Config Server**  
   Centralized configuration management for all microservices. Stores `application.properties` (or `.yml`) in a Git repository and serves them to clients dynamically.

2. **Eureka Discovery Server**  
   Service registry that allows microservices to discover and communicate with each other dynamically.

3. **Gateway Service**  
   Entry point for client requests. Handles routing to backend services and can apply filters, authentication, and logging.

4. **Account Service**  
   Manages bank accounts, including CRUD operations. Communicates with the customer service when needed.

5. **Customer Service**  
   Manages customer data and exposes endpoints for account service or other clients.

---

## Key Features

- **Service Discovery** with Eureka
- **Centralized Configuration** with Spring Cloud Config
- **API Gateway** for routing and filtering
- **REST APIs** for account and customer management
- **Microservices Communication** via REST and Feign clients
- **Resilience** with Circuit Breaker (Resilience4J)
- **In-Memory Database** (H2) for testing

---

## Architecture Diagram

```
Client
│
▼
    Gateway Service (Spring Cloud Gateway)
    │
    ├─ Account Service
    └─ Customer Service
        │
        └─ Config Server (central configuration)
```

---

## Tech Stack

- Java 17
- Spring Boot 4.0 
- Spring Cloud 2025.1.0
- Spring Cloud Gateway
- Eureka Discovery Server
- Spring Cloud Config
- H2 Database
- Lombok
- Maven

---

## How to Run

1. Start the **Config Server**.
2. Start the **Eureka Server**.
3. Start the **Gateway Service**.
4. Start **Customer Service** and **Account Service**.
5. Access endpoints through the gateway: `http://localhost:9999/...`.

---

## Notes

- Ensure compatible Spring Boot and Spring Cloud versions to avoid dependency conflicts.
- The gateway dynamically routes requests to services registered in Eureka.
- The config server provides central configuration for all services.
- This project is a learning exercise for microservices and service orchestration.

---


