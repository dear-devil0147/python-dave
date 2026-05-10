---
name: Feature request
about: Suggest an idea for this project
title: '[FEATURE] '
labels: 'enhancement'
assignees: '' 

--- 

## Is your feature request related to a problem?
A clear and concise description of what the problem is. Ex. I'm always frustrated when [...] 

## Describe the solution you'd like
A clear and concise description of what you want to happen. 

## Describe alternatives you've considered
A clear and concise description of any alternative solutions or features you've considered. 

## Additional Context
Add any other context or screenshots about the feature request here.
---
name: Bug report
about: Create a report to help us improve
title: '[BUG] '
labels: 'bug'
assignees: '' 

--- 

## Description
A clear and concise description of what the bug is. 

## Steps to Reproduce
1. Go to '...'
2. Click on '...'
3. Scroll down to '...'
4. See error 

## Expected Behavior
A clear and concise description of what you expected to happen. 

## Actual Behavior
What actually happened instead. 

## Screenshots
If applicable, add screenshots to help explain your problem. 

## Environment
- OS: [e.g. macOS, Windows, Linux]
- Node version: [e.g. 18.0.0]
- npm version: [e.g. 9.0.0]
- Browser: [e.g. Chrome, Safari] 

## Additional Context
Add any other context about the problem here.
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
.
├── src/                 # Source code
├── public/              # Static assets
├── vite.config.js       # Vite configuration
├── vitest.config.js     # Vitest configuration
└── package.json         # Project dependenciesnpm run previewnpm run buildnpm testnpm start# Dependencies
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
npm install# Contributing to Effective Space Bassoon 

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
{
  "semi": true,
  "trailingComma": "es5",
  "singleQuote": true,
  "printWidth": 80,
  "tabWidth": 2,
  "useTabs": false,
  "arrowParens": "always"
}
{
  "env": {
    "browser": true,
    "es2021": true,
    "node": true
  },
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:react-hooks/recommended"
  ],
  "parserOptions": {
    "ecmaVersion": "latest",
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "plugins": ["react", "react-hooks"],
  "rules": {
    "react/react-in-jsx-scope": "off",
    "react/prop-types": "warn",
    "no-unused-vars": "warn"
  },
  "settings": {
    "react": {
      "version": "detect"
    }
  }
}
{
  "mcpServers": {
    "haven": {
      "type": "http",
      "url": "http://127.0.0.1:8730/mcp"
    }
  }
}import requests 

# Proxy configuration
proxies = {
    "http": "http://185.178.45.222:8080",
    "https": "http://185.178.45.222:8080",
} 

# Target URL
url = "https://facebook.com" 

# Make a request through the proxy
try:
    response = requests.get(url, proxies=proxies, timeout=10)
    print("Status Code:", response.status_code)
    print("Response Body (first 100 chars):")
    print(response.text[:100])
except requests.exceptions.RequestException as e:
    print("Error:", e)http://127.0.0.1:8730/mcp
