# learn-microservices
Welcome to my microservices project! This project is designed to provide exchange rates and currency conversion with a modular and scalable architecture. Below, you'll find a brief overview of the key components:

## Projects

### 1. api-gateway
- Description: The API Gateway serves as the entry point for interacting with the microservices. It handles routing and provides a unified interface.

### 2. currency-exchange-service
- Description: This microservice provides exchange rates for India with other countries. It's responsible for fetching and managing currency conversion data.

### 3. currency-conversion-service
- Description: The Currency Conversion Service takes a provided currency with a currency code and converts it to Indian Rupees. It utilizes the exchange rates from the `currency-exchange-service`.

### 4. naming-server
- Description: The Eureka Naming Server facilitates service discovery, allowing microservices to find and communicate with each other dynamically.

## Development Environment

- IDE: Eclipse
- Build Tool: Maven

## Database

- **H2 In-Memory Database:**
- Description: Exchange rates are stored in an H2 in-memory database. It provides a lightweight and efficient solution for managing data within the microservices architecture.


## Setup Instructions

1. Clone the repository.
2. Open the projects in Eclipse.
3. Build each project using Maven.
4. Run the Eureka Naming Server first.
5. Start the microservices (`api-gateway`, `currency-exchange-service`, `currency-conversion-service`).

## Usage

- Access the API Gateway to interact with the microservices.

- ## URLS

#### Currency Exchange Service
- http://localhost:8000/currency-exchange/from/USD/to/INR

#### Currency Conversion Service
- http://localhost:8100/currency-conversion/from/USD/to/INR/quantity/10
- http://localhost:8100/currency-conversion-feign/from/USD/to/INR/quantity/10

#### Eureka
- http://localhost:8761/

#### Zipkin
- http://localhost:9411/

#### API GATEWAY
- http://localhost:8765/currency-exchange/from/USD/to/INR
- http://localhost:8765/currency-conversion/from/USD/to/INR/quantity/10
- http://localhost:8765/currency-conversion-feign/from/USD/to/INR/quantity/10
- http://localhost:8765/currency-conversion-new/from/USD/to/INR/quantity/10

#### Commands
```
docker run -p 9411:9411 openzipkin/zipkin:2.23
docker push docker.io/ajayondocker/ms-currency-exchange-service:0.0.1-SNAPSHOT
docker-compose --version
docker-compose up
docker push ajayondocker/ms-naming-server:0.0.1-SNAPSHOT
docker push ajayondocker/ms-currency-conversion-service:0.0.1-SNAPSHOT
docker push ajayondocker/ms-api-gateway:0.0.1-SNAPSHOT



