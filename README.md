<div align="center">
  <br />
  <h1>🤖 Agentic VS Code</h1>
  <strong>A Custom-built Visual Studio Code integrated with the Cline AI Coding Assistant</strong>
  <br />
  <br />
  <a href="https://github.com/PreethamNimmagadda02/Agentic-VS-Code/issues">
    <img src="https://img.shields.io/github/issues/PreethamNimmagadda02/Agentic-VS-Code?style=flat-square" alt="Issues" />
  </a>
  <a href="https://github.com/PreethamNimmagadda02/Agentic-VS-Code/pulls">
    <img src="https://img.shields.io/github/issues-pr/PreethamNimmagadda02/Agentic-VS-Code?style=flat-square" alt="Pull Requests" />
  </a>
  <a href="https://github.com/PreethamNimmagadda02/Agentic-VS-Code/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square" alt="License" />
  </a>
  <br />
</div>

<hr />

## 📖 About The Project

Agentic VS Code takes the world's most popular editor, Visual Studio Code, and deeply integrates it with [Cline](https://github.com/cline/cline), a powerful AI coding assistant. This custom build provides seamless access to powerful, autonomous AI capabilities directly from your IDE without complex setup or configuration.

**Key Features:**
- **Pre-packaged AI Integrated Environment**: Visual Studio Code compiled natively for macOS (Apple Silicon).
- **Embedded Cline Assistant**: A bundled, advanced version of the Cline autonomous coding assistant, ready right out of the box.
- **Agentic Capabilities**: Supercharge your development workflow by delegating coding tasks, debugging, and file manipulation securely.

---

## 🏗️ Repository Structure

This repository contains the source code to build the custom IDE. **Note: Compiled builds and disk images are not included in this repository.**

| Component / Subdirectory | Description |
| ------------------------ | ----------- |
| `VS Code/` | The core Visual Studio Code source tree, customized for this agentic build. Contains modifications necessary for seamless AI integration. |
| `Cline/` | The source code for the integrated AI assistant extension (Cline). Contains custom UI, agent logic, and local integration scripts. |

*When built locally, the following artifacts will be generated (they are ignored by Git):*
- `VSCode-darwin-arm64/`: The compiled build output directory targeting macOS on Apple Silicon machines.
- `Agentic-VS-Code.dmg`: The packaged, installable disk image ready for end-user deployment.

---

## 🚀 Getting Started

Since the compiled application is not hosted in this repository, you must build Agentic VS Code from source. Follow the instructions below to get started.

### Prerequisites

You will need the following tools installed on your macOS (Apple Silicon) system:
- **Node.js**: (Consult `.nvmrc` in `VS Code/` for the correct version; generally Node.js 20.x is recommended).
- **Python 3**: Used by native build modules.
- **Native C/C++ build tools**: Run `xcode-select --install` in your terminal.
- **Yarn Classic**: Run `npm install -g yarn`.
- **Gulp**: Needed for building VS Code (`npm install -g gulp-cli`).

### 1. Building the IDE

Navigate to the `VS Code` directory to install dependencies and compile the core editor:

```bash
cd "VS Code"

# Install dependencies for the main VS Code project
yarn install

# Start a background watcher to compile the core code
# (Wait for the initial compilation to complete)
yarn watch
```

To create a full production build and package it for macOS:

```bash
# Inside the "VS Code" directory
yarn run gulp vscode-darwin-arm64-min
```
This will result in the `VSCode-darwin-arm64` directory being created in the root of the project.

### 2. Building the Cline Extension

Navigate to the `Cline` directory to build the AI assistant extension:

```bash
cd ../Cline

# Install dependencies
npm install

# Build the extension
npm run build
```

The compiled extension bundle will be available in `Cline/dist/`. 

### 3. Assembling the Final Application (Optional DMG Packaging)

*(Add your specific packaging script instructions here, e.g., how to combine the compiled VS Code build and the Cline extension into the final `Agentic-VS-Code.dmg`)*

---