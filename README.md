# Xagent Documentation

Official documentation for Xagent - The Agent Operating System.

## Overview

Xagent is an AI agent platform that enables you to describe goals and let agents figure out how to accomplish them. No workflow engineering required.

## Documentation

- [Quick Start](/quickstart) - Get started in minutes
- [Installation](/installation) - Deployment and setup guide
- [API Reference](/api-reference/introduction) - Complete API documentation

## Development

Install the Mintlify CLI to preview documentation changes locally:

```bash
npm i -g mint
```

Run the following command at the root of the documentation:

```bash
mint dev
```

View your local preview at `http://localhost:3000`.

## Updating API Documentation

API documentation is auto-generated from OpenAPI specification. To update:

```bash
# Fetch latest OpenAPI spec from running Xagent instance
curl http://localhost:8000/openapi.json > api-reference/openapi.json

# Regenerate API docs (if needed)
npx @mintlify/scraping@latest openapi-file ./api-reference/openapi.json -o api-reference
```

## Publishing Changes

Install the Mintlify GitHub app from your [dashboard](https://dashboard.mintlify.com/settings/organization/github-app) to deploy changes automatically. Changes are deployed to production after pushing to the default branch.

## Project Structure

```
xagent-docs/
├── api-reference/     # Auto-generated API documentation
├── agents/           # Agent documentation
├── deployment/       # Deployment and configuration
├── files/            # File management
├── guides/           # User guides
├── images/           # Documentation images
├── knowledge/        # Knowledge base docs
├── memory/           # Memory system docs
├── models/           # Model documentation
├── monitoring/       # Monitoring and observability
├── tasks/            # Task execution docs
├── templates/        # Template documentation
├── tools/            # Tool documentation
├── docs.json         # Navigation configuration
└── package.json      # Dependencies
```

## License

This documentation is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0).

## Links

- [Xagent GitHub](https://github.com/xorbitsai/xagent)
- [Mintlify Documentation](https://mintlify.com/docs)
