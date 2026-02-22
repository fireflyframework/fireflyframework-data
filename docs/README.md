# fireflyframework-starter-data Documentation

Welcome to the **fireflyframework-starter-data** starter documentation! This starter provides a standardized, production-ready foundation for building data processing microservices in the Firefly ecosystem.

## 📖 What is fireflyframework-starter-data?

`fireflyframework-starter-data` is an opinionated Spring Boot starter that provides two main capabilities:

### 1. **Data Jobs** - Orchestrated Workflows
For executing complex, multi-step workflows that interact with external systems (databases, APIs, file systems, etc.).

**Use Cases:**
- Processing large datasets from external sources
- Running ETL (Extract, Transform, Load) operations
- Coordinating multi-step business processes
- Batch processing and scheduled tasks

**Learn More:** [Data Jobs — Complete Guide →](data-jobs/guide.md)

### 2. **Data Enrichers** - Third-Party Provider Integration
For fetching and integrating data from external third-party providers (credit bureaus, financial data providers, business intelligence services, etc.).

**Use Cases:**
- Enriching customer data with credit scores
- Adding financial metrics from market data providers
- Augmenting company profiles with business intelligence
- Validating addresses or tax IDs with government services

**Learn More:** [Data Enrichers Documentation →](data-enrichers/README.md)

### 3. **Data Quality** - Validation & Quality Gates
Rule-based data validation with configurable strategies (fail-fast or collect-all).

**Learn More:** [Data Quality Framework →](common/data-quality.md)

### 4. **Data Lineage** - Provenance Tracking
Track data transformations and enrichments across your pipeline.

**Learn More:** [Data Lineage Tracking →](common/data-lineage.md)

### 5. **Data Transformation** - Post-Processing Pipelines
Composable transformation chains for field mapping and computed fields.

**Learn More:** [Data Transformation →](common/data-transformation.md)

### 6. **GenAI Bridge** - Native AI Integration
Python bridge package for `fireflyframework-genai` with tools, pipeline steps, and agent templates.

**Learn More:** [GenAI Integration →](common/genai-bridge.md)

---

## 🚀 Quick Start

### Choose Your Path

**I want to build a data job microservice**
→ See the [Data Jobs — Complete Guide](data-jobs/guide.md)

**I want to build a data enricher microservice**
→ See [Data Enrichers - Step-by-Step Guide](data-enrichers/enricher-microservice-guide.md)

**I want to understand the architecture first**
→ See [Architecture Overview](common/architecture.md)

**I want to see code examples**
→ See [Examples](common/examples.md)

---

## 📚 Documentation Structure

### [Data Jobs — Complete Guide](data-jobs/guide.md)
Documentation for building orchestrated workflows (async and sync) in one place.

### [Data Enrichers](data-enrichers/README.md)
Documentation for integrating with third-party providers:
- **[Step-by-Step Guide](data-enrichers/enricher-microservice-guide.md)** - ⭐ Complete guide from scratch
- **[Data Enrichment Reference](data-enrichers/data-enrichment.md)** - Complete reference guide

### [Common Documentation](common/README.md)
Shared concepts, architecture, and utilities:
- **[Architecture Overview](common/architecture.md)** - Hexagonal architecture and design patterns
- **[Configuration Reference](common/configuration.md)** - Comprehensive configuration options
- **[Observability](common/observability.md)** - Distributed tracing, metrics, health checks
- **[Resiliency](common/resiliency.md)** - Circuit breaker, retry, rate limiting patterns
- **[Logging](common/logging.md)** - Comprehensive logging guide
- **[Testing](common/testing.md)** - Testing strategies and examples
- **[MapStruct Mappers](common/mappers.md)** - Data transformation guide
- **[API Reference](common/api-reference.md)** - Complete API documentation
- **[Examples](common/examples.md)** - Real-world usage patterns

### [New Features](common/)
Advanced capabilities added in this release:
- **[Data Quality Framework](common/data-quality.md)** - Rule-based validation and quality gates
- **[Data Lineage Tracking](common/data-lineage.md)** - Provenance and audit trail
- **[Data Transformation](common/data-transformation.md)** - Post-enrichment transformation pipelines
- **[GenAI Bridge](common/genai-bridge.md)** - Native integration with fireflyframework-genai

---

## 🎯 Common Tasks

