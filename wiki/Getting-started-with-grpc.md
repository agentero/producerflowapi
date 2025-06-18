# Getting started with the gRPC API

This guide explains how to effectively use our gRPC API for your integration needs.

## Overview

Our gRPC API provides a high-performance, strongly-typed interface for interacting with our services. gRPC uses Protocol Buffers (protobuf) to define service contracts and message formats.

## Connect

Connect is a family of libraries for building browser and gRPC-compatible HTTP APIs. It uses Protocol Buffer schemas to handle marshaling, routing, compression, and content type negotiation, while also generating idiomatic, type-safe clients in supported languages.

### Production-grade simplicity

Connect is focused on essential features, built on top of time-tested HTTP libraries and designed to get out of your way. It's simple, reliable, and unobtrusive, because nobody has time to debug overcomplicated networking or sift through esoteric options. Under the hood, it's just Protocol Buffers and standard HTTP libraries.

### Seamless multi-protocol support

Connect servers and clients support three protocols:

- **gRPC**: Full support for the gRPC protocol including streaming, trailers, and error details
- **gRPC-Web**: Direct support for the gRPC-Web protocol without requiring a translating proxy
- **Connect's own protocol**: A straightforward HTTP-based protocol that works over HTTP/1.1, HTTP/2, and HTTP/3

By default, Connect servers support all three protocols. Clients default to using the Connect protocol but can switch to gRPC or gRPC-Web with a configuration toggle.

## Generated SDKs

The recommended way to access our API is through generated SDKs. When we push our schemas to the Buf Schema Registry (BSR), it automatically generates SDKs for multiple languages that package up code generated from the Protobuf files.

Using these SDKs provides several benefits:

- Natively integrate across backend, frontend, and mobile clients
- Consume SDKs without worrying about Protobuf environment, compiler, or plugins
- Take advantage of automatic organization-wide SDK caching
- View API reference documentation directly from the BSR

## Go SDK

For Go developers, we provide a generated SDK that makes it easy to integrate with our services.

## TypeScript SDK

For TypeScript and JavaScript developers, we offer a generated SDK for both browser and Node.js environments.

## Additional Language Support

If you need support for languages other than Go or TypeScript, please contact us for assistance.

Alternatively, you can generate SDKs for your preferred language using the Buf CLI. This allows you to create client libraries for various languages supported by Buf.
