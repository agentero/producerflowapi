# Producerflow API

[![GoDoc](https://godoc.org/github.com/agentero/producerflowapi?status.svg)](https://godoc.org/github.com/agentero/producerflowapi)
[![Go Build Test](https://github.com/agentero/producerflowapi/actions/workflows/go-build.yml/badge.svg)](https://github.com/agentero/producerflowapi/actions/workflows/go-build.yml)
[![TypeScript Build Test](https://github.com/agentero/producerflowapi/actions/workflows/ts-build.yml/badge.svg)](https://github.com/agentero/producerflowapi/actions/workflows/ts-build.yml)
[![Proto Validation](https://github.com/agentero/producerflowapi/actions/workflows/proto-validation.yml/badge.svg)](https://github.com/agentero/producerflowapi/actions/workflows/proto-validation.yml)

> **⚠️ Under Construction**  
> This project is currently under active development. APIs and features may change without notice until the first stable release.

A comprehensive producer flow API service providing both gRPC and REST endpoints for managing producer workflows and data flows. Built with modern protocol buffer definitions and generating client libraries for multiple languages.

## Features

- **Dual API Support**: Both gRPC and REST endpoints for maximum flexibility
- **Type-Safe Clients**: Generated Go and TypeScript client libraries
- **Protocol Buffers**: Strongly-typed message definitions
- **CI/CD Ready**: Automated build and deployment workflows
- **Multi-Language Support**: Code generation for Go and TypeScript

## Project Structure

```
producerflowapi/
├── proto/              # Protocol buffer definitions
├── gen/                # Generated code
│   ├── go/            # Generated Go code
│   └── typescript/    # Generated TypeScript code
├── docs/              # Documentation
├── .github/           # GitHub workflows and templates
│   └── workflows/     # CI/CD workflows
```

## Documentation

- **[Changelog](CHANGELOG.md)** - Release history and version changes
- **[Security Policy](SECURITY.md)** - Security reporting and vulnerability disclosure
- **[Deprecation Policy](DEPRECATION.md)** - API deprecation guidelines and timelines

## Getting Started

This project is currently under development. More detailed setup and usage instructions will be provided as the project matures.

### Prerequisites

- Protocol Buffer compiler (protoc)
- Go 1.21+ (for Go client generation)
- Node.js 18+ (for TypeScript client generation)

### Development

Development setup and contribution guidelines will be documented as the project evolves.

## API Specification

The API is defined using Protocol Buffers and follows industry-standard practices for both gRPC and REST interfaces. Detailed API documentation will be available upon the first stable release.

## Versioning

This project follows [Semantic Versioning](https://semver.org/). See the [changelog](CHANGELOG.md) for release history.

## Security

For security concerns and vulnerability reporting, please see our [Security Policy](SECURITY.md).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

*For questions, issues, or contributions, please use the GitHub issue tracker or contact the development team.*
