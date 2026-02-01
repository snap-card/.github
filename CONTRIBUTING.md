# Contributing to Snap Card

Thank you for your interest in contributing to Snap Card! This document provides guidelines and information for contributors.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Coding Standards](#coding-standards)
- [Commit Guidelines](#commit-guidelines)
- [Pull Request Process](#pull-request-process)
- [Issue Guidelines](#issue-guidelines)

## Code of Conduct

By participating in this project, you agree to maintain a respectful and inclusive environment. We expect all contributors to:

- Be respectful and considerate in all interactions
- Welcome newcomers and help them get started
- Accept constructive criticism gracefully
- Focus on what is best for the community and project

## Getting Started

### Prerequisites

Ensure you have the following installed:

- Node.js 20+
- npm 10+
- Git
- Docker & Docker Compose

### Setting Up Your Development Environment

1. **Fork the repository**

   Click the "Fork" button on GitHub to create your own copy.

2. **Clone your fork**
   ```bash
   git clone https://github.com/YOUR_USERNAME/snap-card.git
   cd snap-card
   ```

3. **Add upstream remote**
   ```bash
   git remote add upstream https://github.com/snap-card/snap-card.git
   ```

4. **Install dependencies**
   ```bash
   npm install
   ```

5. **Set up environment variables**
   ```bash
   cp .env.example .env
   # Edit .env with your local configuration
   ```

6. **Start development servers**
   ```bash
   npm run dev
   ```

## Development Workflow

### Branching Strategy

We use a simplified Git flow:

- `main` - Production-ready code
- `develop` - Integration branch for features
- `feature/*` - New features
- `bugfix/*` - Bug fixes
- `hotfix/*` - Production hotfixes

### Creating a Feature Branch

```bash
# Sync with upstream
git fetch upstream
git checkout develop
git merge upstream/develop

# Create your branch
git checkout -b feature/your-feature-name
```

### Running Tests

```bash
# Run all tests
npm test

# Run tests for a specific package
npm run test --workspace=packages/api

# Run tests in watch mode
npm run test:watch

# Run linting
npm run lint

# Run type checking
npm run type-check
```

## Coding Standards

### TypeScript

- Use TypeScript for all new code
- Enable strict mode
- Define explicit types for function parameters and return values
- Avoid `any` type; use `unknown` when type is truly unknown

### Code Style

- Use Prettier for formatting (auto-runs on commit)
- Follow ESLint rules defined in the project
- Maximum line length: 100 characters
- Use meaningful variable and function names

### File Organization

```
src/
├── modules/           # Feature modules
│   └── feature-name/
│       ├── dto/       # Data transfer objects
│       ├── entities/  # Database entities
│       ├── feature.controller.ts
│       ├── feature.service.ts
│       ├── feature.module.ts
│       └── feature.spec.ts
├── common/            # Shared utilities
└── config/            # Configuration
```

### Testing

- Write unit tests for all business logic
- Aim for 80%+ code coverage on new code
- Use descriptive test names that explain the expected behavior
- Follow the Arrange-Act-Assert pattern

```typescript
describe('FeatureService', () => {
  describe('methodName', () => {
    it('should return expected result when given valid input', () => {
      // Arrange
      const input = { ... };

      // Act
      const result = service.methodName(input);

      // Assert
      expect(result).toEqual(expectedOutput);
    });
  });
});
```

## Commit Guidelines

We follow [Conventional Commits](https://www.conventionalcommits.org/) specification.

### Commit Message Format

```
<type>(<scope>): <subject>

[optional body]

[optional footer]
```

### Types

- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, semicolons, etc.)
- `refactor`: Code refactoring
- `perf`: Performance improvements
- `test`: Adding or updating tests
- `chore`: Maintenance tasks
- `ci`: CI/CD changes

### Examples

```
feat(api): add user authentication endpoint

fix(web): resolve navigation state persistence issue

docs: update API documentation for v2 endpoints

refactor(bff): simplify session management logic
```

## Pull Request Process

1. **Update your branch**
   ```bash
   git fetch upstream
   git rebase upstream/develop
   ```

2. **Push your changes**
   ```bash
   git push origin feature/your-feature-name
   ```

3. **Create a Pull Request**
   - Use the PR template provided
   - Fill in all required sections
   - Link related issues

4. **Code Review**
   - Address reviewer feedback
   - Make requested changes
   - Re-request review when ready

5. **Merge**
   - PRs require at least one approval
   - All checks must pass
   - Squash and merge is preferred

### PR Checklist

- [ ] Code follows project style guidelines
- [ ] Self-review completed
- [ ] Tests added/updated
- [ ] Documentation updated
- [ ] No new warnings or errors
- [ ] Branch is up to date with target branch

## Issue Guidelines

### Reporting Bugs

When reporting bugs, please include:

1. **Environment details** (OS, browser, Node version)
2. **Steps to reproduce**
3. **Expected behavior**
4. **Actual behavior**
5. **Screenshots/logs** (if applicable)

### Suggesting Features

For feature requests, please describe:

1. **Use case** - What problem does this solve?
2. **Proposed solution** - How should it work?
3. **Alternatives considered** - Other approaches you've thought about

### Issue Labels

- `bug` - Something isn't working
- `enhancement` - New feature request
- `documentation` - Documentation improvements
- `good first issue` - Good for newcomers
- `help wanted` - Extra attention needed
- `priority: high` - Urgent issues
- `priority: low` - Nice to have

## Questions?

If you have questions, feel free to:

- Open a discussion on GitHub
- Reach out to the maintainers
- Check existing issues and documentation

---

Thank you for contributing to Snap Card!
