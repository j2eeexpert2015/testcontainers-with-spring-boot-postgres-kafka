# Retail Order System

This project is a Spring Boot application that provides a RESTful API for managing retail orders. It demonstrates a microservices architecture pattern by integrating PostgreSQL for persistent data storage and Kafka for asynchronous event-driven communication. The system supports basic order management operations and publishes order events to Kafka for other services to consume.

## Features

* Create, retrieve, update, and delete orders.
* Uses PostgreSQL for data persistence.
* Asynchronously publishes "Order Placed" events to a Kafka topic (`order_placed_topic`) upon order creation.
* Includes a Kafka consumer to process `OrderPlacedEvent` events, simulating order processing.
* Comprehensive test suite including unit and integration tests, with Testcontainers for PostgreSQL and Kafka.
* Docker support for easy setup and deployment, including Kafka and Kafka UI.
* OpenAPI 3 (Swagger) documentation for API endpoints.

## Technologies Used

* Java 17
* Spring Boot 3.1.0
* Spring Data JPA
* PostgreSQL 16-alpine (using Testcontainers)
* Kafka (using Confluent Platform cp-kafka:latest with Testcontainers)
* Maven
* JUnit Jupiter
* Testcontainers (for PostgreSQL and Kafka)
* Docker
* Springdoc-openapi (Swagger UI)

## Getting Started

### Prerequisites

* Java 17 or higher
* Maven 3.6.0 or higher
* Docker (if you want to use the Docker setup)
* PostgreSQL (if you want to run the application outside Docker)

### Installation

1.  **Clone the repository:**

```bash
git clone <repository_url>
cd retail-order-system-with-postgres-kafka
```

2.  **Build the application:**

```bash
mvn clean install
```

### Running the Application

#### With Docker Compose (Recommended)

1.  **Start the Docker Compose environment:**

```bash
docker-compose up -d
```

This will start PostgreSQL, Zookeeper, Kafka, and Kafka UI.

2.  **Build and run the Spring Boot application (if not already built):**

```bash
mvn spring-boot:run
```

**Note:** You can also build the application directly into the Docker image. For an optimized workflow, consider building a Docker image for the Spring Boot application and including it in your `docker-compose.yml` file.

3.  **(Optional) Access Kafka UI:**

    * Kafka UI is available at `http://localhost:8081` to monitor Kafka topics and messages.

#### Running with Spring Boot (Without Docker Compose)

1.  **Ensure PostgreSQL and Kafka are running and accessible.**
    * You need to have PostgreSQL and Kafka set up and running separately. Make sure the connection details in `src/main/resources/application.properties` are correct for your local setup.

2.  **Run the Spring Boot application:**

```bash
mvn spring-boot:run
```

#### Access Swagger UI
```bash
http://localhost:8080/swagger-ui/index.html
```

#### Access UI for Apache Kafka
```bash
http://localhost:8081
```

### Running Tests

The project includes integration tests that use Testcontainers to run PostgreSQL and Kafka within Docker.

#### Running All Tests (with Testcontainers)

This command will run all tests, including those that use Testcontainers:

```bash
mvn test