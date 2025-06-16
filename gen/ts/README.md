# ProducerFlow API Types

This package contains generated TypeScript types for the ProducerFlow API, created from Protocol Buffer definitions using `protoc-gen-es`.

## Installation

```bash
npm install @producerflow/producerflowapi
```

## Usage

```typescript
import { 
  EntityType, 
  ProducerOnboardingState,
  Producer, 
  Agency,
  NewAgencyRequest,
  // ... other types
} from '@producerflow/producerflowapi';

// Create a new agency request
const agencyRequest = new NewAgencyRequest({
  agency: {
    name: "Example Insurance Agency",
    entityType: EntityType.AGENCY,
    email: "contact@example.com",
    // ... other fields
  }
});

// Convert to binary for transmission
const binaryData = agencyRequest.toBinary();

// Convert to JSON
const jsonData = agencyRequest.toJson();
```

## Development

This package is automatically generated from Protocol Buffer definitions. Do not edit the generated files directly.

To build the package:

```bash
npm run build
```

To type-check:

```bash
npm run typecheck
```

## Dependencies

- `@bufbuild/protobuf`: Protocol Buffers runtime for TypeScript.