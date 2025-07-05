# AWS CDK Constructs

Welcome to Venmo's AWS CDK Constructs documentation. Our TypeScript CDK constructs help you build secure, scalable infrastructure on AWS using proven patterns and best practices.

## What's New in Version 1.2.0

🚀 **Latest Features:**

- New ECS Fargate construct with built-in autoscaling
- Enhanced DynamoDB construct with encryption by default
- Improved Lambda construct with X-Ray tracing enabled
- Updated VPC construct with enhanced security groups

## Getting Started

Venmo's CDK constructs provide:

- **Pre-built Components**: Battle-tested infrastructure patterns
- **Type Safety**: Full TypeScript support with IDE integration
- **Security by Default**: Built-in security best practices
- **Operational Excellence**: Monitoring and logging included

## Quick Start

Install and use our CDK constructs:

```bash
npm install @venmo/cdk-constructs
```

```typescript
import { VenmoLambda, VenmoApiGateway } from '@venmo/cdk-constructs';

const lambda = new VenmoLambda(this, 'MyFunction', {
  functionName: 'my-service',
  // Security and monitoring configured automatically
});
```

## Next Steps

- Check out the [Construct Reference](./api/overview.md)
- Learn about [Configuration](./configuration.md)
- Explore [Examples](./examples.md)
