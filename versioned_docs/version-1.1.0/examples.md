# Examples

Here are some practical examples of using Alpha.

## Basic Usage

```typescript
import { AlphaClient } from '@alpha/sdk';

const client = new AlphaClient({
  apiKey: process.env.ALPHA_API_KEY
});

async function createProject() {
  const project = await client.projects.create({
    name: 'My First Project',
    description: 'A sample project'
  });
  
  console.log('Created project:', project.id);
}
```

## Advanced Usage

```typescript
import { AlphaClient, ProjectConfig } from '@alpha/sdk';

const client = new AlphaClient({
  apiKey: process.env.ALPHA_API_KEY,
  timeout: 10000
});

async function advancedExample() {
  // Create a project with custom configuration
  const config: ProjectConfig = {
    name: 'Advanced Project',
    settings: {
      autoBackup: true,
      encryptionEnabled: true
    }
  };
  
  const project = await client.projects.create(config);
  
  // Add resources to the project
  const resource = await client.resources.create({
    projectId: project.id,
    type: 'database',
    config: {
      size: 'large',
      region: 'us-east-1'
    }
  });
  
  console.log('Project and resource created successfully');
}
```

## Error Handling

```typescript
import { AlphaClient, AlphaError } from '@alpha/sdk';

const client = new AlphaClient({
  apiKey: process.env.ALPHA_API_KEY
});

async function withErrorHandling() {
  try {
    const project = await client.projects.create({
      name: 'Test Project'
    });
  } catch (error) {
    if (error instanceof AlphaError) {
      console.error('Alpha API Error:', error.message);
      console.error('Error Code:', error.code);
    } else {
      console.error('Unexpected error:', error);
    }
  }
}
```
