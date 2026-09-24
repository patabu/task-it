# Task-it

Task-it is a full-stack task management project designed primarily as a practical laboratory for software architecture, design patterns, testing, and AI-assisted development.

The goal is not to build the most innovative task manager possible, but to use a simple and understandable domain to focus on software design quality and the progressive evolution of the system.

The backend represents the main learning focus of the project and will be developed using Java and Spring Boot. The frontend will act as a client for the application and will be developed almost entirely through agentic coding under supervision, without being the main focus of the repository.

## Project Goals

The project is intended to provide hands-on practice with:

* full-stack application design
* separation of concerns
* Clean Architecture
* SOLID principles
* design patterns
* domain modeling
* automated testing
* data persistence
* error handling
* architecture documentation
* containerization
* continuous integration
* using Codex as a development assistant
* reviewing AI-generated code
* incremental development of a GitHub project

## Main Features

Task-it will allow the user to:

* create a task
* view existing tasks
* view task details
* update a task
* delete a task
* assign a priority
* set a due date
* change task progress status
* complete a task
* cancel a task
* filter tasks
* sort tasks according to different criteria

The main task statuses are:

* TODO
* IN_PROGRESS
* DONE
* CANCELLED

The available priorities are:

* LOW
* MEDIUM
* HIGH

## Planned Stack

### Backend

* Java 21
* Spring Boot
* Maven
* PostgreSQL
* Flyway
* JUnit
* Testcontainers

### Frontend

* React
* TypeScript

The frontend is not the main architectural focus of the project and may be implemented primarily using Codex.

### DevOps

* Docker
* Docker Compose
* GitHub Actions

## Architecture

The backend will be developed according to Clean Architecture principles.

The goal is to keep the following concerns separated:

* domain
* application logic
* infrastructure
* API

Relevant architectural decisions will be documented using Architecture Decision Records.

## Design Patterns

Design patterns will be introduced only when they solve an actual problem within the project.

Patterns that may potentially be used include:

* Repository
* Dependency Injection
* Strategy
* Factory
* Adapter
* Specification

The goal of the project is not to use as many design patterns as possible.

## Testing

The project will progressively include:

* unit tests
* domain tests
* use case tests
* integration tests
* API tests
* database integration tests

## Documentation

The repository will include documentation covering:

* architecture
* design decisions
* API
* local setup
* trade-offs
* possible future evolutions

The main architectural decisions will be recorded in:

```text
docs/adr/
```

## Documentation

- [Project scope](docs/scope.md)
- [Requirements](docs/requirements.md)
- [Architecture decisions](docs/adr/)

## Roadmap

### Phase 0 — Project Definition

* [X] Clearly define the project scope
* [X] Define the features included in the first version
* [X] Identify the main entities
* [X] Define task statuses and priorities
* [X] Define the main business rules
* [X] Define what will not be included in the first version
* [X] Create the GitHub repository
* [X] Create the initial README
* [X] Create an initial roadmap

### Phase 1 — Project Bootstrap

* [X] Initialize the backend project
* [X] Configure the build system
* [X] Define the initial project structure
* [ ] Configure development environments
* [ ] Prepare the basic application configuration
* [ ] Verify that the project can be built and executed
* [ ] Configure `.gitignore`
* [ ] Define commit conventions

### Phase 2 — Domain Modeling

* [ ] Define the Task model
* [ ] Define the task identifier
* [ ] Define task statuses
* [ ] Define task priorities
* [ ] Define state transition rules
* [ ] Define domain invariants
* [ ] Define domain errors
* [ ] Define operations that belong to the domain
* [ ] Write tests for domain rules

### Phase 3 — Application Layer

* [ ] Identify application use cases
* [ ] Define the task creation use case
* [ ] Define the task retrieval use case
* [ ] Define the task listing use case
* [ ] Define the task update use case
* [ ] Define the task deletion use case
* [ ] Define the task start use case
* [ ] Define the task completion use case
* [ ] Define the task cancellation use case
* [ ] Define boundaries between the application layer and infrastructure
* [ ] Write use case tests

### Phase 4 — Persistence

* [ ] Configure PostgreSQL
* [ ] Define the initial database schema
* [ ] Introduce database migrations
* [ ] Connect the backend to the database
* [ ] Implement task persistence
* [ ] Correctly handle creation, updates, and deletion
* [ ] Verify mapping between domain and persistence models
* [ ] Write persistence integration tests
* [ ] Test behavior against a real database using containers

### Phase 5 — REST API

