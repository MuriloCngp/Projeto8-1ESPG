<p align="center">
  <img src="https://img.shields.io/badge/Global%20Solution-2026-4ea8de?style=for-the-badge&labelColor=0d0f14" />
  <img src="https://img.shields.io/badge/ASP.NET%20Core-C%23-63d4a8?style=for-the-badge&labelColor=0d0f14" />
  <img src="https://img.shields.io/badge/Python-FastAPI-c49af5?style=for-the-badge&labelColor=0d0f14" />
  <img src="https://img.shields.io/badge/SQL%20Server-Entity%20Framework-f5a623?style=for-the-badge&labelColor=0d0f14" />
</p>

<h1 align="center">🛰️ Space Telemetry — Monitoramento de Fauna</h1>

<p align="center">
  <b>Unindo telemetria espacial e inteligência artificial na proteção da biodiversidade</b><br/>
  Identificação precoce de alterações comportamentais em espécies monitoradas via biotelemetria e satélites LEO.
</p>

---

## 👥 Integrantes

| Nome | RM |
|------|-----|
| Nome Completo | XXXXXXX |
| Nome Completo | XXXXXXX |
| Nome Completo | XXXXXXX |

---

## 📖 Sobre o Projeto

O **Space Telemetry** é um sistema distribuído desenvolvido para auxiliar pesquisadores e órgãos ambientais na identificação precoce de alterações comportamentais em espécies monitoradas.

Dispositivos de biotelemetria acoplados aos animais transmitem dados fisiológicos e geográficos contínuos para satélites de baixa órbita (LEO). Esses dados chegam a uma API ASP.NET Core que os repassa a um serviço de Machine Learning em Python — responsável por detectar anomalias e prever eventos ambientais de risco. Os resultados ficam persistidos no SQL Server para rastreabilidade, histórico e suporte à tomada de decisão.

A arquitetura foi construída sobre princípios de SOA, WebServices, Programação Orientada a Objetos e Repository Pattern, com cada camada tendo responsabilidade única e se comunicando via interfaces bem definidas.

---

## 🎯 Objetivos

- Centralizar dados de telemetria animal em tempo real
- Detectar padrões comportamentais anômalos via Machine Learning
- Gerar alertas preventivos antes que eventos críticos ocorram
- Disponibilizar histórico de análises para pesquisa e tomada de decisão

---

## 🏗️ Arquitetura da Solução

```
┌─────────────────────────────────────────────────────────────────────┐
│                         COLETA DE DADOS                             │
│                                                                     │
│   [ BiotelemetryTag ]  ────────────►  [ LEO Satellite ]            │
│     frequência cardíaca                  transmissão                │
│     aceleração · GPS                     de baixa órbita            │
└─────────────────────────────────┬───────────────────────────────────┘
                                  │ dados brutos
                                  ▼
┌─────────────────────────────────────────────────────────────────────┐
│                        API  ASP.NET CORE                            │
│                                                                     │
│   TelemetryController  ──►  TelemetryPredictionService             │
│                                       │                             │
│                                       ├──────────────────────────┐  │
│                                       ▼                          │  │
│                             PredictionRepository                 │  │
└───────────────────────────────────────┼──────────────────────────┼──┘
                                        │                          │
                    POST /predict        │                          │ salvar
                                        ▼                          ▼
┌──────────────────────────┐   ┌────────────────────────────────────┐
│    ML SERVICE (Python)   │   │          SQL SERVER                │
│                          │   │                                    │
│  FastAPI  ──►  modelos   │   │  PredictionHistory                 │
│                          │   │  SpaceEquipment                    │
│  · Isolation Forest      │   │  Satellite · BiotelemetryTag       │
│  · LSTM                  │   │                                    │
│  · XGBoost               │   └────────────────────────────────────┘
└──────────────────────────┘
          │ resultado
          ▼
   [ Consumer Apps ]
     REST · Swagger
```

---

## 🔄 Fluxo Operacional

