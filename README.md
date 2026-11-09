# Xagent Documentation

Official documentation for Xagent, an enterprise platform for building, deploying, and operating AI teammates.

## Overview

Run a task directly from the workspace or build a reusable teammate for a specific job. Publish the teammate so end users can reach it through a shareable link, widget, or API.

## Documentation

- [Quick start](https://docs.xagent.co/quickstart)
- [Installation](https://docs.xagent.co/installation)
- [Build a teammate](https://docs.xagent.co/agents/building)
- [Deploy for end users](https://docs.xagent.co/agents/sharing)
- [API reference](https://docs.xagent.co/api-reference/introduction)

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
# Fetch the latest OpenAPI spec from a running Xagent instance
curl http://localhost:8000/openapi.json > ./api-reference/openapi.json

# Regenerate API reference pages from the spec
npx @mintlify/scraping@latest openapi-file ./api-reference/openapi.json -o /tmp/xagent-api-refresh

# Sync generated pages into the docs site without deleting hand-written pages
rsync -a \
  --exclude 'introduction.mdx' \
  --exclude 'websocket/' \
  /tmp/xagent-api-refresh/ ./api-reference/

# If endpoints were removed, delete stale generated files manually as needed
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
