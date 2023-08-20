# Microservices Course

## Section 1 - Welcome
"If microservices are implemented incorrectly or used as a band-aid without addressing some of the root flaws in your system, youl'll be unable to do new product development because you're drowning in the complexity." Alexandra Noonan, Engineer, Segment

## Section 3 - Problems with Monolith & SOA
- Single Technology Platform
- Inflexible Deployment
- Inefficient Compute Resources
- Large and Complex
- Complicated and Expensive
- Lack of Tooling

## Section 4 - Microservices Architecture
The term microservices first appeared in 2011.

In 2014 - [Martin Fowler article](https://martinfowler.com/articles/microservices.html).

- Componentization via Services
- Products instead Projects
- Accelerate Development
- Make the app easy to maintain
- Each team decides the standards about development, database, logs, etc.
- Each team is responsible for its service
- Each service has its own database
- Automation of Tests and Deployments
- Handle failure gracefully (SAGA Pattern)

Migrate from monolith to microservices
: Start small and upgrade each part separately

You build, you run it! - Werner Vogels, AWS CTO

## Section 5 - Problems Solved by Microservices
- Single Technology Platform
- |Inflexible Deployment (When one component is updated the whole app is deployed again)
- Inefficient Compute Resources (CPU and RAM)
- Large and Complex (Difficult to maintain)
- Complicated and Expensive ESB (Enterprise Service Bus)
- Lack of Tooling

## Section 6 - Designing Microservices Architecture
"Plan more, code less"

- Mapping the components (Once set - not easy to change) (Data Duplication, Service Query, Aggregation Service)
- Defining Communication Patterns (1 to 1 Sync, 1 to 1 Async, Pub/Sub or Event Driven) (Spiderweb problem - Consul - Gateway)
- Selecting Technology Stack
- Design the Architecture

## Section 7 - Deploying Microservices
CI/CD
: Faster release cycle - Reliability - Reporting

- Containers - Docker
- Kubernetes

## Section 8 - Testing Microservices
- Unit tests
- Integration tests
- End to end tests
- Test Data (Fake - Stub - Mock)

## Section 9 - Service Mesh
- Manages all service-to-service communication
- Platform agnostic
- The service interact only with the service mesh
- Types -> In-Process (DDS Foundation) - Sidecar (More popular - **Istio** - Linkerd - Maesh)
- Not many companies using it

### When to use
- You have a lot of services
- Which communicate a lot with each other
- You have a complex communication requirement with various protocols or brittle network

### Circuit Breaker
- Prevents cascading failures when a service fails
- Example: Monitoring if a service launches N timeouts the circuit breaker stop the service from receiving requests

## Section 10 - Logging and Monitoring
Logging
: Recording the system's activity - Audit - Documenting errors / Should allow tracing end-to-end flow - Should contain as much information as possible - Can be filtered / Creates a service for logging / Winston (Nodejs) - Serilog (.Net Core). Data for logging: Timestamp - User responsible for the action / The event / Severity / Service that is logging / Message / Correlation ID for tracing flows. Prefer Queue for transport data to logging.

Monitoring
: Based on system's metrics - Alerting when needed / Monitor Infrastructure (CPU - RAM - Disk - Network) and Application (Requests/min - Orders/day) / Nagios - Elastic Stack - New Relic - Application Insights

## Section 11 - When Not to Use Microservices
- Small Systems
- When there is no way to separate logic or data
- Microservices systems have **performance** overhead
- Microservices design and implementation takes **time**
- Microservices' main strength is in the short update cycle, so if the system won't have any updates you maybe consider not to use microservices

## Section 12 - Microservices and the Organization
- Conway's Law -> "Any organization that designs a system will produce a design whose structure is a copy of the organization's communication structure."
- Traditional Team
- Go small, quick win

## Section 13 - Anti-Patterns and Common Mistakes
- No Well-Defined Services
- No Well-Defined API

## Section 14 - Breaking Monolith to Microservices
- Motivation for breaking monolith (Modularize the system - Save costs - Modernize the system)
- Strategies for breaking monolith (Must be planned - New Module as Services - Separate Existing Modules to Services - Complete Rewrite)