### Getting Started
- **[Install the library](#installation)** - Add to your project
- **[Create your first data job](data-jobs/guide.md)** - Complete guide (async and sync)
- **[Create your first enricher](data-enrichers/enricher-microservice-guide.md)** - Step-by-step guide

### Configuration
- **[Configure orchestrators](common/configuration.md#orchestration-configuration)** - Airflow, AWS Step Functions, Mock
- **[Configure observability](common/observability.md)** - Tracing, metrics, health checks
- **[Configure resiliency](common/resiliency.md)** - Circuit breaker, retry, rate limiting

### Advanced Topics
- **[Implement SAGA patterns](data-jobs/guide.md#saga-and-step-events)** - Distributed transactions
- **[Create custom operations](data-enrichers/data-enrichment.md#provider-specific-custom-operations)** - Provider-specific workflows
- **[Test your code](common/testing.md)** - Unit and integration testing

---

## 📦 Installation

### Maven

Add the following to your `pom.xml`:

```xml
<!-- Use Firefly's parent POM for standardized dependency management -->
<parent>
    <groupId>org.fireflyframework</groupId>
    <artifactId>fireflyframework-parent</artifactId>
    <version>1.0.0-SNAPSHOT</version>
    <relativePath/>
</parent>

<dependencies>
    <!-- Firefly Common Data Library -->
    <dependency>
        <groupId>org.fireflyframework</groupId>
        <artifactId>fireflyframework-starter-data</artifactId>
        <version>1.0.0-SNAPSHOT</version>
    </dependency>
</dependencies>
```

### Prerequisites

- **Java 21+** - Required for virtual threads and modern language features
- **Maven 3.8+** or Gradle 7+
- **Spring Boot 3.x** knowledge
- **Reactive programming** familiarity (Project Reactor)

---

## ✨ Key Features

### Automatic Observability
- ✅ **Distributed Tracing** - Micrometer integration with OpenTelemetry
- ✅ **Metrics Collection** - Automatic metrics for all operations
- ✅ **Health Checks** - Ready-to-use health check endpoints
- ✅ **Comprehensive Logging** - Structured JSON logging

### Automatic Resiliency
- ✅ **Circuit Breaker** - Prevent cascading failures
- ✅ **Retry Logic** - Exponential backoff with jitter
- ✅ **Rate Limiting** - Protect external APIs
- ✅ **Bulkhead Isolation** - Isolate failures

### Event-Driven Architecture
- ✅ **Automatic Event Publishing** - Job and enrichment lifecycle events
- ✅ **CQRS Integration** - Command/Query separation
- ✅ **SAGA Support** - Distributed transaction patterns

### Data Quality & Lineage
- ✅ **Quality Gates** - Rule-based validation with fail-fast and collect-all strategies
- ✅ **Data Lineage** - Track provenance across enrichments and transformations
- ✅ **Transformation Pipelines** - Composable field mapping and computed fields

### Enrichment Enhancements
- ✅ **Fallback Chains** - Automatic provider failover with `@EnricherFallback`
- ✅ **Per-Provider Resilience** - Independent circuit breaker, retry, rate limiter per provider
- ✅ **Cost Tracking** - Per-provider call counting and cost reports
- ✅ **Preview/Dry-Run** - Preview enrichment routing without execution
- ✅ **SSE Streaming** - Real-time batch enrichment results via Server-Sent Events
- ✅ **Job Timeouts** - Configurable per-stage timeout enforcement

### GenAI Integration
- ✅ **Native Bridge** - Python package for `fireflyframework-genai` integration
- ✅ **AI Agent Tools** - Data enrichment and job management as agent tools
- ✅ **Pipeline Steps** - Enrichment and quality gate steps for GenAI pipelines

### Developer Experience
- ✅ **Abstract Base Classes** - Minimal boilerplate code
- ✅ **Type-Safe APIs** - Compile-time safety
- ✅ **Reactive Programming** - Non-blocking operations with Project Reactor
- ✅ **Comprehensive Testing** - Test utilities and examples

---

## 🏗️ Architecture

The library follows **Hexagonal Architecture** (Ports and Adapters):

```
┌────────────────────────────────────────────────────────────────┐
│                       Your Application                         │
│                                                                │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐          │
│  │  Data Jobs   │  │   Enrichers  │  │  Quality &   │          │
│  │              │  │              │  │  Lineage     │          │
│  │  - Async     │  │  - Credit    │  │  - Rules     │          │
│  │  - Sync      │  │  - Company   │  │  - Tracking  │          │
│  └──────────────┘  └──────────────┘  └──────────────┘          │
│         ↓                  ↓                  ↓                 │
│  ┌──────────────────────────────────────────────────────┐      │
│  │           fireflyframework-starter-data (Core)       │      │
│  │                                                      │      │
│  │  - Abstract base classes    - Fallback chains        │      │
│  │  - Observability (auto)     - Cost tracking          │      │
│  │  - Resiliency (auto/prov)   - Transformation         │      │
│  │  - Event publishing (auto)  - Preview & SSE          │      │
│  └──────────────────────────────────────────────────────┘      │
│         ↓                  ↓                  ↓                 │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐          │
│  │ Orchestrators│  │   Providers  │  │  GenAI       │          │
│  │              │  │              │  │  Bridge      │          │
│  │  - Airflow   │  │  - REST APIs │  │  - Tools     │          │
│  │  - AWS SF    │  │  - SOAP APIs │  │  - Steps     │          │
│  │  - Mock      │  │  - gRPC APIs │  │  - Agents    │          │
│  └──────────────┘  └──────────────┘  └──────────────┘          │
└────────────────────────────────────────────────────────────────┘
```

**Learn More:** [Architecture Overview](common/architecture.md)

---

## 📖 Documentation Index

### By Feature
- **[Data Jobs — Complete Guide](data-jobs/guide.md)** - Orchestrated workflows
- **[Data Enrichers](data-enrichers/README.md)** - Third-party provider integration

### By Topic
- **[Architecture](common/architecture.md)** - Design patterns and principles
- **[Configuration](common/configuration.md)** - All configuration options
- **[Observability](common/observability.md)** - Monitoring and tracing
- **[Resiliency](common/resiliency.md)** - Fault tolerance patterns
- **[Testing](common/testing.md)** - Testing strategies
- **[Examples](common/examples.md)** - Real-world code examples

---

## 🤝 Support

For questions, issues, or contributions:
- Check the [Examples](common/examples.md) for common patterns
- Review the [API Reference](common/api-reference.md) for detailed API docs
- See the [Architecture Overview](common/architecture.md) for design decisions

---

## 📝 License

Copyright © 2024-2026 Firefly Software Solutions Inc. All rights reserved.