```
  [ BiotelemetryTag ]
          │
          │  sinal de biotelemetria
          ▼
  [ LEO Satellite ]
          │
          │  dados coletados
          ▼
  [ TelemetryController ]
          │
          │  solicitação de predição
          ▼
  [ TelemetryPredictionService ]
          │
          ├─────────────────────────────────────┐
          │  POST /predict                      │  salvar histórico
          ▼                                     ▼
  [ Python ML API ]                      [ SQL Server ]
          │
          │  resultado da análise
          ▼
    ┌─────────────┐
    │  Anomalia?  │
    └──────┬──────┘
           │
     ┌─────┴─────┐
     │ sim       │ não
     ▼           ▼
 [ Alerta ]  [ Normal ]
     │           │
     └─────┬─────┘
           │
           ▼
  [ Persistência + REST API ]
```

---

## 🔁 Sequência de Chamadas

```
BiotelemetryTag   Satellite    Controller   PredictionService   Python ML    Database
      │               │             │               │               │            │
      │─ telemetria ─►│             │               │               │            │
      │               │─ dados ────►│               │               │            │
      │               │             │─ predição ───►│               │            │
      │               │             │               │─ POST/predict►│            │
      │               │             │               │◄── resultado ─│            │
      │               │             │               │─ histórico ──────────────►│
      │               │             │               │◄────────────── confirmação─│
      │               │             │◄── retorno ───│               │            │
```

---

## 🧩 Diagrama de Classes

```
                    ┌─────────────────────────┐
                    │    «abstract»           │
                    │     SpaceEquipment      │
                    │─────────────────────────│
                    │  + Id                   │
                    │  + Name                 │
                    │  + TransmitDiagnostic() │
                    └────────────┬────────────┘
                                 │
               ┌─────────────────┴──────────────────┐
               │                                    │
               ▼                                    ▼
  ┌────────────────────────┐          ┌─────────────────────────────┐
  │       Satellite        │          │       BiotelemetryTag       │
  │────────────────────────│          │─────────────────────────────│
  │  + OrbitType           │          │  + SpeciesId                │
  │  + AltitudeKm          │          │  + HeartRate                │
  │  + TransmitDiagnostic()│          │  + Acceleration             │
  └────────────────────────┘          │  + TransmitDiagnostic()     │
                                      └──────────────┬──────────────┘
                                                     │
                                                     ▼
                                      ┌─────────────────────────────┐
                                      │      PredictionHistory      │
                                      │─────────────────────────────│
                                      │  + SpeciesId                │
                                      │  + Probability              │
                                      │  + AlertLevel               │
                                      │  + AnalysisDate             │
                                      └─────────────────────────────┘


  ┌──────────────────────────────────┐     ┌──────────────────────────────────┐
  │  «interface»                     │     │  «interface»                     │
  │  ITelemetryPredictionService     │     │  IGenericRepository<T>           │
  └────────────────┬─────────────────┘     └─────────────────┬────────────────┘
                   │ implements                               │ implements
                   ▼                                          ▼
  ┌──────────────────────────────────┐     ┌──────────────────────────────────┐
  │   TelemetryPredictionService     │────►│       GenericRepository<T>       │
  └──────────────────────────────────┘     └──────────────────────────────────┘
```

---

## 🚀 Tecnologias Utilizadas

### Backend

