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
Effective requirements analysis involves asking the right questions, understanding the problem deeply, and clarifying ambiguities. Follow these steps:

#### **Gathering Requirements**
- **Ask Questions About Functional Requirements**
  - What are the core features of the system?  
  - What inputs and outputs are expected?  
  - What workflows or user actions need to be supported?  
  - Are there edge cases or specific scenarios to handle?  
  - Who are the primary users, and what are their goals?

- **Ask Questions About Non-Functional Requirements**
  - What is the expected load on the system (e.g., users, requests per second)?  
  - How should the system respond to failure (resilience)?  
  - What level of security is needed (e.g., encryption, authentication)?  
  - Are there constraints for scalability, performance, or latency?  
  - What are the maintainability and extensibility expectations?

- **Clarify Business Goals**
  - What problem is the system solving for the business?  
  - How does success look for the stakeholders?  
  - What are the budget and timeline constraints?  

- **Document Assumptions and Constraints**
  - What external systems or APIs does the solution rely on?  
  - What technologies or frameworks are mandated?  
  - Are there compliance or regulatory requirements?  

#### **Think Systemically**
- How will data flow through the system?  
- What integrations or dependencies exist (e.g., third-party APIs)?  
- Are there long-term goals to consider (future-proofing)?  

#### **Validating Requirements**
- Create user stories or scenarios to validate understanding.  
- Prioritize requirements based on impact and feasibility.  
- Collaborate with stakeholders to resolve ambiguities.

---

### 4.2 Modeling Techniques
Use modeling tools to represent and visualize your design for better clarity and communication:

- **UML Diagrams**  
  - **Class Diagram**: Define entities, their attributes, and relationships.  
  - **Sequence Diagram**: Depict the interactions between objects over time.  
  - **Use-Case Diagram**: Highlight user interactions with the system.

- **State Machines and Workflows**  
  - Represent system states and transitions (e.g., `Order` state transitioning from `Pending` → `Shipped` → `Delivered`).  
  - Define workflows for processes like user registration, checkout, or API request handling.

---

### 4.3 Step-by-Step Design Process

1. **Understand the Problem**
   - Revisit the gathered requirements and confirm understanding.  
   - Identify constraints (e.g., budget, technology stack).  
   - Break the problem into smaller sub-problems.

2. **Identify Entities and Relationships**
   - Define the core objects in the system (e.g., `User`, `Product`, `Order`).  
   - Map relationships (e.g., one-to-many, many-to-many).  
   - Document key attributes and behaviors for each entity.

3. **Define System Boundaries**
   - Identify what is in scope and out of scope for the system.  
   - Determine the interfaces (e.g., REST APIs, database access).

4. **Divide into Components**
   - Break the system into logical modules (e.g., `Authentication`, `Order Management`).  
   - Ensure components are loosely coupled and highly cohesive.  
   - Define clear APIs or contracts for communication between modules.

5. **Design Data Flow**
   - Define how data moves between components (e.g., user input → backend → database → response).  
   - Map out CRUD operations for core entities.

6. **Focus on Scalability and Modularity**
   - Choose scalable patterns (e.g., microservices, load balancing).  
   - Ensure each component can evolve independently.  
   - Avoid monolithic designs unless simplicity is a priority.

7. **Optimize for Performance**
   - Identify performance bottlenecks early (e.g., query-heavy modules).  
   - Use caching, indexing, and efficient algorithms where needed.

8. **Add Fault Tolerance and Resilience**
   - Plan for failures (e.g., retries, circuit breakers).  
   - Define a monitoring and alerting strategy.

9. **Document the Design**
   - Use diagrams, descriptions, and specifications for clarity.  
   - Highlight trade-offs and decisions made during design.

10. **Review and Iterate**
    - Share the design with peers or stakeholders for feedback.  
    - Revise based on practical constraints or new insights.

---

> **Pro Tip**: Always validate your design with real-world scenarios, prototypes, or test cases before implementation. Focus on making the design extensible and maintainable for long-term success.

---
Here’s the updated markdown with the detailed hints for Domain-Specific Practices:

## 5. Domain-Specific Practices

### 5.1 E-Commerce and Payment Systems

#### **Design an Amazon-like Marketplace**
- **Catalog and Inventory**
  - How to store product details (name, price, description) and maintain inventory counts.
  - Handling large-scale searches (e.g., indexing, caching, product recommendations).
