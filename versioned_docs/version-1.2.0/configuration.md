# Configuration

Learn how to configure Alpha for your specific needs.

## Environment Variables

Alpha uses the following environment variables:

- `ALPHA_API_KEY` - Your API key
- `ALPHA_ENV` - Environment (development, staging, production)
- `ALPHA_DEBUG` - Enable debug mode (true/false)

## Configuration File

Create an `alpha.config.json` file in your project root:

```json
{
  "apiUrl": "https://api.alpha.com",
  "timeout": 30000,
  "retries": 3,
  "features": {
    "enableCaching": true,
    "enableMetrics": true
  }
}
```

## Advanced Configuration

For advanced use cases, you can use a TypeScript configuration file:

```typescript
// alpha.config.ts
export default {
  apiUrl: process.env.ALPHA_API_URL || 'https://api.alpha.com',
  timeout: 30000,
  retries: 3,
  features: {
    enableCaching: process.env.NODE_ENV === 'production',
    enableMetrics: true
  }
};
```
