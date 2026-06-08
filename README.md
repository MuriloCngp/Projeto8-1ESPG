# 🏗️ Arquitetura da Solução

A arquitetura foi construída seguindo princípios de:

- SOA (Service-Oriented Architecture)
- WebServices
- Repository Pattern
- Dependency Injection
- Programação Orientada a Objetos
- RESTful APIs

## Diagrama de Arquitetura

```mermaid
flowchart TD

    BT["🐾 BiotelemetryTag"]
    SAT["🛰️ Satellite"]

    BT --> SAT

    SAT --> Controller

    subgraph PRESENTATION["Presentation Layer"]
        Controller["TelemetryController"]
        IService["ITelemetryPredictionService"]
        IRepository["IGenericRepository<T>"]
    end

    subgraph SERVICE["Service Layer"]
        Service["TelemetryPredictionService"]
        HttpClient["HttpClientFactory"]
    end

    Controller --> Service
    IService -. Dependency Injection .-> Service
    Service --> HttpClient

    subgraph ML["Machine Learning API"]
        Python["Python ML API"]
        Models["Isolation Forest | LSTM | XGBoost"]
    end

    Service --> Python
    Python --> Models

    subgraph REPOSITORY["Repository Layer"]
        Repo["PredictionHistoryRepository"]
        EF["Entity Framework Core"]
    end

    Models --> Repo
    Repo --> EF

    subgraph DATABASE["SQL Server"]
        DB["PredictionHistory"]
    end

    EF --> DB

    Decision{"Critical Alert?"}

    DB --> Decision

    Critical["🚨 Notify Team"]
    Normal["📋 Store History"]

    Decision --> Critical
    Decision --> Normal

    Critical --> API["REST API"]
    Normal --> API

    API --> User["👩‍🔬 Researcher"]
```
