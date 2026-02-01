# Snap Card

A modern, cloud-native platform built with scalability and performance in mind.

## Overview

Snap Card is a full-stack application ecosystem featuring web and mobile clients backed by a robust microservices architecture. The platform is designed with enterprise-grade security, high availability, and seamless user experiences across devices.

## Tech Stack

### Backend
- **Framework**: NestJS (TypeScript)
- **Databases**: PostgreSQL, DynamoDB, Redis
- **Authentication**: JWT, OAuth 2.0, Biometric

### Frontend
- **Web**: Next.js, React, TailwindCSS
- **iOS**: SwiftUI (MVVM)
- **Mobile**: Flutter (Dart)

### Infrastructure
- **Cloud**: AWS (EKS, RDS, CloudFront, S3)
- **IaC**: Terraform
- **CI/CD**: GitHub Actions
- **Monorepo**: Nx

## Architecture

```
┌─────────────────────────────────────────────────────────┐
│                     Client Layer                        │
│   ┌─────────┐    ┌─────────┐    ┌─────────────────┐    │
│   │   Web   │    │   iOS   │    │     Flutter     │    │
│   └────┬────┘    └────┬────┘    └────────┬────────┘    │
└────────┼──────────────┼──────────────────┼─────────────┘
         │              │                  │
         └──────────────┼──────────────────┘
                        ▼
┌─────────────────────────────────────────────────────────┐
│                   BFF Layer                             │
│   • Session Management  • Rate Limiting  • Caching      │
└────────────────────────┬────────────────────────────────┘
                         ▼
┌─────────────────────────────────────────────────────────┐
│                   API Layer                             │
│   • Business Logic  • Authentication  • Data Access     │
└────────────────────────┬────────────────────────────────┘
                         ▼
┌─────────────────────────────────────────────────────────┐
│                   Data Layer                            │
│   ┌──────────┐   ┌──────────┐   ┌──────────┐            │
│   │ Postgres │   │ DynamoDB │   │  Redis   │            │
│   └──────────┘   └──────────┘   └──────────┘            │
└─────────────────────────────────────────────────────────┘
```

## Getting Started

### Prerequisites
- Node.js 20+
- npm 10+
- Docker & Docker Compose
- AWS CLI (for infrastructure)

### Installation

```bash
# Clone the repository
git clone https://github.com/snap-card/snap-card.git
cd snap-card

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env

# Start development servers
npm run dev
```

## Project Structure

```
snap-card/
├── snapcard-app/              # Main application monorepo
│   ├── packages/
│   │   ├── api/               # Core backend services
│   │   ├── bff/               # Backend-for-frontend
│   │   ├── web/               # Web application
│   │   └── shared/            # Shared utilities
├── snapcard-ios-app/          # Native iOS application
├── snapcard-infrastructure/   # Terraform & CI/CD
└── .github/                   # GitHub configurations
```

## Contributing

We welcome contributions from the community. Please read our [Contributing Guide](CONTRIBUTING.md) before submitting any changes.

## Security

If you discover a security vulnerability, please email security@snapcard.dev instead of opening a public issue.

## License

This project is proprietary software. See the [LICENSE](LICENSE) file for details.

## Links

- [Organization](https://github.com/snap-card)
- [Documentation](https://docs.snapcard.dev)
- [Status Page](https://status.snapcard.dev)

---

Built with care by the Snap Card team.