- **Shopping Cart and Order Management**
  - Managing concurrent modifications to a cart, especially with promotions or limited stock.
  - Handling order lifecycles: created → paid → shipped → delivered → returned/refunded.
- **Payments and Checkout**
  - Payment gateway integrations (credit cards, digital wallets).
  - Secure handling of payment data and PCI compliance; transaction retries and idempotency.
- **User Accounts and Authentication**
  - Session management, OAuth, or token-based auth (e.g., JWT).
  - Wishlist, order history, and user preferences.
- **Scalability and Performance**
  - Load balancing and caching strategies (CDN for static content).
  - Database partitioning and indexing for product searches.

#### **Design Splitwise** (including the Simplify Algorithm)
- **Data Modeling**
  - Representing expenses, users, groups, and shares for each expense.
  - Handling different currencies and exchange rates if needed.
- **Expense Sharing and Balancing**
  - Tracking who owes whom and simplifying outstanding balances (Simplify Algorithm).
  - Ensuring accurate rounding and avoiding floating-point inaccuracies.
- **Concurrency and Consistency**
  - Preventing conflicts when multiple users update expenses concurrently.
  - Ensuring consistency in the final ledger.
- **Notifications and Activity Feeds**
  - Real-time updates on new expenses, settled amounts, or changes in group splits.
- **Security and Auditing**
  - Secure handling of sensitive payment details.
  - Maintaining an audit log of changes for transparency.

#### **Design Payment Systems**
- **Payment Flow and Gateways**
  - Steps for authorization, capture, and settlement.
  - Supporting multiple gateways (e.g., PayPal, Stripe) and fallback mechanisms.
- **Security and Compliance**
  - PCI-DSS requirements, tokenization of card details, and encryption.
  - Fraud detection measures (e.g., velocity checks, suspicious activity alerts).
- **Idempotency and Error Handling**
  - Unique transaction IDs to avoid duplicate charges.
  - Handling network failures, timeouts, and partial payments.
- **Ledger and Reconciliation**
  - Maintaining a reliable record of transactions for auditing.
  - Reconciling with external banking systems or payment gateways.
- **Refunds and Chargebacks**
  - Tracking partial vs. full refunds and managing disputes.

#### **Design a Food Delivery App** (e.g., Swiggy, Zomato)
- **Restaurants and Menu Management**
  - Handling dynamic menus, item availability, and real-time updates.
  - Managing promotions, pricing, and personalized recommendations.
- **Order Lifecycle**
  - Stages: order created → payment → order accepted by restaurant → food prepared → delivery → completion.
  - Real-time status updates and notifications to users.
- **Delivery Logistics**
  - Delivery agent assignment, route optimization, and real-time tracking (GPS).
  - Concurrency with multiple orders in transit; load balancing for delivery partners.
- **Scalability and Reliability**
  - Handling peak hours and large traffic surges.
  - Using caching (e.g., for popular items) and microservices for modular scaling.
- **Payment and Refunds**
  - Integration with multiple payment methods and handling refunds for cancelled orders.

---

### 5.2 Gaming and Real-Time Systems

#### **Design Chess**
- **Board and Pieces Representation**
  - Data structures to model the board (2D array, list of piece objects).
  - Representing allowed moves and special moves (castling, en-passant).
- **Move Validation and Game Rules**
  - Checking for check, checkmate, or stalemate conditions.
  - Encapsulating piece-specific logic to avoid code duplication.
- **Multiplayer and Concurrency**
  - Real-time or turn-based gameplay; avoiding race conditions.
  - Synchronizing game state across players.
- **Persistence and Replay**
  - Saving game state for resuming or reviewing moves later.
  - Move history for undo/redo functionality.

#### **Design Snakes and Ladders**
- **Board Layout**
  - Storing snake and ladder positions for quick lookups.
  - Designing for scalability if board size changes.
- **Game Mechanics**
  - Random dice rolling and turn-based moves.
  - Managing multiple players and ensuring smooth concurrency.
- **State Management**
  - Tracking player positions and verifying game end conditions.

#### **Design an Elevator System**
- **Scheduling Algorithms**
  - Simple up/down logic or optimized scheduling (e.g., SCAN, priority queues).
  - Handling peak vs. off-peak traffic.
