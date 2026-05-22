# FossFLOW - Isometric Diagramming Tool <img width="30" height="30" alt="fossflow" src="https://github.com/user-attachments/assets/56d78887-601c-4336-ab87-76f8ee4cde96" />

<p align="center">
 <a href="README.md">English</a> | <a href="docs/README.cn.md">简体中文</a> | <a href="docs/README.es.md">Español</a> | <a href="docs/README.pt.md">Português</a> | <a href="docs/README.fr.md">Français</a> | <a href="docs/README.hi.md">हिन्दी</a> | <a href="docs/README.bn.md">বাংলা</a> | <a href="docs/README.ru.md">Русский</a> | <a href="docs/README.id.md">Bahasa Indonesia</a> | <a href="docs/README.de.md">Deutsch</a>
</p>

## Try it online
<p align="center">
Go to  <b> --> https://grujowmi.github.io/FossFlow/ <-- </b>
</p>

------------------------------------------------------------------------------------------------------------------------------
FossFLOW is a powerful, open-source Progressive Web App (PWA) for creating beautiful isometric diagrams. Built with React and the <a href="https://github.com/markmanx/isoflow">Isoflow</a> (Now forked and published to NPM as fossflow) library, it runs entirely in your browser with offline support.

- **🤝 [CONTRIBUTING.md](CONTRIBUTING.md)** - How to contribute to the project.

## 🐳 Quick Deploy with Docker

```bash
# Using Docker Compose (recommended - includes persistent storage)
docker compose up

# Or run directly from Docker Hub with persistent storage
docker run -p 80:80 -v $(pwd)/diagrams:/data/diagrams stnsmith/fossflow:latest
```

Server storage is enabled by default in Docker. Your diagrams will be saved to `./diagrams` on the host.

To disable server storage, set `ENABLE_SERVER_STORAGE=false`:
```bash
docker run -p 80:80 -e ENABLE_SERVER_STORAGE=false stnsmith/fossflow:latest
```

## Quick Start (Local Development)

```bash
# Clone the repository
git clone https://github.com/Grujowmi/FossFLOW
cd FossFLOW

# Install dependencies
npm install

# Build the library (required first time)
npm run build:lib

# Start development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Monorepo Structure

This is a monorepo containing two packages:

- `packages/fossflow-lib` - React component library for drawing network diagrams (built with Webpack)
- `packages/fossflow-app` - Progressive Web App which wraps the lib and presents it (built with RSBuild)

### Development Commands

```bash
# Development
npm run dev          # Start app development server
npm run dev:lib      # Watch mode for library development

# Building
npm run build        # Build both library and app
npm run build:lib    # Build library only
npm run build:app    # Build app only

# Testing & Linting
npm test             # Run unit tests
npm run lint         # Check for linting errors

# E2E Tests (Selenium)
cd e2e-tests
./run-tests.sh       # Run end-to-end tests (requires Docker & Python)

# Publishing
npm run publish:lib  # Publish library to npm
```

## How to Use

### Creating Diagrams

1. **Add Items**:
   - Press the "+" button on the top right menu, the library of components will appear on the left
   - Drag and drop components from the library onto the canvas
   - Or right-click on the grid and select "Add node"

2. **Connect Items**: 
   - Select the Connector tool (press 'C' or click connector icon)
   - **Click mode** (default): Click first node, then click second node
   - **Drag mode** (optional): Click and drag from first to second node
   - Switch modes in Settings → Connectors tab

3. **Save Your Work**:
   - **Quick Save** - Saves to browser session
   - **Export** - Download as JSON file
   - **Import** - Load from JSON file

### Storage Options

- **Session Storage**: Temporary saves cleared when browser closes
- **Export/Import**: Permanent storage as JSON files
- **Auto-Save**: Automatically saves changes every 5 seconds to session

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Documentation

- [FOSSFLOW_ENCYCLOPEDIA.md](FOSSFLOW_ENCYCLOPEDIA.md) - Comprehensive guide to the codebase
- [CONTRIBUTING.md](CONTRIBUTING.md) - Contributing guidelines

## License

MIT
