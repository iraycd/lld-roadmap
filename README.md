# Low-Level Design (LLD) Preparation Roadmap

> A structured guide to mastering low-level design concepts, principles, and best practices.

---

## Table of Contents
1. [Fundamentals](#1-fundamentals)
2. [Design Principles](#2-design-principles)
3. [Design Patterns](#3-design-patterns)
4. [Systematic Design Thinking](#4-systematic-design-thinking)
5. [Domain-Specific Practices](#5-domain-specific-practices)
6. [Architectural Styles](#6-architectural-styles)
7. [Distributed Systems and Microservices](#7-distributed-systems-and-microservices)
8. [Concurrency and Performance](#8-concurrency-and-performance)
9. [Security and Resilience](#9-security-and-resilience)
10. [Testing and Quality Assurance](#10-testing-and-quality-assurance)
11. [Tools and Techniques](#11-tools-and-techniques)
12. [Interview Preparation](#12-interview-preparation)

---

## 1. Fundamentals

### 1.1 Object-Oriented Programming (OOP)
- **Abstraction** – Hide complex details behind a simple interface.  
- **Encapsulation** – Keep related data and methods in one place.  
- **Inheritance** – Derive new classes from existing ones.  
- **Polymorphism** – Implement different behaviors under a single interface.

### 1.2 Clean Code
- **Meaningful naming conventions** – Use descriptive, consistent names.  
- **Readable and modular code** – Keep your code structured and easy to understand.  
- **DRY (Don’t Repeat Yourself)** – Abstract repeated logic into reusable components.  
- **Refactoring techniques** – Continuously improve code structure without changing behavior.

---

## 2. Design Principles

### 2.1 SOLID Principles
1. **Single Responsibility Principle (SRP)** – Each class should have one responsibility.  
2. **Open-Closed Principle (OCP)** – Entities should be open for extension but closed for modification.  
3. **Liskov Substitution Principle (LSP)** – Subtypes must be replaceable for their supertypes.  
4. **Interface Segregation Principle (ISP)** – Clients shouldn’t depend on unused interfaces.  
5. **Dependency Inversion Principle (DIP)** – High-level modules shouldn’t depend on low-level modules; both should depend on abstractions.

### 2.2 Other Principles
- **KISS (Keep It Simple, Stupid)** – Favor simplicity over complexity.  
- **YAGNI (You Aren’t Gonna Need It)** – Avoid implementing what you don’t currently need.  
- **Separation of Concerns** – Organize code into distinct sections based on functionality.  
- **DRY (Don’t Repeat Yourself)** – Reiterated here for emphasis on reusability.

---

## 3. Design Patterns
### 3.1 Creational Patterns
- **Singleton**  
  - **Quick Note**: Ensures a class has only one instance and provides a global point of access to it.  
  - **Web Example**: Database connection pool or API client instance (e.g., a shared instance of `MongoDB` or `Axios` for HTTP requests).  

- **Factory**  
  - **Quick Note**: Defines an interface for creating objects but lets subclasses decide which class to instantiate.  
  - **Web Example**: A factory function that generates different types of form input elements (`TextInput`, `Checkbox`, `RadioButton`) based on a configuration.

- **Abstract Factory**  
  - **Quick Note**: Provides an interface for creating families of related or dependent objects without specifying their concrete classes.  
  - **Web Example**: A factory for generating UI components for different platforms (e.g., `MaterialUI` vs. `Bootstrap` components).

- **Builder**  
  - **Quick Note**: Constructs a complex object step by step, allowing customization of the object’s construction process.  
  - **Web Example**: Building a dynamic query object for a search filter in a REST API.

- **Prototype**  
  - **Quick Note**: Creates new objects by copying an existing object (a prototype).  
  - **Web Example**: Cloning objects like deeply nested JSON data structures to modify without affecting the original.

---

### 3.2 Structural Patterns
- **Adapter**  
  - **Quick Note**: Converts one interface to another so that incompatible systems can work together.  
  - **Web Example**: Adapting legacy SOAP-based APIs to work with RESTful APIs in a modern web app.

- **Bridge**  
  - **Quick Note**: Decouples an abstraction from its implementation, allowing them to vary independently.  
  - **Web Example**: Decoupling front-end theme management (dark mode vs. light mode) from specific CSS or style implementations.

- **Composite**  
  - **Quick Note**: Composes objects into tree structures to represent part-whole hierarchies, enabling uniform treatment of individual objects and compositions.  
  - **Web Example**: Managing nested UI components like menus, where each menu or submenu is treated uniformly.

- **Decorator**  
  - **Quick Note**: Dynamically adds behaviors to an object without altering its structure.  
  - **Web Example**: Adding middleware to HTTP requests in `Express.js` (e.g., logging, authentication, or validation).

- **Façade**  
  - **Quick Note**: Provides a simplified interface to a larger body of code or subsystem.  
  - **Web Example**: A helper service that combines multiple API calls into a single function for easier use on the front end.

- **Flyweight**  
  - **Quick Note**: Shares common parts of an object to minimize memory usage and improve performance.  
  - **Web Example**: Sharing CSS styles between components using utility-first CSS frameworks like Tailwind CSS.

- **Proxy**  
  - **Quick Note**: Acts as a surrogate or placeholder to control access to another object.  
  - **Web Example**: Using a proxy server for API requests in development to handle CORS issues or route traffic through secure endpoints.

---

### 3.3 Behavioral Patterns
- **Observer**  
  - **Quick Note**: Defines a dependency between objects so that when one object changes state, all its dependents are notified.  
  - **Web Example**: Real-time notifications in a web app using WebSockets or event listeners in JavaScript for DOM updates.

- **Strategy**  
  - **Quick Note**: Defines a family of algorithms and makes them interchangeable to be used at runtime.  
  - **Web Example**: Different strategies for form validation (e.g., client-side, server-side, or hybrid).

- **Command**  
  - **Quick Note**: Encapsulates a request as an object, allowing for parameterization and queuing of requests.  
  - **Web Example**: Undo/redo functionality in a text editor or a web-based drawing app.

- **Iterator**  
  - **Quick Note**: Provides a way to access elements of a collection sequentially without exposing its underlying representation.  
  - **Web Example**: Iterating through a paginated API response to display data in an infinite scroll view.

- **Mediator**  
  - **Quick Note**: Centralizes communication between objects to reduce dependencies between them.  
  - **Web Example**: A central event bus in frameworks like Vue.js or React Context API to handle component communication.

- **Memento**  
  - **Quick Note**: Captures and restores an object's internal state without exposing its implementation.  
  - **Web Example**: Saving the state of a form or a draft in a rich-text editor.

- **Chain of Responsibility**  
  - **Quick Note**: Passes requests along a chain of handlers where each handler decides to process it or pass it further.  
  - **Web Example**: Middleware chaining in `Express.js`, where requests are processed or passed to the next handler.

- **State**  
  - **Quick Note**: Allows an object to alter its behavior when its internal state changes.  
  - **Web Example**: Managing UI states in a React application (e.g., toggling between `loading`, `success`, and `error` states).

- **Template Method**  
  - **Quick Note**: Defines the skeleton of an algorithm, allowing subclasses to define specific steps.  
  - **Web Example**: Base components in React or Angular that define the structure, allowing child components to override specific parts.

- **Visitor**  
  - **Quick Note**: Allows adding new operations to objects without modifying their structure by separating the operation logic.  
  - **Web Example**: A tool that traverses and processes all elements of a DOM tree to apply specific actions like analytics tracking.

- **Interpreter**  
  - **Quick Note**: Defines a grammar for a language and interprets sentences in that language using the grammar.  
  - **Web Example**: Parsing and interpreting search query strings or filters for an e-commerce app.

---

## 4. Systematic Design Thinking

### 4.1 Requirements Analysis
- **Functional requirements** – Features the system must provide.  
- **Non-functional requirements** – Performance, scalability, security, etc.

### 4.2 Modeling Techniques
- **UML diagrams** – Class, Sequence, Use-Case for visualizing designs.  
- **State machines and workflows** – Representing system states and transitions.

### 4.3 Step-by-Step Design Process
1. Identify entities and relationships.  
2. Break down the problem into components.  
3. Optimize for scalability, modularity, and clarity.

---

## 5. Domain-Specific Practices

### 5.1 E-Commerce and Payment Systems
- **Design an Amazon-like marketplace**  
- **Design Splitwise** (including the Simplify Algorithm)  
- **Design Payment Systems**  
- **Design Food Delivery App** (e.g., Swiggy, Zomato)

### 5.2 Gaming and Real-Time Systems
- **Design Chess**  
- **Design Snakes and Ladders**  
- **Design an Elevator System**  
- **Design a Traffic Light System**

### 5.3 Social and Collaborative Platforms
- **Design LinkedIn**  
- **Design a Chat-Based System**  
- **Design a Community Discussion Platform**

### 5.4 Transportation and Logistics
- **Design a Parking Lot**  
- **Design a Car Rental System**  
- **Design a Car Booking Service** (e.g., Ola, Uber)  
- **Design an Airline Management System**

### 5.5 Utilities
- **Design a “Notify-Me” Button**  
- **Design a Logging System**  
- **Design a Calendar Application**  
- **Design a Rate Limiter**

---

## 6. Architectural Styles

### 6.1 Clean Architecture
- **Layered design** – Domain, Application, Interface, Infrastructure.  
- **Dependency Inversion** – Decouple high-level logic from low-level details.

### 6.2 Domain-Driven Design (DDD)
- **Entities and Value Objects**  
- **Aggregates and Repositories**  
- **Bounded Contexts**  
- **Ubiquitous Language**

### 6.3 Hexagonal Architecture (Ports and Adapters)
- **Decoupling core logic** from external systems.  
- **Flexible delivery mechanisms** to accommodate different interfaces.

---

## 7. Distributed Systems and Microservices

### 7.1 Microservices Design
- **Service boundaries and granularity**  
- **RESTful APIs and inter-service communication**  
- **Service discovery and orchestration**

### 7.2 Event-Driven Architecture
- **Event sourcing**  
- **CQRS (Command Query Responsibility Segregation)**  
- **Message brokers** (e.g., Kafka, RabbitMQ)

### 7.3 Distributed Systems Basics
- **CAP theorem** – Consistency, Availability, Partition tolerance.  
- **Data partitioning and replication**  
- **Consensus algorithms** (e.g., Paxos, Raft)

---

## 8. Concurrency and Performance

### 8.1 Concurrency and Multi-threading
- **Thread safety and synchronization**  
- **Deadlock avoidance**  
- **Thread pooling and executors**

### 8.2 Performance Optimization
- **Data structures and algorithm efficiency**  
- **Caching strategies**  
- **Database optimization and query tuning**

---

## 9. Security and Resilience

### 9.1 Security
- **Authentication and authorization** (OAuth, JWT)  
- **Secure coding practices**  
- **Encryption and secure communication**

### 9.2 Resilience
- **Fault-tolerant systems** (Circuit Breaker, retries)  
- **Graceful degradation**  
- **Observability** (monitoring, logging, alerting)

---

## 10. Testing and Quality Assurance

### 10.1 Testing Approaches
- **Unit Testing**  
- **Integration Testing**  
- **Test-Driven Development (TDD)**

### 10.2 Code Reviews
- **Identifying code smells**  
- **Enforcing coding standards**  
- **Continuous refactoring**

---

## 11. Tools and Techniques

### 11.1 UML Tools
- **Lucidchart**  
- **Visual Paradigm**

### 11.2 Dependency Injection Frameworks
- **Spring**  
- **Guice**  
- **Dagger**

### 11.3 Monitoring and Debugging
- **Prometheus, Grafana** for metrics and dashboards  
- **Logging frameworks** (Log4j, SLF4J)

---

## 12. Interview Preparation

### 12.1 Mock Interviews
- Practice explaining designs clearly and concisely.  
- Hone whiteboard problem-solving skills.

### 12.2 Portfolio
- Build reusable design templates for common problems.  
- Host examples on GitHub or personal repositories.

### 12.3 Problem Scenarios
- Practice with real-world designs like **Parking Lot**, **Chess**, or **Rate Limiter** to showcase your understanding.

---

> **Tip:** Constantly revisit previous sections to reinforce your understanding of core principles and patterns. Hands-on practice is crucial—try designing small projects or refactoring existing code to embody these concepts.
