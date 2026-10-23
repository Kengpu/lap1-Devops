# CI/CD Pipeline with GitHub Actions

Modern JavaScript ES Modules project using Node.js 24, Yarn 4, Express 5, Mocha, Chai, Supertest, ESLint, and c8 code coverage.

## Project Structure

```text
ci-cd-lab/
├── .github/
│   └── workflows/
│       └── ci.yml
├── test/
│   └── test.js
├── .gitignore
├── .yarnrc.yml
├── app.js
├── eslint.config.js
├── package.json
├── README.md
└── server.js
```

## Getting Started

### Prerequisites
- Node.js >= 24
- Corepack / Yarn 4 (`yarn@4.18.1`)
- Git

### Installation
Install project dependencies with Yarn:
```bash
yarn install
```

### Running Locally
Start the Express server on port 3000 (or `PORT` environment variable):
```bash
yarn start
```
Access the application at `http://localhost:3000/`.

### Linting
Run ESLint to check code quality:
```bash
yarn lint
```

### Running Tests
Execute unit and integration tests using Mocha, Chai, and Supertest:
```bash
yarn test
```

### Code Coverage
Generate test coverage metrics using c8:
```bash
yarn coverage
```
The coverage report is generated locally in the `coverage/` directory (`coverage/index.html`).

## CI/CD Pipeline
Continuous Integration is configured via GitHub Actions in `.github/workflows/ci.yml`. On every push and pull request to `main`, the workflow executes:
1. Environment setup (Node.js 24, Yarn cache)
2. Immutable dependency installation (`yarn install --immutable`)
3. Linting (`yarn lint`)
4. Test suite (`yarn test`)
5. Code coverage generation (`yarn coverage`)
6. Upload of the HTML coverage report as an artifact (`code-coverage-report`)
