# Top Stories GPT

<div align="center">
  <img src="./docs/images/top%20stories%20agent.png" alt="Top Stories GPT - Professional AI Content Generation" width="400"/>
</div>

Your automated content ninja. Transform RSS feeds into polished, executive-style articles that drive decisions. Pick your topic, get fresh insights, and publish with authority – all in minutes, not hours.

## Overview

Top Stories GPT streamlines content creation by turning industry news into sharp, executive-ready articles. It combines GPT technology with automated workflows to deliver professional content that cuts through the noise.

## System Architecture

```mermaid
graph TB
    subgraph Input ["Content Sources"]
        RSS[RSS Feeds]
        API[External APIs]
        Web[Web Content]
    end

    subgraph Processing ["AI Processing Layer"]
        GPT[Top Stories GPT]
        style GPT fill:#2ecc71,stroke:#27ae60,stroke-width:2px
        Analysis[Content Analysis]
        Style[Style Enhancement]
    end

    subgraph Automation ["Automation Layer"]
        Make[Make.com Workflow]
        style Make fill:#3498db,stroke:#2980b9,stroke-width:2px
        Monitor[Performance Monitor]
        Queue[Content Queue]
    end

    subgraph Output ["Distribution"]
        CMS[Webflow CMS]
        style CMS fill:#e74c3c,stroke:#c0392b,stroke-width:2px
        Publish[Auto Publishing]
    end

    RSS --> GPT
    API --> GPT
    Web --> GPT
    GPT --> Analysis
    Analysis --> Style
    Style --> Make
    Make --> Monitor
    Make --> Queue
    Queue --> CMS
    CMS --> Publish

    classDef default fill:#f9f9f9,stroke:#666,stroke-width:1px
    classDef highlight fill:#fff,stroke:#333,stroke-width:2px
```

## Key Features

- **Fast & Fresh**: From RSS to polished article in minutes
- **Executive Edge**: Clear, authoritative business writing
- **Smart Automation**: RSS monitoring to publishing, hands-free
- **Quality Control**: Built-in tone and fact-checking
- **Instant Publishing**: Direct to your CMS, no manual work needed

## Documentation

- [GPT Instructions](docs/gpt-instructions.md): Configuration and content structure
- [Make Workflow](docs/make-workflow.md): Automation pipeline documentation
- [Performance Metrics](docs/performance-metrics.md): System monitoring and optimization
- [Terminology Guide](docs/terminology-guide.md): Professional language guidelines
- [Webflow Integration](docs/webflow-integration.md): CMS configuration and usage

## Example Content

The `/examples` directory contains sample articles demonstrating:
- Professional tone and structure
- Strategic content framing
- Executive-focused insights
- Executive-style formatting

## Getting Started

1. Review the documentation in `/docs`
2. Examine example articles in `/examples`
3. Configure webhook settings in `/src/make`
4. Set up Webflow integration using `/src/webflow`

## System Requirements

- Make.com account with webhook access
- Webflow CMS subscription
- GPT API access
- Node.js environment

## Contributing

1. Fork the repository
2. Create a feature branch
3. Submit a pull request

## License

Copyright 2025. All rights reserved.