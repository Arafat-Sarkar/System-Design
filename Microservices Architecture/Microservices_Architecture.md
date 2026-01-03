# Microservices Architecture

Microservice Architecture is a way of building software where an application is broken into small, independent services.Each service handles one specific function, runs independently, and communicates with others using APIs. Many small, loosely coupled services that can be developed, deployed, and scaled separately.

---

## Agility & faster development 

Microservices allow multiple teams to work in parallel. This helps deliver new features faster and respond quickly to changes.

**Independent deployment:** Each service can be deployed or updated separately without affecting the entire application.

**Smaller codebase:** Every service has a small and focused codebase, making it easier to understand, maintain, and debug.

**Experimentation & innovation:** Teams can safely experiment with new ideas or technologies on individual services without risking the whole system.

---

## Scalability & resilience

Microservices make the system easier to scale and more resilient. Individual services can handle growth and failures independently.

**Horizontal scaling:** Each service can be scaled out by adding more instances instead of upgrading a single server.

**Fault isolation:** If one service fails, it does not bring down the entire application. Other services continue to work normally.

**Increased uptime:** Because failures are isolated and services can be updated independently, the overall system stays available for a longer time.

---

## Organizational alignment & ownership

Microservices help align the organization with the system architecture. Teams clearly own specific services.

**Aligned team and service:** Each team is responsible for one or more services end-to-end, from development to deployment and maintenance.

**Microservice teams:** Teams are small, cross-functional, and focused on a single service, which improves accountability and speed.

**Improved communication & collaboration:** Clear ownership reduces dependency between teams, leading to better communication and smoother collaboration.

---

## Technology flexibility & modernization

Microservices allow organizations to adopt new technologies gradually without rewriting the entire system.

**Polyglot architecture:** Different services can use different programming languages, frameworks, or databases based on what fits best.

**Modular modernization:** Legacy systems can be modernized step by step by breaking them into smaller services.

**Leveraging cloud-native technology:** Microservices work well with cloud-native tools like containers, Kubernetes, auto-scaling, and managed cloud services.

---

## Service

A service is a small, self-contained software component that performs one specific business function. It communicates with other services through well-defined APIs and works independently.

## Service Key Characteristics

**Independent deployment:** A service can be developed, tested, and deployed without impacting other services.

**Focused functionality:**
Each service is responsible for a single, clearly defined task or business capability.

**Loose coupling:**
Services depend on each other as little as possible, interacting only through APIs.

**Private data ownership:**
Each service manages and owns its own data; other services cannot directly access it.

**Technology agnostic:**
A service can be built using any programming language, framework, or database that best fits its needs.

---

## Steps to Migrate from Monolithic to Microservices Architecture

**Step 1: Assessment and Planning** Examine your current monolithic application to understand its structure, dependencies, and pain points. Set clear goals for why you want to migrate and plan the migration strategy carefully.

**Step 2: Decomposition** Break down the monolith into smaller logical modules. Identify which parts can become independent services and how they interact.

**Step 3: Service Identification and Design** Define each microservice clearly, including its responsibility, API contracts, and boundaries. Make sure services focus on single business capabilities.

**Step 4: Technology Selection** Choose the best technology stack, databases, and frameworks for each service, depending on its requirements. Microservices allow different technologies for different services.

**Step 5: Infrastructure Setup** Prepare the environment for running microservices. This includes cloud platforms, containers (like Docker), orchestration tools (like Kubernetes), and CI/CD pipelines.

**Step 6: Implementation** Start building individual services based on the design. Ensure they are independent, modular, and follow coding standards.

**Step 7: Data Management** Decide how each service will manage its own database or storage. Avoid shared databases where possible to ensure independence.

**Step 8: Integration and Interoperability** Enable services to communicate with each other via APIs, message queues, or event-driven mechanisms while keeping them loosely coupled.

**Step 9: Testing and Validation** Test services individually (unit tests) and together (integration tests) to ensure correct functionality, performance, and reliability.

**Step 10: Deployment and Monitoring** Deploy services independently using automated pipelines. Set up monitoring, logging, and alerting to detect issues early.

**Step 11: Incremental Rollout and Refinement** Migrate gradually, starting with non-critical services. Learn from each step, refine services, and fix issues iteratively.

**Step 12: Organizational Alignment and Culture** Align teams and processes to support microservices. Encourage ownership, collaboration, and a culture of continuous improvement.

---

## Communication Between Services

### Synchronous Communication

- Services communicate in real-time.
- The calling service waits for a response before continuing.
- **Common methods:** HTTP/REST, gRPC.

**Example:** Service A requests data from Service B via an API and waits for the response.

### Asynchronous Communication

- Services communicate without waiting for an immediate response.
- The calling service can continue its work while the other service processes the request.
- **Common methods:** Message queues, Event buses, Kafka, RabbitMQ.

**Example:** Service A sends an order message to Service B via a queue and continues processing.

### HTTP / RESTful APIs

- Synchronous communication using standard HTTP requests (GET, POST, PUT, DELETE).
- Data usually in JSON or XML format.
- Simple and widely used, easy to implement.

**Example:** Service A calls Service B via https://serviceb/api/data.

### gRPC and Protocol Buffers

- Synchronous or asynchronous communication using remote procedure calls (RPC).
- Uses Protocol Buffers (compact binary format) for faster serialization.
- Efficient for high-performance, low-latency services.

**Example:** Service A calls a method on Service B directly like a local function.

### GraphQL

- API query language for fetching exactly the data you need.
- One endpoint can return customized responses, reducing over-fetching or under-fetching.
- Can replace REST in some use-cases.

**Example:** Client queries Service B for just name and price of products.

### WebSocket

- Full-duplex, bi-directional communication between client and server.
- Real-time updates like chat apps, notifications, live dashboards.
- Always open connection until closed by client or server.

### Message Queue (MQ)

- Asynchronous communication using queues.
- Services send messages to a queue; other services consume them when ready.
- Helps decouple services and handle high traffic efficiently.
- **Common tools:** RabbitMQ, Kafka, AWS SQS.

**Example:** Service A sends an order to a queue; Service B processes it later.
