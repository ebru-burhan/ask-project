# CE350 - Ask CLI Tool

A simple and lightweight command-line interface (CLI) tool written in Bash that interacts with Large Language Model (LLM) APIs. 

## Features
* Sends prompts to an LLM via API and returns the plain text response.
* Supports both direct arguments (`./ask "prompt"`) and piped inputs (`echo "text" | ./ask "prompt"`).
* Uses `curl` for API requests and `jq` for secure JSON parsing.

## Prerequisites
Before running the script, ensure you have the following installed:
* Git Bash (or any Unix-like terminal)
* `curl`
* `jq`

## Setup & Usage
You must export your API credentials and model preferences as environment variables before using the tool:

```bash
export ASK_API_URL="https://api.groq.com/openai/v1/chat/completions"
export ASK_MODEL="llama-3.3-70b-versatile"
export ASK_API_KEY="your_api_key_here"
```

**1. Standard Argument**
```bash
$ ./ask "What is the capital of Turkey?"
Ankara
```

**2. Piped Input**
```bash
$ echo "Hello, how are you?" | ./ask "Translate this to German"
Hallo, wie geht es dir?
```

**3. Combined Input (Pipe + Argument)**
```bash
$ echo "1923" | ./ask "What happened in Turkey in this year?"
Turkey was declared a republic on October 29, 1923, with Mustafa Kemal Atatürk as its first president.
