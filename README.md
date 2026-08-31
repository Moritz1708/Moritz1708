# Moritz Waldau

**IT Consultant @ Cluster Reply — .NET, Azure, and agentic AI.**

I design and modernize .NET systems that people actually depend on, and I spend a lot of my time
these days on where AI agents fit into that work.

![C#](https://img.shields.io/badge/C%23-512BD4?style=flat-square&logo=csharp&logoColor=white)
![.NET](https://img.shields.io/badge/.NET_4.8--10-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![Blazor](https://img.shields.io/badge/Blazor-512BD4?style=flat-square&logo=blazor&logoColor=white)
![.NET MAUI](https://img.shields.io/badge/.NET_MAUI-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![.NET Aspire](https://img.shields.io/badge/.NET_Aspire-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![MCP](https://img.shields.io/badge/Model_Context_Protocol-000000?style=flat-square)

## About

After a dual study program in Business Information Systems (B.Sc.), I worked at Swiss Life
Germany on applications used daily by more than 13,000 advisors. Today I own the maintenance and
evolution of a .NET 4.8 legacy application, make the architecture calls, and help the client
prioritize the epics on the way to a modern .NET 9 MAUI solution.

AI-assisted development is a fixed part of that day: I work with Claude Code and GitHub Copilot
daily, build AI agents and my own MCP servers, and follow the agentic space firsthand.

Away from the keyboard you'll find me in the mountains — hiking in summer, skiing in winter.

## Featured — OrderSphere

My reference architecture for modern e-commerce systems: eight microservices on .NET 10, cut
along Clean Architecture and Domain-Driven Design boundaries, with CQRS over MediatR and a
`Result<T>` pattern throughout instead of exceptions. Every service owns its PostgreSQL database
and communicates asynchronously over Azure Service Bus with the Outbox/Inbox pattern.

```mermaid
flowchart LR
    UI[Blazor WASM<br/>MudBlazor] --> GW[YARP Gateway + BFF<br/>Auth0 OIDC]
    GW --> CAT[Catalog]
    GW --> BAS[Basket]
    GW --> ORD[Ordering]
    GW --> PAY[Payment]
    GW --> USR[UserProfile]
    GW --> ADV[Advisory<br/>Azure OpenAI + MCP]
    CAT --> DB[(PostgreSQL<br/>one per service)]
    ORD --> DB
    PAY --> DB
    CAT --> RD[(Redis<br/>HybridCache)]
    BAS --> RD
    ORD -->|Outbox| SB{{Azure Service Bus}}
    SB -->|Inbox| NOT[Notification]
    SB --> WHK[Webhooks]
```

- 8 microservices · Clean Architecture · DDD · CQRS
- Outbox/Inbox over Azure Service Bus, one PostgreSQL database per service
- AI advisory agent on Azure OpenAI with a custom MCP server
- CI with a 70% coverage gate, CodeQL, Gitleaks and Trivy
- azd/Bicep deployment to Azure Container Apps

**[→ OrderSphere](https://github.com/Moritz1708/OrderSphere)**

## Elsewhere on GitHub

- **[Portfolio](https://github.com/Moritz1708/Portfolio)** — my personal site, [live here](https://moritz1708.github.io/Portfolio/)
- **[EmployeeManagementSystem](https://github.com/MoritzWaldau/EmployeeManagementSystem)** — cloud-native .NET 9 app with Aspire, Docker and GitHub Actions, deployed to Azure Container Apps (on my second account, [@MoritzWaldau](https://github.com/MoritzWaldau))

## Contact

- [LinkedIn](https://www.linkedin.com/in/moritz-waldau-0a5778238/)
- [Portfolio](https://moritz1708.github.io/Portfolio/)
- moritzwaldau99@gmail.com
