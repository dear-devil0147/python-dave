import { defineConfig } from 'vitest/config';
import react from '@vitejs/plugin-react';
import path from 'path';

export default defineConfig({
  plugins: [react()],
  test: {
    globals: true,
    environment: 'jsdom',
    setupFiles: [],
    coverage: {
      provider: 'v8',
      reporter: ['text', 'json', 'html'],
      exclude: [
        'node_modules/',
        'dist/',
      ]
    }
  },
  resolve: {
    alias: {
      '@': path.resolve(__dirname, './src'),
    },
  },
});
# Contributing to Effective Space Bassoon

Thank you for your interest in contributing! This document provides guidelines and instructions for contributing to this project.

## Code of Conduct

This project adheres to the Contributor Covenant Code of Conduct. By participating, you are expected to uphold this code.

## Getting Started

1. Fork the repository
2. Clone your fork locally
3. Install dependencies: `npm ci`
4. Create a feature branch: `git checkout -b feature/your-feature-name`

## Development Process

1. Make your changes
2. Run tests: `npm test`
3. Run linter: `npm run lint` (if available)
4. Commit with clear messages
5. Push to your fork
6. Open a Pull Request

## Code Standards

- Follow the existing code style
- Use meaningful variable and function names
- Add comments for complex logic
- Write tests for new features
- Keep commits atomic and well-documented

## Testing

- All tests must pass before merging
- Add tests for new features
- Maintain or improve code coverage
- Run: `npm test`

## Pull Request Process

1. Update documentation as needed
2. Add a clear description of changes
3. Link related issues
4. Ensure all CI checks pass
5. Request review from maintainers

## Reporting Issues

- Use clear, descriptive titles
- Provide steps to reproduce
- Include expected vs actual behavior
- Share your environment details

## Questions?

Feel free to open an issue for questions or discussions.
# Effective Space Bassoon

A React application built with Vite, featuring modern development tools and best practices.

## Features

- ⚛️ React 18
- ⚡ Vite for fast development
- 🧪 Vitest for unit testing
- 🎨 Modern JavaScript/ES modules
- 📦 Optimized builds

## Getting Started

### Prerequisites

- Node.js 18+ or 20+
- npm or yarn

### Installation

```bash
npm install{
  "semi": true,
  "trailingComma": "es5",
  "singleQuote": true,
  "printWidth": 80,
  "tabWidth": 2,
  "useTabs": false,
  "arrowParens": "always"
}
name: CI

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main, develop]

jobs:
  test:
    runs-on: ubuntu-latest

    strategy:
      matrix:
        node-version: [18.x, 20.x]

    steps:
      - uses: actions/checkout@v4

      - name: Use Node.js ${{ matrix.node-version }}
        uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node-version }}
          cache: 'npm'

      - name: Install dependencies
        run: npm ci

      - name: Run linter
        run: npm run lint --if-present

      - name: Run tests
        run: npm test

      - name: Build
        run: npm run build
# Dependencies
node_modules/
/.pnp
.pnp.js

# Testing
/coverage

# Production
/build
/dist

# Misc
.DS_Store
.env
.env.local
.env.development.local
.env.test.local
.env.production.local

# Logs
npm-debug.log*
yarn-debug.log*
yarn-error.log*
lerna-debug.log*

# IDE
.vscode/
.idea/
*.swp
*.swo
*~
.project
.classpath
.c9/
*.launch
.settings/
*.sublime-workspace

# OS
Thumbs.db
.
├── src/                 # Source code
├── public/              # Static assets
├── vite.config.js       # Vite configuration
├── vitest.config.js     # Vitest configuration
└── package.json         # Project dependencies