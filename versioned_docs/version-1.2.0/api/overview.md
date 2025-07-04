# API Overview

The Alpha API provides comprehensive endpoints for managing your Alpha resources.

## Authentication

All API requests require authentication using API keys:

```typescript
const client = new AlphaClient({
  apiKey: 'your-api-key-here'
});
```

## Core Endpoints

### Projects

- `GET /projects` - List all projects
- `POST /projects` - Create a new project
- `GET /projects/:id` - Get project details

### Resources

- `GET /resources` - List resources
- `POST /resources` - Create a resource

## Rate Limiting

The API is rate limited to 1000 requests per hour per API key.
