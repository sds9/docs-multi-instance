# Docusaurus Multi-Instance Documentation

This repository demonstrates a complete implementation of [Docusaurus multi-instance documentation](https://docusaurus.io/docs/docs-multi-instance) with TypeScript. It features two independent documentation instances: **Alpha** and **Bravo**.

## 🚀 Quick Start

```bash
# Install dependencies
npm install

# Start development server
npm start

# Build for production
npm run build
```

The site will be available at `http://localhost:3000` with:

- **Alpha Documentation**: `http://localhost:3000/alpha/`
- **Bravo Documentation**: `http://localhost:3000/bravo/`

## 📁 Project Structure

```text
docs-multi-instance/
├── alpha/                    # Alpha documentation source
│   ├── intro.md
│   ├── configuration.md
│   ├── examples.md
│   └── api/
│       └── overview.md
├── bravo/                    # Bravo documentation source
│   ├── intro.md
│   ├── architecture.md
│   └── api-reference.md
├── sidebarsAlpha.ts          # Alpha sidebar configuration
├── sidebarsBravo.ts          # Bravo sidebar configuration
├── docusaurus.config.ts      # Main configuration
├── versioned_docs/           # Alpha versioned docs (v1.0.0)
├── versioned_sidebars/       # Alpha versioned sidebars
├── bravo_versioned_docs/     # Bravo versioned docs (v1.0.0)
├── bravo_versioned_sidebars/ # Bravo versioned sidebars
├── versions.json             # Alpha version metadata
└── bravo_versions.json       # Bravo version metadata
```

## 🔧 Configuration Details

### Multi-Instance Setup

The configuration in `docusaurus.config.ts` sets up two documentation instances:

1. **Alpha (Default Instance)**: Configured in the preset
2. **Bravo (Named Instance)**: Configured as a separate plugin

```typescript
presets: [
  [
    'classic',
    {
      docs: {
        // Alpha instance (default - no id specified)
        path: 'alpha',
        routeBasePath: 'alpha',
        sidebarPath: './sidebarsAlpha.ts',
      },
      // ... other preset options
    },
  ],
],
plugins: [
  [
    '@docusaurus/plugin-content-docs',
    {
      id: 'bravo',  // Named instance
      path: 'bravo',
      routeBasePath: 'bravo',
      sidebarPath: './sidebarsBravo.ts',
    },
  ],
],
```

### Navigation Configuration

The navbar includes links to both documentation instances:

```typescript
navbar: {
  items: [
    {
      type: 'docSidebar',
      sidebarId: 'alphaSidebar',
      position: 'left',
      label: 'Alpha',
    },
    {
      type: 'docSidebar',
      sidebarId: 'bravoSidebar',
      docsPluginId: 'bravo',  // Important: specify plugin ID for named instances
      position: 'left',
      label: 'Bravo',
    },
  ],
},
```

## 📝 Documentation Content

### Alpha Documentation

Comprehensive platform documentation including:

- **Getting Started**: Platform overview and quick start guide
- **API Reference**: Complete API documentation with TypeScript examples
- **Configuration**: Environment variables and config file setup
- **Examples**: Practical usage examples and code samples

### Bravo Documentation

Event-driven architecture documentation including:

- **Overview**: System architecture and key features
- **Architecture**: Distributed system design and components
- **API Reference**: Event streaming and webhook APIs

## 🔄 Versioning

Each documentation instance supports independent versioning:

```bash
# Version Alpha documentation
npm run docusaurus docs:version 1.1.0

# Version Bravo documentation
npm run docusaurus docs:version:bravo 1.1.0
```

### Current Versions

- **Alpha**: `1.0.0` (versioned)
- **Bravo**: `1.0.0` (versioned)

### Versioned Files

- Alpha: `versions.json`, `versioned_docs/`, `versioned_sidebars/`
- Bravo: `bravo_versions.json`, `bravo_versioned_docs/`, `bravo_versioned_sidebars/`

## 🛠 Available Scripts

| Command | Description |
|---------|-------------|
| `npm start` | Start development server |
| `npm run build` | Build for production |
| `npm run serve` | Serve production build locally |
| `npm run clear` | Clear Docusaurus cache |
| `npm run docusaurus docs:version <version>` | Create new Alpha version |
| `npm run docusaurus docs:version:bravo <version>` | Create new Bravo version |

## 🎯 Use Cases

This multi-instance setup is ideal for:

- **Multiple Products**: Separate docs for different products/services
- **Different Audiences**: Developer docs vs. user guides
- **Independent Lifecycles**: Different release cycles and versioning
- **Team Separation**: Different teams managing different doc sets

## 🔗 Key Features Demonstrated

- ✅ TypeScript configuration
- ✅ Multiple documentation instances
- ✅ Independent versioning
- ✅ Separate sidebars and navigation
- ✅ Custom content for each instance
- ✅ Proper routing and URLs
- ✅ Production-ready build

## 📚 Learn More

- [Docusaurus Multi-Instance Documentation](https://docusaurus.io/docs/docs-multi-instance)
- [Docusaurus Configuration](https://docusaurus.io/docs/configuration)
- [Docusaurus Versioning](https://docusaurus.io/docs/versioning)
