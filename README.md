# Kubernetes Controller

[![CI Status](https://github.com/solaris24251/k8s-controller/workflows/CI/badge.svg)](https://github.com/solaris24251/k8s-controller/actions)
[![Release](https://img.shields.io/github/v/release/solaris24251/k8s-controller)](https://github.com/solaris24251/k8s-controller/releases)
[![Docker](https://img.shields.io/badge/docker-ghcr.io%2Fsolaris24251%2Fk8s--controller-blue)](https://ghcr.io/solaris24251/k8s-controller)
[![Go Version](https://img.shields.io/badge/go-1.24-blue.svg)](https://golang.org/dl/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

A Kubernetes resource management tool built with [Cobra CLI](https://github.com/spf13/cobra) and [client-go](https://github.com/kubernetes/client-go), providing comprehensive Kubernetes resource management capabilities.

## Features

- **Kubernetes deployment listing** with kubeconfig authentication
- **Multiple authentication methods** (kubeconfig file, custom path, in-cluster)
- **Clean CLI interface** with intuitive commands
- **Docker support** with distroless images for security
- **Comprehensive build system** with Makefile
- **Kubernetes client-go integration** for cluster operations
- **CI/CD pipeline** with automated testing

## Installation

### Local Development

```bash
# Clone the repository
git clone <repository-url>
cd go-k8s-controller

# Download dependencies
make deps

# Build the application
make build-local
```
### Using Make

```bash
# Build for production (Linux)
make build

# Build and show help
make run

# Build and run list deployments
make run-list-deployments

# Run all checks (format, test)
make check

# Show all available targets
make help
```

### Using Docker

```bash
# Build Docker image
make docker-build

# Push to registry
make docker-push
```

## Usage

### Basic Commands

```bash
# Show help
./bin/k8s-controller --help

# Show list command help
./bin/k8s-controller list --help
```

### Kubernetes Operations

#### Listing Deployments

```bash
# List deployments in default namespace (uses default kubeconfig)
k8s-controller list

# List deployments in specific namespace
k8s-controller list --namespace argocd

# List deployments with custom kubeconfig
k8s-controller list --kubeconfig /path/to/kubeconfig
```

# Project Structure

- `cmd/` — Contains your CLI commands.
- `main.go` — Entry point for your application.
- `server.go` - fasthttp server
- `Makefile` — Build automation tasks.
- `Dockerfile` — Distroless Dockerfile for secure containerization.
- `.github/workflows/` — GitHub Actions workflows for CI/CD.
- `charts/app` - helm chart

# License

MIT License. See [LICENSE](LICENSE) for details.
