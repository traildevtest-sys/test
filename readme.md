
# OpenRouter API Tester

A lightweight developer tool for testing, benchmarking, and debugging LLM APIs through a unified interface. The project allows developers to send prompts to multiple AI models, compare responses, measure latency, and inspect request/response payloads in real time.

Designed for developers building AI applications who need a simple environment to experiment with prompts, evaluate model behavior, and debug API integrations.

---

## Overview

Modern AI development often involves interacting with multiple models from different providers. Each provider exposes slightly different APIs, authentication methods, and request formats. This project abstracts those differences and provides a unified testing environment.

The system allows developers to:

* Send prompts to multiple models through a single interface
* Compare model responses side-by-side
* Inspect raw API requests and responses
* Measure response time and token usage
* Debug prompt formatting and parameter settings

The tool is useful for:

* Prompt engineering
* Model comparison
* Latency benchmarking
* API debugging
* Integration testing

---

## Features

### Unified Model Interface

Send requests to different AI models using a consistent API format.

### Prompt Playground

Interactive environment for experimenting with prompts and system messages.

### Model Comparison

Execute the same prompt across multiple models and compare outputs.

### Request Inspection

View complete request payloads and API responses for debugging.

### Performance Metrics

Track:

* Response latency
* Token usage
* Completion length

### Parameter Control

Adjust model parameters in real time:

* temperature
* max_tokens
* top_p
* frequency_penalty
* presence_penalty

---

## Tech Stack

**Frontend**

* Next.js
* React
* TailwindCSS

**Backend**

* Node.js
* Express

**LLM Integration**

* OpenRouter API
* OpenAI-compatible endpoints

**Developer Tooling**

* TypeScript
* ESLint
* Prettier

---

## Architecture

```
client
│
├── components
│   ├── PromptEditor.tsx
│   ├── ModelSelector.tsx
│   ├── ResponsePanel.tsx
│   └── MetricsPanel.tsx
│
├── pages
│   └── index.tsx
│
server
│
├── routes
│   └── chat.ts
│
├── services
│   └── openrouter.ts
│
├── utils
│   └── formatter.ts
│
└── index.ts
```

The client handles the UI and prompt editing while the backend manages API communication and request normalization.

---

## Installation

Clone the repository.

```
git clone https://github.com/yourusername/openrouter-api-tester
```

Enter the project directory.

```
cd openrouter-api-tester
```

Install dependencies.

```
npm install
```

---

## Environment Variables

Create a `.env` file in the root directory.

```
OPENROUTER_API_KEY=your_api_key
PORT=3000
```

Optional parameters:

```
DEFAULT_MODEL=openai/gpt-4o
REQUEST_TIMEOUT=30000
```

---

## Running the Project

Start the development server.

```
npm run dev
```

Start the backend API server.

```
npm run server
```

Open the interface:

```
http://localhost:3000
```

---

## API Usage

Example request to the backend proxy.

```
POST /api/chat
```

Request body:

```
{
  "model": "openai/gpt-4o",
  "messages": [
    {
      "role": "user",
      "content": "Explain how transformers work."
    }
  ],
  "temperature": 0.7,
  "max_tokens": 500
}
```

Response structure:

```
{
  "id": "chatcmpl-123",
  "model": "openai/gpt-4o",
  "choices": [
    {
      "message": {
        "role": "assistant",
        "content": "Transformers are neural network architectures..."
      }
    }
  ],
  "usage": {
    "prompt_tokens": 23,
    "completion_tokens": 110,
    "total_tokens": 133
  }
}
```

---

## Example Use Cases

### Prompt Testing

Evaluate prompt structure before deploying to production.

### Model Benchmarking

Run the same prompt across multiple models and compare outputs.

### Latency Measurement

Track response time differences between models.

### Integration Debugging

Inspect raw request payloads to verify API formatting.

---

## Extending the Project

Possible extensions:

* Streaming response support
* Prompt history
* Saved prompt templates
* Multi-turn conversation testing
* Token cost estimation
* Model leaderboard

---

## Security Notes

* API keys should never be exposed in frontend code.
* Always route model requests through a backend proxy.
* Use environment variables for sensitive credentials.

---

## Contributing

Contributions are welcome. Typical contribution workflow:

1. Fork the repository
2. Create a feature branch
3. Commit changes
4. Submit a pull request

---

## License

MIT License

---

## Acknowledgements

* OpenRouter for unified LLM access
* OpenAI API design for standardized chat completions
* Open-source developer tooling ecosystem
