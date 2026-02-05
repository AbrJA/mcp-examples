# MCP Examples with Julia

This project demonstrates a simple Model Context Protocol (MCP) server implemented in Julia, featuring `echo` and `greet` tools accessible via HTTP.

## Getting Started

### Prerequisites

- Julia (version 1.7 or later recommended)
- ModelContextProtocol.jl package

To install the ModelContextProtocol package, open the Julia REPL and run:
```julia
using Pkg
Pkg.add("ModelContextProtocol")
```

### Running the Server

1. Navigate to the project directory:
   ```bash
   cd /path/to/your/project
   ```

2. Run the Julia script:
   ```bash
   julia example.jl
   ```

   This will start an HTTP server on `http://localhost:3000`.

## Tools

The server exposes two tools:

### 1. `echo` Tool

Echoes back the provided message.

- **Description:** Echo back the provided message
- **Parameters:**
  - `message` (string, required): The message to echo.

**Example Usage (using `curl`):**
```bash
curl -X POST http://localhost:3000/v1/tools/echo -H "Content-Type: application/json" -d '{"message": "Hello from MCP!"}'
```

### 2. `greet` Tool

Generates a greeting message.

- **Description:** Generate a greeting message
- **Parameters:**
  - `name` (string, required): The name to greet.
  - `language` (string, optional, default: "english"): The language for the greeting (e.g., "spanish", "french", "english").

**Example Usage (using `curl`):**

- **English Greeting:**
```bash
curl -X POST http://localhost:3000/v1/tools/greet -H "Content-Type: application/json" -d '{"name": "Alice"}'
```

- **Spanish Greeting:**
```bash
curl -X POST http://localhost:3000/v1/tools/greet -H "Content-Type: application/json" -d '{"name": "Bob", "language": "spanish"}'
```

- **French Greeting:**
```bash
curl -X POST http://localhost:3000/v1/tools/greet -H "Content-Type: application/json" -d '{"name": "Charlie", "language": "french"}'
```