- **System State and Concurrency**
  - Managing multiple elevators concurrently.
  - Preventing race conditions or deadlocks.
- **Fail-Safes and Safety Protocols**
  - Emergency stops, overload detection, and error handling.

#### **Design a Traffic Light System**
- **State Machine**
  - Light states (red, yellow, green) and transitions.
  - Timers and adaptive logic based on traffic density.
- **Concurrency and Coordination**
  - Synchronizing multiple intersections.
  - Preventing overlaps (two directions both green).
- **Scalability**
  - Supporting multiple signals across a city.
  - Real-time monitoring and malfunction alerts.

---

### 5.3 Social and Collaborative Platforms

#### **Design LinkedIn**
- **User Profiles and Connections**
  - Modeling professional data, endorsements, and recommendations.
  - Differentiating connections, followers, and groups.
- **Feed and Content Management**
  - Posts, shares, comments, and relevance-based ranking.
  - Handling real-time updates or notification feeds.
- **Search and Indexing**
  - Efficient searching for people, jobs, and companies.
- **Messaging and Notifications**
  - Real-time chat, read receipts, and alerts.

#### **Design a Chat-Based System**
- **Real-Time Messaging**
  - WebSocket or long-polling approach for instant communication.
  - Handling concurrency and message delivery order.
- **Data Storage and Offline Support**
  - Saving message history and syncing messages after reconnect.
- **Scalability and Sharding**
  - Partitioning chat rooms or user data for large-scale systems.
- **Security**
  - End-to-end encryption and spam mitigation.

#### **Design a Community Discussion Platform**
- **Threaded Discussions**
  - Structuring posts, comments, and nested replies.
  - Implementing moderation tools for reporting/blocking.
- **User Reputation and Voting**
  - Upvotes/downvotes, gamification (badges, karma).
- **Notifications and Subscriptions**
  - Alerts for topics or threads with batching to avoid spam.

---

### 5.4 Transportation and Logistics

#### **Design a Parking Lot**
- **Slots and Vehicle Types**
  - Differentiating between vehicle sizes.
  - Real-time slot availability updates.
- **Ticketing and Payment**
  - Entry/exit time tracking and charge calculation.
  - Subscription-based passes or lost ticket handling.

#### **Design a Car Rental System**
- **Inventory Management**
  - Tracking vehicle availability and maintenance schedules.
  - Preventing double bookings.
- **Reservation and Billing**
  - Payment handling and handling penalties for late returns.
- **User Management**
  - Verifying licenses and multi-location drop-offs.

#### **Design a Car Booking Service** (e.g., Ola, Uber)
- **Real-Time Matching**
  - GPS-based dispatch algorithms.
  - Surge pricing and peak hour concurrency.
- **Trip Management**
  - Fare calculations and progress tracking.
- **Driver and Rider Experience**
  - Ratings, feedback loops, and safety features.

#### **Design an Airline Management System**
- **Flight Scheduling**
  - Managing routes, timetables, and overbooking policies.
- **Ticketing and Reservations**
  - Fare classes, seat assignments, and multi-leg journeys.
- **Integration with External Systems**
  - Check-in kiosks and baggage handling.

---

### 5.5 Utilities

#### **Design a “Notify-Me” Button**
- **User Subscription Flow**
  - Registering for notifications and handling unsubscribes.
- **Notification Triggers**
  - Event-driven notifications with idempotency.
- **Scalability**
  - Handling spikes in notifications.

#### **Design a Logging System**
- **Data Ingestion**
  - Collecting logs from distributed applications.
- **Storage and Indexing**
  - Retention policies and query efficiency.
- **Querying and Analysis**
  - Real-time search and alerting.

#### **Design a Calendar Application**
- **Event Creation**
  - Managing recurring events and time zone adjustments.
- **Reminders**
  - Push, email, or SMS reminders with custom intervals.
- **Collaboration**
  - Shared calendars, invites, and conflict resolution.

#### **Design a Rate Limiter**
- **Core Algorithm**
  - Leaky Bucket, Token Bucket, or Sliding Window techniques.
- **Implementation**
  - Using in-memory stores (Redis) and ensuring concurrency safety.
- **Edge Cases**
  - Handling rate limits being reached gracefully.

---
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
