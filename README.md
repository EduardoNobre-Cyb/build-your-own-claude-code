# Build Your Own Claude Code

[![progress-banner](https://backend.codecrafters.io/progress/claude-code/ea99b3e3-2556-4cd8-a4c9-0b944cf53e80)](https://app.codecrafters.io/users/codecrafters-bot?r=2qF)

A fully-featured AI coding assistant built from scratch as part of the [CodeCrafters](https://codecrafters.io) "Build Your Own Claude Code" challenge.

## 🚀 Project Overview

This repository contains a complete implementation of an LLM-powered coding assistant:

- **Python Version** ✅ Complete - Fully functional AI assistant with tool calling capabilities

The implementation features a modern, clean architecture with:
- OpenAI-compatible API integration via OpenRouter
- Function calling and tool execution framework
- Conversational agent loop with context preservation
- Extensible tool system for future enhancements

## Features

## ✨ Features

### Core Functionality

- **AI Integration** - Uses Anthropic's Claude models via OpenRouter API
- **Tool Calling** - Function calling capabilities with OpenAI-compatible interface
- **Agent Loop** - Conversational flow between user, AI, and tools with context preservation
- **CLI Interface** - Simple command-line interface for interactive queries
- **File Operations** - Built-in file reading capabilities for code analysis

### Advanced Features

- **Command-Line Arguments**
  - `-p` - Accept prompt/query as command-line argument
  - Environment variable configuration for API keys
- **Conversation Loop** - Multi-turn interactions with tool calling
- **Context Preservation** - Maintains conversation history across tool executions
- **Error Handling** - Comprehensive error handling for API failures and file operations
- **Extensible Architecture** - Framework designed for adding additional tools

## 📋 Requirements

### Python Version

- Python 3.14 or higher
- [uv](https://github.com/astral-sh/uv) package manager
- OpenRouter API key
- Standard library modules: `argparse`, `os`, `sys`, `json`
- External dependencies: `openai>=2.15.0`

## 🔧 Installation & Usage

### Prerequisites

**For Claude Code Assistant:**

- Python 3.14 or higher
- uv package manager
- OpenRouter API account and key

### Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd codecrafters-claude-code-python
```

2. Install dependencies:

```bash
uv sync
```

3. Set up environment variables:

```bash
export OPENROUTER_API_KEY="your-api-key-here"
export OPENROUTER_BASE_URL="https://openrouter.ai/api/v1"  # Optional
```

### Running the Claude Code Assistant

```bash
./your_program.sh -p "Your question or request here"
```

### Environment Variables

- `OPENROUTER_API_KEY`: Required - Your OpenRouter API key
- `OPENROUTER_BASE_URL`: Optional - Custom OpenRouter endpoint (defaults to https://openrouter.ai/api/v1)

## 💡 Usage Examples

### File Analysis

```bash
# Ask the AI to read and analyze a file
$ ./your_program.sh -p "Read the main.py file and explain what it does"

# Request specific information from documentation
$ ./your_program.sh -p "Use README.md to determine the chemical expiry period in months. Respond with only a number."
22

# Analyze project structure
$ ./your_program.sh -p "What files are in this project and what do they do?"
```

### Code Understanding

```bash
# Understand implementation details
$ ./your_program.sh -p "How does this project implement tool calling?"

# Debug and troubleshoot
$ ./your_program.sh -p "What might cause a 400 error in the API request?"

# Code review
$ ./your_program.sh -p "Review the main.py file for potential improvements"
```

### Interactive Queries

```bash
# General questions about the codebase
$ ./your_program.sh -p "Explain the conversation loop in this AI assistant"

# Configuration help
$ ./your_program.sh -p "What environment variables need to be set?"
```

## 🏗️ Architecture

### Python Implementation

The Python version features a clean, straightforward design:

```
codecrafters-claude-code-python/
├── app/
│   └── main.py              # Main application logic and entry point
├── codecrafters.yml         # CodeCrafters platform configuration
├── pyproject.toml          # Python project and dependency configuration
├── your_program.sh         # Shell script for execution
├── uv.lock                 # Dependency lock file
└── README.md               # This documentation
```

**Key Design Principles:**
- **Simplicity**: Clean, readable single-file implementation
- **Extensibility**: Tool framework designed for easy expansion
- **Modern Python**: Uses modern Python features and best practices
- **API Integration**: OpenAI-compatible interface via OpenRouter
- **Error Handling**: Robust error handling and validation

**Core Components:**
- **Argument Parsing**: Command-line interface using `argparse`
- **API Client**: OpenAI SDK configured for OpenRouter
- **Tool Framework**: Function calling with JSON schema definitions
- **Conversation Loop**: Multi-turn conversation with context preservation
- **File Operations**: Built-in file reading tool with error handling

**Tool System:**
```python
tools=[{
    "type": "function",
    "function": {
        "name": "Read",
        "description": "Read and return the contents of a file",
        "parameters": {
            "type": "object",
            "properties": {
                "file_path": {
                    "type": "string",
                    "description": "The path to the file to read",
                }
            },
            "required": ["file_path"],
        },
    },
}]
```

**Conversation Flow:**
1. Parse command-line arguments and validate API key
2. Initialize OpenAI client with OpenRouter configuration
3. Start conversation loop with user prompt
4. Handle tool calls and execute file operations
5. Return results to AI for processing
6. Output final response to user

## 🎯 Learning Outcomes

This project demonstrates proficiency in:

- **API Integration**: OpenAI-compatible API usage and configuration
- **Function Calling**: LLM tool calling and parameter passing
- **Agent Architecture**: Conversational AI loops and context management
- **Error Handling**: Robust error handling for API and file operations
- **Python Packaging**: Modern Python project structure with uv
- **CLI Development**: Command-line interface design and argument parsing
- **JSON Processing**: Schema definition and data serialization
- **Environment Configuration**: API key management and environment variables
- **Tool Development**: Extensible function calling framework
- **Code Organization**: Clean, maintainable code structure

## 📚 Documentation

### Available Tools

#### Read Tool
- **Purpose**: Read and return contents of specified files
- **Parameters**: `file_path` (string) - Path to the file to read
- **Usage**: Claude can request to read files to answer questions about code or documentation
- **Error Handling**: Handles file not found, permission errors, and encoding issues

### CodeCrafters Integration

```bash
# Submit your solution
codecrafters submit

# Run CodeCrafters tests
codecrafters test
```

## 🙏 Acknowledgments

This project is part of the [CodeCrafters](https://codecrafters.io) "Build Your Own Claude Code" challenge, which provides a structured learning path for building AI-powered applications and understanding LLM integration patterns.

## 📝 License

This project is part of the CodeCrafters educational platform. Please refer to CodeCrafters terms for usage guidelines.

---

**Status**: Python implementation complete ✅  
**Note**: If you're viewing this repo on GitHub, head over to [codecrafters.io](https://codecrafters.io) to try the challenge yourself!
