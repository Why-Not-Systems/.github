<p align="center">
  <img src="assets/banner.svg" alt="Why Not Systems: engenharia de IA" width="100%">
</p>

# Por que não construir sistemas melhores?

A **Why Not Systems** é uma equipe de engenharia de IA que transforma tarefas repetíveis em sistemas autônomos.

Projetamos agentes, orquestramos fluxos de trabalho e usamos dados, código e verificações automáticas para construir soluções que operam com mais consistência e menos intervenção manual.

## No que trabalhamos

- Agentes de IA especializados
- Orquestração e automação de fluxos
- Integração com APIs e serviços externos
- Geração e processamento de dados
- Sistemas com validação e publicação controlada

## Como pensamos

- Agentes pequenos e independentes
- Responsabilidades claras
- Decisões baseadas em dados
- Verificação antes da execução ou publicação
- Automatização modular e fácil de manter

## Como funciona

```mermaid
%%{init: {
  "theme": "base",
  "themeVariables": {
    "fontFamily": "JetBrains Mono, Fira Code, monospace",
    "fontSize": "16px",
    "background": "#0B0F18",
    "primaryColor": "#141B29",
    "primaryTextColor": "#F1F5FF",
    "primaryBorderColor": "#64748B",
    "lineColor": "#3EF2C2",
    "secondaryColor": "#0D2428",
    "tertiaryColor": "#1A2338",
    "textColor": "#F1F5FF",
    "clusterBkg": "#0F1623",
    "clusterBorder": "#64748B",
    "edgeLabelBackground": "#141B29"
  },
  "flowchart": {
    "curve": "basis",
    "htmlLabels": true,
    "nodeSpacing": 34,
    "rankSpacing": 46
  }
}}%%
flowchart LR
    INPUT["<b>Dados & Eventos</b><br/>Trigger · API · Agenda"]
    ROUTER{"<b>Orquestração</b>"}

    subgraph AGENTS["<b>AGENTES ESPECIALIZADOS</b>"]
        direction TB
        A["<b>Pesquisa</b>"]
        B["<b>Geração</b>"]
        C["<b>Verificação</b>"]
    end

    VALIDATE["<b>Validação</b><br/>QA & Rules"]
    DECISION{"<b>Ação aprovada?</b>"}
    PUBLISH["<b>Integração ou publicação</b>"]
    REVIEW["<b>Correção ou revisão</b>"]

    INPUT --> ROUTER
    ROUTER --> A
    ROUTER --> B
    ROUTER --> C
    A --> VALIDATE
    B --> VALIDATE
    C --> VALIDATE
    VALIDATE --> DECISION
    DECISION -->|<b>Sim</b>| PUBLISH
    DECISION -->|<b>Não</b>| REVIEW
    REVIEW --> ROUTER

    classDef source fill:#141B29,stroke:#4D90FF,stroke-width:2px,color:#F1F5FF;
    classDef agent fill:#10242A,stroke:#3EF2C2,stroke-width:2px,color:#F1F5FF;
    classDef control fill:#1A2338,stroke:#9D76FF,stroke-width:2px,color:#F1F5FF;
    classDef decision fill:#1A2338,stroke:#C0C9DA,stroke-width:2px,color:#F1F5FF;
    classDef success fill:#10302D,stroke:#3EF2C2,stroke-width:2px,color:#F1F5FF;
    classDef review fill:#251D38,stroke:#9D76FF,stroke-width:2px,color:#F1F5FF;

    class INPUT source;
    class A,B,C agent;
    class ROUTER,VALIDATE control;
    class DECISION decision;
    class PUBLISH success;
    class REVIEW review;
```
