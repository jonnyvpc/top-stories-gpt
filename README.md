# Top Stories GPT - AI-Powered Executive Content Generator

![Top Stories GPT](docs/images/workflow-diagram.png)

## Overview
Top Stories GPT is a sophisticated content automation system that generates polished, professional articles for C-suite executives. It combines the power of custom GPT with Make.com automation and Webflow CMS to deliver high-quality business content.

## Key Features
- 🤖 Custom GPT with WSJ/FT-inspired writing style
- 🔄 Automated content pipeline via Make.com
- 📊 RSS feed integration for real-time content sourcing
- 🎯 Webflow CMS integration for seamless publishing
- 📝 Sophisticated terminology variation system
- 💼 C-suite focused content structure

## System Architecture
1. **Content Sourcing**
   - RSS feed monitoring for latest tech/business news
   - Webhook system for real-time article fetching

2. **Content Generation**
   - Custom GPT processing with executive-focused tone
   - Structured output format for Webflow CMS
   - Smart terminology variation system

3. **Content Distribution**
   - Automated Webflow CMS integration
   - Professional formatting and image handling
   - Dynamic CTA generation

## Documentation
- [GPT Instructions](docs/gpt-instructions.md)
- [Terminology Guide](docs/terminology-guide.md)
- [Make.com Workflow](docs/make-workflow.md)
- [Webflow Integration](docs/webflow-integration.md)

## Content Structure
Each generated article follows a carefully designed structure:
- Strategic title and attention grabbers
- Executive-focused summaries
- Three-part body with strategic analysis
- Professional image integration
- Dynamic CTAs

## Sample Output
View sample generated articles in the [examples](examples/) directory.

## Getting Started
1. Set up your custom GPT using the instructions in [docs/gpt-instructions.md](docs/gpt-instructions.md)
2. Import the Make.com workflow from [src/make/workflow.json](src/make/workflow.json)
3. Configure your Webflow CMS using the template in [src/webflow/cms-template.json](src/webflow/cms-template.json)

## License
MIT License - See [LICENSE](LICENSE) for details

## Author
Jonathan Jackson