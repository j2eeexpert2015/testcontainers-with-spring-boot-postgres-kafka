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
git clone https://github.com/j2eeexpert2015/testcontainers-with-spring-boot-postgres-kafka.git
cd testcontainers-with-spring-boot-postgres-kafka
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
```

## 👤 About the Instructor

[![Ayan Dutta - Instructor](https://img-c.udemycdn.com/user/200_H/5007784_d6b8.jpg)](https://www.udemy.com/user/ayandutta/)

Hi, I’m **Ayan Dutta**, a Software Architect, Instructor, and Content Creator.  
I create practical, hands-on courses on **Java, Spring Boot, Debugging, Git, Python**, and more.

---

## 🌐 Connect With Me

- 💬 **Slack Group:** [Join Here](https://join.slack.com/t/learningfromexp/shared_invite/zt-1fnksxgd0-_jOdmIq2voEeMtoindhWrA)
- 📢 After joining, go to the `#java-debugging-with-intellij-idea-udemy` channel
- 📧 **Email:** j2eeexpert2015@gmail.com
- 🔗 **YouTube:** [LearningFromExperience](https://www.youtube.com/@learningfromexperience)
- 📝 **Medium Blog:** [@mrayandutta](https://medium.com/@mrayandutta)
- 💼 **LinkedIn:** [Ayan Dutta](https://www.linkedin.com/in/ayan-dutta-a41091b/)

---

## 📺 Subscribe on YouTube

[![YouTube](https://img.shields.io/badge/Watch%20on%20YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@learningfromexperience)

---

## 📚 Explore My Udemy Courses

### 🧩 Java Debugging Courses with Eclipse, IntelliJ IDEA, and VS Code

<table>
  <tr>
    <td>
      <a href="https://www.udemy.com/course/eclipse-debugging-techniques-and-tricks">
        <img src="https://img-c.udemycdn.com/course/480x270/417118_3afa_4.jpg" width="250"><br/>
        <b>Eclipse Debugging Techniques</b>
      </a>
    </td>
    <td>
      <a href="https://www.udemy.com/course/java-debugging-with-intellij-idea">
        <img src="https://img-c.udemycdn.com/course/480x270/2608314_47e4.jpg" width="250"><br/>
        <b>Java Debugging With IntelliJ</b>
      </a>
    </td>
    <td>
      <a href="https://www.udemy.com/course/java-debugging-with-visual-studio-code-the-ultimate-guide">
        <img src="https://img-c.udemycdn.com/course/480x270/5029852_d692_3.jpg" width="250"><br/>
        <b>Java Debugging with VS Code</b>
      </a>
    </td>
  </tr>
</table>

---

### 💡 Java Productivity & Patterns

<table>
  <tr>
    <td>
      <a href="https://www.udemy.com/course/intellij-idea-tips-tricks-boost-your-java-productivity">
        <img src="https://img-c.udemycdn.com/course/480x270/6180669_7726.jpg" width="250"><br/>
        <b>IntelliJ IDEA Tips & Tricks</b>
      </a>
    </td>
    <td>
      <a href="https://www.udemy.com/course/design-patterns-in-javacreational">
        <img src="https://img-c.udemycdn.com/course/480x270/779796_5770_2.jpg" width="250"><br/>
        <b>Creational Design Patterns</b>
      </a>
    </td>
  </tr>
</table>

---

### 🐍 Python Debugging Courses

<table>
  <tr>
    <td>
      <a href="https://www.udemy.com/course/learn-python-debugging-with-pycharm-ide">
        <img src="https://img-c.udemycdn.com/course/480x270/4840890_12a3_2.jpg" width="250"><br/>
        <b>Python Debugging With PyCharm</b>
      </a>
    </td>
    <td>
      <a href="https://www.udemy.com/course/python-debugging-with-visual-studio-code">
        <img src="https://img-c.udemycdn.com/course/480x270/5029842_d36f.jpg" width="250"><br/>
        <b>Python Debugging with VS Code</b>
      </a>
    </td>
    <td>
      <a href="https://www.udemy.com/course/get-started-with-python-debugging-in-visual-studio-code">
        <img src="https://img-c.udemycdn.com/course/480x270/6412275_a17d.jpg" width="250"><br/>
        <b>Python Debugging (Free)</b>
      </a>
    </td>
  </tr>
</table>

---

### 🛠 Git & GitHub Courses

<table>
  <tr>
    <td>
      <a href="https://www.udemy.com/course/getting-started-with-github-desktop">
        <img src="https://img-c.udemycdn.com/course/480x270/6112307_3b4e_2.jpg" width="250"><br/>
        <b>GitHub Desktop Guide</b>
      </a>
    </td>
    <td>
      <a href="https://www.udemy.com/course/learn-to-use-git-and-github-with-eclipse-a-complete-guide">
        <img src="https://img-c.udemycdn.com/course/480x270/3369428_995b.jpg" width="250"><br/>
        <b>Git & GitHub with Eclipse</b>
      </a>
    </td>
  </tr>
</table>


