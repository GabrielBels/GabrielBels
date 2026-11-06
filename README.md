Senior Software Engineer building LLM agents and AI developer tools on .NET, with a background in high-scale, event-driven platforms.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-gabrielbels-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/gabrielbels/)
[![Integricode](https://img.shields.io/badge/featured-Integricode-6d28d9?style=flat&logo=github&logoColor=white)](https://github.com/GabrielBels/integricode)

I build AI features that have to hold up in production: agents that call tools, answers held to a JSON schema, and plain code that checks what the model says before anyone sees it. Most of my production work lives in private enterprise codebases; the projects below are the public ones you can read end to end.

## Featured: Integricode

[**Integricode**](https://github.com/GabrielBels/integricode) is an AI pull-request reviewer that runs in GitHub Actions. It checks a change for bugs and against the requirement it claims to implement (a `REQ-NNN` entry or a Jira Cloud issue), and publishes only the findings it can back with evidence.

**See it run:** [a real Integricode review](https://github.com/GabrielBels/integricode-demo/pull/1) on a public demo pull request, where it flags an off-by-one that the pull request's 8 passing tests miss.

- **Agent loop** on Microsoft Agent Framework, with OpenAI, Azure OpenAI, and Anthropic behind one `IChatClient` from Microsoft.Extensions.AI.
- **Tool calling under a budget:** the model reads the repository through read-only tools, capped at 40 calls and 400k characters, and answers in a JSON schema.
- **Code decides what gets published:** a finding is dropped unless it points at a real line of the pull request and quotes the requirement verbatim, and a "yes, it solves the requirement" verdict the evidence does not support is downgraded to "partly".
- **Prompt-injection guardrails:** the pull request and the requirement are treated as untrusted data, and a tripwire flags text aimed at AI reviewers.
- **Engineering:** 268 test methods (492 cases), 6 ADRs, tagged releases, and dogfooded on a private SaaS codebase.

Also public: [**claude-mods**](https://github.com/GabrielBels/claude-mods), Claude Code plugins that turn git, Jira, and session history into standups, ticket handoffs, and timesheets.

## What I Work On

- Building LLM agents and AI developer tools: tool calling, structured output, code-side validation, and prompt-injection defenses.
- Integrating LLM and ML capabilities into existing products without overcomplicating the core system.
- Modernizing legacy .NET systems into containerized, Linux-based, CI/CD-driven platforms.
- Designing event-driven workflows with Kafka, MassTransit, background workers, and multi-tenant services.
- Building and tuning GraphQL APIs, especially around N+1 query patterns and DataLoader strategies.
- Migrating persistence layers across SQL Server, PostgreSQL, EF Core, Dapper, and database-first architectures.

## Production Impact

- Reworked a failing saga flow into an event-driven architecture, moving a critical provisioning path from a 99% failure rate under concurrent load to reliable execution for thousands of concurrent requests.
- Helped migrate 500+ customer-specific service instances into a multi-tenant clustered architecture with demand-based scaling.
- Built migration automation that removed roughly 95% of manual comparison and merging work during platform adoption.
- Reduced GraphQL permission-layer latency by about 70% by redesigning the DataLoader strategy.
- Led a .NET Framework 4.7.2 to .NET 9 modernization, including Docker, Linux hosting, PostgreSQL, EF Core, Hangfire, and ASP.NET Identity.
- Reduced monthly infrastructure cost by about 90% through rightsizing and platform modernization.
- Re-engineered a CRM data ingestion pipeline for 300k+ record CSV imports, cutting processing time from over 5 minutes to about 40 seconds.

## Toolbox

```text
AI:              Microsoft Agent Framework, Microsoft.Extensions.AI, OpenAI, Azure OpenAI,
                 Anthropic, tool calling, structured output, RAG
Languages:       C#, JavaScript, SQL
Backend:         .NET, ASP.NET Core, MVC, Hosted Services, Hangfire
Data:            PostgreSQL, SQL Server, EF Core, Dapper
Architecture:    Kafka, MassTransit, GraphQL, microservices, multi-tenant systems
Infrastructure:  Docker, Linux, Windows Server, IIS, GitHub Actions, CI/CD, AWS
Frontend:        React, JavaScript, jQuery
```
