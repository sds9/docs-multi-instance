# SDKs & Developer Tools

Welcome to Venmo's SDKs & Developer Tools documentation! This comprehensive guide covers our TypeScript libraries, CLI tools, and development utilities for building AWS infrastructure.

## What's New in Version 1.2.0

🎉 **Latest Updates:**

- New TypeScript SDK with enhanced type definitions
- Improved CLI with interactive project scaffolding
- Enhanced testing utilities for infrastructure validation
- Updated deployment tools with rollback capabilities

## Overview

Our developer tools ecosystem includes:

- **TypeScript SDK**: Type-safe interfaces for all AWS services
- **CLI Tools**: Command-line utilities for development and deployment
- **Testing Framework**: Comprehensive testing tools for infrastructure
- **VS Code Extensions**: Enhanced development experience with IntelliSense

## Key Features

- **Type Safety**: Full TypeScript support across all tools
- **Developer Experience**: Integrated toolchain for seamless workflows  
- **Testing Support**: Built-in testing utilities and patterns
- **CI/CD Integration**: Ready-to-use GitHub Actions and pipeline templates

## Getting Started

Install the Venmo infrastructure toolkit:

```bash
npm install -g @venmo/infra-cli
npm install @venmo/aws-sdk
```

Initialize a new project:

```bash
venmo-cli init my-service
cd my-service
npm run deploy
```

Example TypeScript SDK usage:

```typescript
import { VenmoAWS } from '@venmo/aws-sdk';

const aws = new VenmoAWS({
  region: 'us-east-1',
  // Authentication and defaults handled automatically
});

// Type-safe DynamoDB operations
const result = await aws.dynamodb.query({
  TableName: 'my-table',
  KeyConditionExpression: 'pk = :pk',
  ExpressionAttributeValues: {
    ':pk': 'user-123'
  }
});
```

## Available Tools

### CLI Tools
- Project scaffolding and templates
- Infrastructure deployment and management
- Environment synchronization
- Debugging and troubleshooting utilities

### SDK Libraries
- Type-safe AWS service clients
- Venmo-specific utilities and helpers
- Built-in retry logic and error handling
- Comprehensive logging and telemetry

### Development Tools
- VS Code extension with snippets and validation
- Testing frameworks and utilities
- Code generators for common patterns
- Performance profiling and optimization tools

## Next Steps

- [Explore Tool Documentation](./architecture.md)
- [View API Reference](./api-reference.md)
- Learn about [Best Practices](./architecture.md)

1. Install Bravo CLI: `npm install -g @bravo/cli`
2. Initialize a new project: `bravo init my-project`
3. Start the development server: `bravo dev`

## Architecture

Bravo follows a distributed architecture pattern with:

- Event brokers
- Stream processors
- Data stores
- API gateways

Learn more in our [Architecture Guide](./architecture.md).
