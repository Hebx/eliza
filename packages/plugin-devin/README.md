# @elizaos/plugin-devin

Devin API integration plugin for Eliza, providing automated engineering assistance through the Devin API.

## Installation

```bash
pnpm add @elizaos/plugin-devin
```

## Configuration

The plugin requires a Devin API token for authentication. Set the following environment variable:

```bash
DEVIN_API_TOKEN=your_api_token_here
```

Or configure it in your Eliza runtime settings:

```typescript
runtime.setSetting("DEVIN_API_TOKEN", "your_api_token_here");
```

## Features

- Session Management: Create and manage Devin engineering sessions
- State Tracking: Monitor session status and progress
- Client Agnostic: Works with any Eliza client implementation
- Rate Limiting: Built-in API request rate limiting
- Error Handling: Comprehensive error handling with retries

## Usage

### Actions

#### START_DEVIN_SESSION

Creates a new Devin session with the specified prompt.

```typescript
const result = await runtime.runAction("START_DEVIN_SESSION", {
    content: { text: "Help me refactor this code" }
});
```

### Providers

#### devinProvider

Manages Devin session state and provides session information.

```typescript
const state = await runtime.getState();
const devinState = state.devin;

// Access session details
console.log(devinState.sessionId);
console.log(devinState.status);
console.log(devinState.url);
```

## Testing

Run the test suite:

```bash
pnpm test
```

## API Documentation

For detailed API documentation, visit:
- [Devin API Integration Guide](https://docs.devin.ai/tutorials/api-integration)
- [External API Reference](https://docs.devin.ai/external-api/)

## License

MIT