[![ASP.NET Core](https://img.shields.io/badge/ASP.NET_Core-512BD4?style=for-the-badge&logo=dotnet&logoColor=white&labelColor=0d0f14)](https://dotnet.microsoft.com)
[![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=csharp&logoColor=white&labelColor=0d0f14)](https://learn.microsoft.com/dotnet/csharp)
[![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=for-the-badge&logo=swagger&logoColor=black&labelColor=0d0f14)](https://swagger.io)

### Banco de Dados

[![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white&labelColor=0d0f14)](https://www.microsoft.com/sql-server)
[![Entity Framework](https://img.shields.io/badge/Entity_Framework_Core-512BD4?style=for-the-badge&logo=dotnet&logoColor=white&labelColor=0d0f14)](https://learn.microsoft.com/ef)

### Machine Learning

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white&labelColor=0d0f14)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white&labelColor=0d0f14)](https://fastapi.tiangolo.com)

> Modelos: Isolation Forest · LSTM · XGBoost

---

## 🧠 Conceitos de POO Aplicados

**Encapsulamento** — atributos das entidades protegidos, expostos apenas via propriedades e DTOs.

**Herança** — `SpaceEquipment` é a classe base abstrata; `Satellite` e `BiotelemetryTag` herdam e estendem seu comportamento.

**Polimorfismo** — `TransmitDiagnostic()` é implementado de forma distinta em cada equipamento, preservando a mesma assinatura.

**Abstração** — `SpaceEquipment` define o contrato comum; os detalhes de cada tipo ficam encapsulados nas subclasses.

---

## 🔌 Interfaces

- `IGenericRepository<T>` — operações de persistência (CRUD genérico)
- `ITelemetryPredictionService` — processamento e orquestração das predições

---

## 💉 Injeção de Dependência

Registrada via container nativo do ASP.NET Core:

```csharp
builder.Services.AddScoped(typeof(IGenericRepository<>), typeof(GenericRepository<>));
builder.Services.AddScoped<ITelemetryPredictionService, TelemetryPredictionService>();
builder.Services.AddHttpClient();
```

---

## 📦 DTOs

| DTO | Direção |
|-----|---------|
| `TelemetryDTO` | Request |
| `BiotelemetryTagDTO` | Request |
| `SatelliteDTO` | Request |
| `SpaceEquipmentDTO` | Request / Response |
| `PredictionResponseDTO` | Response |

---

## 🗄️ Banco de Dados

**`PredictionHistory`** — armazena espécie monitorada, coordenadas geográficas, frequência cardíaca, aceleração, tipo de anomalia, probabilidade, nível de alerta e data da análise.

**`SpaceEquipment`** — tabela base (TPH) com discriminator para os subtipos `Satellite` e `BiotelemetryTag`.

---

## 🛡️ Tratamento de Exceções

A exceção customizada `SpaceTelemetryException` centraliza o tratamento de falhas na API Python, erros de comunicação externa, falhas de processamento e exceções não mapeadas nas integrações.

---

## 🔗 Endpoints

### `POST /api/telemetry/predict`

Recebe dados de biotelemetria e retorna uma predição com nível de alerta.

```json
{
  "speciesId":    "ANIMAL-001",
  "latitude":     -23.5505,
  "longitude":    -46.6333,
  "acceleration": 8.5,
  "heartRate":    120
}
```

### `GET /api/telemetry/predictions`

Retorna o histórico completo de predições armazenadas no banco.

---

## 📂 Estrutura do Projeto

```
SpaceTelemetry/
├── Controllers/
│   └── TelemetryController.cs
│
├── Services/
│   └── TelemetryPredictionService.cs
│
├── Repositories/
│   └── GenericRepository.cs
│
├── Interfaces/
│   ├── IGenericRepository.cs
│   └── ITelemetryPredictionService.cs
│
├── Models/
│   ├── SpaceEquipment.cs
│   ├── Satellite.cs
│   ├── BiotelemetryTag.cs
│   ├── PredictionHistory.cs
│   └── Telemetry.cs
│
├── DTOs/
│   ├── RequestDTOs/
│   └── ResponseDTOs/
│
├── Exceptions/
│   └── SpaceTelemetryException.cs
│
├── Profiles/
│   └── TelemetryProfile.cs
│
└── Data/
    └── AppDbContext.cs
```

---

## ▶️ Como Executar

**1. Clone o repositório**
```bash
git clone URL_DO_REPOSITORIO
cd SpaceTelemetry
```

**2. Aplique as migrations**
```bash
dotnet ef database update
```

**3. Suba a aplicação**
```bash
dotnet run
```

**4. Acesse o Swagger**
```
https://localhost:[porta]/swagger
```

> [!NOTE]
> Certifique-se de que o serviço Python de ML está em execução antes de realizar chamadas ao endpoint `/predict`.

---

## 📸 Evidências de Execução

> Adicionar prints de: Swagger em execução · endpoints testados · banco populado · comunicação com a API Python · retornos JSON

---

## 🎥 Demonstração

[▶ Assistir no YouTube](https://youtu.be/5G9euYeWuxI)

---

## ✅ Conclusão

A solução demonstra a aplicação integrada de SOA, WebServices, Programação Orientada a Objetos e Machine Learning na construção de um sistema distribuído para monitoramento ambiental. A arquitetura proposta garante escalabilidade, rastreabilidade e processamento inteligente de dados — contribuindo para pesquisas ambientais e sistemas de alerta preventivo.

---

<p align="center">FIAP · Global Solution 2026 · Engenharia de Software</p>