* [ ] Define the application's HTTP contract
* [ ] Expose task creation
* [ ] Expose the task list
* [ ] Expose task details
* [ ] Expose task updates
* [ ] Expose task deletion
* [ ] Expose task state transition operations
* [ ] Define request and response models
* [ ] Define error handling
* [ ] Define consistent HTTP status codes
* [ ] Handle invalid input
* [ ] Write API tests

### Phase 6 — Filtering and Sorting

* [ ] Introduce filtering by status
* [ ] Introduce filtering by priority
* [ ] Introduce filtering by due date
* [ ] Introduce sorting by priority
* [ ] Introduce sorting by due date
* [ ] Introduce sorting by creation date
* [ ] Evaluate where to apply the Strategy Pattern
* [ ] Evaluate where to apply the Specification Pattern
* [ ] Write tests for filtering and sorting

### Phase 7 — Frontend

* [ ] Initialize the frontend project
* [ ] Create the main layout
* [ ] Create the task list view
* [ ] Create the task details view
* [ ] Create the task creation form
* [ ] Create the task editing form
* [ ] Integrate task state transition operations
* [ ] Integrate task deletion
* [ ] Integrate filtering
* [ ] Integrate sorting
* [ ] Handle loading states
* [ ] Handle error states
* [ ] Make the interface responsive
* [ ] Connect the frontend to the backend

### Phase 8 — Docker

* [ ] Containerize the backend
* [ ] Containerize the frontend
* [ ] Configure PostgreSQL using a container
* [ ] Create Docker Compose configuration
* [ ] Manage configuration through environment variables
* [ ] Verify that the entire application can be started with a single command
* [ ] Document the Docker setup

### Phase 9 — Architecture Documentation

* [ ] Write `docs/architecture.md`
* [ ] Document layer separation
* [ ] Document allowed dependencies
* [ ] Document the request flow
* [ ] Document the main design patterns used
* [ ] Document architectural trade-offs
* [ ] Create ADRs for the main decisions
* [ ] Document rejected alternatives where relevant

### Phase 10 — Quality

* [ ] Review naming and package structure
* [ ] Remove duplicated code
* [ ] Verify class responsibilities
* [ ] Check for SOLID violations
* [ ] Check for unwanted dependencies between layers
* [ ] Increase test coverage where useful
* [ ] Add static analysis checks
* [ ] Review logging and error handling
* [ ] Perform a complete backend code review

### Phase 11 — CI

* [ ] Create a GitHub Actions workflow
* [ ] Run automated builds
* [ ] Run unit tests
* [ ] Run integration tests
* [ ] Run static analysis checks
* [ ] Verify the frontend build
* [ ] Prevent merging when the pipeline fails
* [ ] Display CI status in the README

### Phase 12 — Security Baseline

* [ ] Validate all inputs
* [ ] Review error handling
* [ ] Avoid exposing internal information
* [ ] Review secret management
* [ ] Review Docker configurations
* [ ] Check for vulnerable dependencies
* [ ] Add `SECURITY.md`
* [ ] Document the main security considerations

### Phase 13 — Final Review

* [ ] Run the application from a clean environment
* [ ] Verify all main features
* [ ] Verify all tests
* [ ] Review documentation
* [ ] Review ADRs
* [ ] Review Git history
* [ ] Remove temporary configurations
* [ ] Remove unnecessary TODOs
* [ ] Improve the README
* [ ] Add frontend screenshots
* [ ] Add an architecture diagram
* [ ] Add API usage examples
* [ ] Prepare a `v1.0.0` release

## Definition of Done

The first version of the project can be considered complete when:

* the backend implements all planned features
* the domain is covered by tests
* the API is covered by integration tests
* PostgreSQL is managed through database migrations
* the frontend and backend communicate correctly
* the entire project can be started using Docker Compose
* the GitHub CI pipeline runs successfully
* the architecture is documented
* the main decisions are documented through ADRs
* the repository can be cloned and executed by following the README alone

## Out of Scope for the First Version

To avoid unnecessary complexity, the first version will not include:

* authentication
* authorization
* user management
* teams
* notifications
* WebSockets
* message brokers
* microservices
* Kubernetes
* Redis
* event sourcing
* CQRS

These features may be introduced later as separate exercises.

## Future Evolution

Once the initial version is complete, Task-it may serve as a foundation for experimenting with different architectures.

Possible future evolutions include:

* authentication and user management
* multi-tenancy
* asynchronous notifications
* event-driven architecture
* CQRS
* domain events
* message brokers
* caching
* audit logging
* observability
* API versioning
* modular monolith
* microservices

The goal will be to compare these evolutions with the initial version and understand when additional architectural complexity provides a real benefit.