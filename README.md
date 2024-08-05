# Order Management Microservices Project

## Table of Contents
- [Project Overview](#project-overview)
- [Architecture](#architecture)
- [Technologies Used](#technologies-used)
- [Prerequisites](#prerequisites)
- [Service Descriptions](#Service-Descriptions)
- [Monitoring and Observability](#Monitoring-and-Observability)

## Project Overview

This project is a comprehensive Spring Boot-based microservices application for order management. It consists of multiple services that handle various aspects of product management, inventory tracking, order processing, and customer notifications. The project also includes an Angular front-end for user interaction.

## Architecture

The project is built using a microservices architecture, with the following components:

1. **Gateway Service**: Acts as an API gateway and entry point for the application.
2. **Inventory Service**: Manages product inventory and stock levels.
3. **Notification Service**: Handles sending notifications to clients.
4. **Order Service**: Processes and manages customer orders.
5. **Product Service**: Handles product-related operations and data.
6. **Angular Front-end**: Provides a user interface for interacting with the system.

## Technologies Used

### Common Technologies
- Spring Boot
- OpenAPI for API documentation
- Prometheus for metrics collection
- Tempo for distributed tracing
- Loki for log aggregation

### Gateway Service
- Spring Cloud Gateway
- Keycloak for authentication 
- Resilience4j for fault tolerance
- Swagger UI for API documentation visualization

### Inventory Service
- MySQL database
- Flyway for database migration
- RestAssured for integration testing
- Testcontainers for integration testing

### Notification Service
- Kafka consumer
- SMTP server for sending emails
- Avro schema for data serialization

### Order Service
- MySQL database
- Flyway for database migration
- Kafka producer
- Avro schema for data serialization
- RestClient
- Testcontainers for integration testing

### Product Service
- MongoDB database
- RestAssured for integration testing
- Loki for logging
- Testcontainers for integration testing

### Angular Front-end
- Angular framework
- OIDC Client for authentication

## Prerequisites

- Java 17 or later
- Maven 3.6.x or later
- Node.js and npm (for Angular front-end)
- Docker and Docker Compose (for running dependent services)
- Kafka
- MySQL
- MongoDB
- Keycloak


API documentation for each service can be accessed via Swagger UI at /swagger-ui.html endpoint of respective services.
## Service Descriptions

### Gateway Service

Routes incoming requests to appropriate microservices
Handles authentication and authorization using Keycloak
Implements fault tolerance with Resilience4j

### Inventory Service

Check product stock levels
Updates inventory when orders are placed
Provides CRUD operations for inventory management

### Notification Service

Listens to Kafka topics for new orders
Sends email notifications to clients upon order creation

### Order Service

Processes new orders
Updates inventory based on order details
Produces events to Kafka for other services

### Product Service

Manages product information
Provides CRUD operations for products

### Angular Front-end

Provides user interface for browsing products and placing orders
Implements authentication using OIDC client

## Monitoring and Observability

- Use Prometheus to collect metrics from all services
- Utilize Tempo for distributed tracing across services
- Access logs for the Product service through Loki

## Testing

Integration tests are implemented using RestAssured and Testcontainers.
