# API Reference

Complete API reference for Bravo services.

## Authentication

All API requests require a Bearer token:

```typescript
const response = await fetch('https://api.bravo.com/v1/events', {
  headers: {
    'Authorization': 'Bearer your-token-here',
    'Content-Type': 'application/json'
  }
});
```

## Events API

### Send Event

`POST /v1/events`

Send a single event to Bravo for processing.

**Request Body:**

```typescript
interface EventRequest {
  type: string;
  data: Record<string, any>;
  timestamp?: string;
  metadata?: Record<string, any>;
}
```

**Example:**

```typescript
const event = {
  type: 'user.signup',
  data: {
    userId: '12345',
    email: 'user@example.com'
  },
  metadata: {
    source: 'web-app',
    version: '1.0'
  }
};

const response = await fetch('/v1/events', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer token',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(event)
});
```

### Batch Events

`POST /v1/events/batch`

Send multiple events in a single request.

**Request Body:**

```typescript
interface BatchEventRequest {
  events: EventRequest[];
}
```

## Streams API

### Create Stream

`POST /v1/streams`

Create a new event stream.

```typescript
interface StreamRequest {
  name: string;
  description?: string;
  config: {
    partitions: number;
    retentionMs: number;
  };
}
```

### List Streams

`GET /v1/streams`

Returns a list of all streams.

### Get Stream

`GET /v1/streams/:id`

Get details about a specific stream.

## Webhooks API

### Register Webhook

`POST /v1/webhooks`

Register a webhook endpoint to receive events.

```typescript
interface WebhookRequest {
  url: string;
  events: string[];
  secret?: string;
}
```
