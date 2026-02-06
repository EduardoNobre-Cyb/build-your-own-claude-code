# Claude Code Assistant

[![progress-banner](https://backend.codecrafters.io/progress/claude-code/ea99b3e3-2556-4cd8-a4c9-0b944cf53e80)](https://app.codecrafters.io/users/codecrafters-bot?r=2qF)

A Python implementation of an AI coding assistant built as part of the [CodeCrafters "Build Your own Claude Code" Challenge](https://codecrafters.io/challenges/claude-code). This project creates an LLM-powered agent that can read files and respond to queries using Claude models via OpenRouter API.

## Overview

This AI assistant demonstrates core concepts of building LLM-powered tools:
- **Tool Calling**: Integration with function calling capabilities
- **Agent Loops**: Conversational flow between user, AI, and tools
- **File Operations**: Reading and processing files based on user requests
- **API Integration**: Using OpenRouter API with OpenAI-compatible interface

## Features

- 🤖 **Claude Integration**: Uses Anthropic's Claude models via OpenRouter
- 📁 **File Reading**: Can read and analyze file contents on request
- 🔄 **Conversation Loop**: Maintains context across multiple tool calls
- ⚡ **Simple CLI**: Easy command-line interface for queries
- 🛠️ **Extensible**: Built with a framework for adding more tools

## Prerequisites

- Python 3.14+
- [uv](https://github.com/astral-sh/uv) package manager
- OpenRouter API key

## Setup

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd codecrafters-claude-code-python
   ```

2. **Install dependencies**:
   ```bash
   uv sync
   ```

3. **Set up environment variables**:
   ```bash
   export OPENROUTER_API_KEY="your-api-key-here"
   export OPENROUTER_BASE_URL="https://openrouter.ai/api/v1"  # Optional
   ```

## Usage

Run the assistant with a prompt:

```bash
./your_program.sh -p "Your question or request here"
```

### Examples

```bash
# Ask the AI to read and analyze a file
./your_program.sh -p "Read the main.py file and explain what it does"

# Request specific information from a file
./your_program.sh -p "Use README.md to determine the chemical expiry period in months. Respond with only a number."

# General coding questions
./your_program.sh -p "How does this project implement tool calling?"
```

## Project Structure

```
codecrafters-claude-code-python/
├── app/
│   └── main.py           # Main application logic
├── codecrafters.yml      # CodeCrafters configuration
├── pyproject.toml        # Python project configuration
├── your_program.sh       # Execution script
└── README.md            # This file
```

## How It Works

1. **Command Line Input**: The program accepts a prompt via the `-p` argument
2. **API Connection**: Connects to OpenRouter API using Claude Haiku model
3. **Tool Registration**: Registers a "Read" function for file operations
4. **Conversation Loop**: 
   - Sends user prompt to Claude
   - If Claude requests to read a file, executes the tool
   - Returns file contents to Claude
   - Claude processes and responds
   - Continues until Claude provides a final answer
5. **Output**: Prints Claude's final response

## Available Tools

### Read Tool
- **Purpose**: Read and return contents of specified files
- **Parameters**: `file_path` (string) - Path to the file to read
- **Usage**: Claude can request to read files to answer questions about code or documentation

## Development

### Running Locally
```bash
./your_program.sh -p "Your test prompt"
```

### CodeCrafters Integration
```bash
# Submit your solution
codecrafters submit

# Run CodeCrafters tests
codecrafters test
```

### Environment Variables
- `OPENROUTER_API_KEY`: Required - Your OpenRouter API key
- `OPENROUTER_BASE_URL`: Optional - Custom OpenRouter endpoint (defaults to https://openrouter.ai/api/v1)

## Technical Details

- **Language**: Python 3.14
- **AI Model**: anthropic/claude-haiku-4.5
- **API Client**: OpenAI Python SDK (OpenRouter compatible)
- **Package Manager**: uv
- **Tool Framework**: OpenAI function calling protocol

## Error Handling

The application includes error handling for:
- Missing API keys
- API request failures
- File reading errors
- Invalid command line arguments

## Contributing

This is a CodeCrafters challenge implementation. Feel free to:
- Add more tools (write files, run commands, etc.)
- Implement different AI models
- Enhance error handling
- Improve the conversation interface

## License

This project is part of the CodeCrafters educational platform. Please refer to CodeCrafters terms for usage guidelines.

---

**Note**: If you're viewing this repo on GitHub, head over to [codecrafters.io](https://codecrafters.io) to try the challenge yourself!
