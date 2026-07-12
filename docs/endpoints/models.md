# Models

Anthropic offers different Claude models optimized for 
different use cases. Each model has its own strengths,
speed, and pricing.

## Available models

| Model | Best for | Context window |
|-------|----------|----------------|
| claude-opus-4-6 | Complex reasoning, long tasks | 200K tokens |
| claude-sonnet-4-6 | Balanced speed and intelligence | 200K tokens |
| claude-haiku-4-5 | Fast, lightweight tasks | 200K tokens |

## What is a context window?

The context window is the maximum amount of text Claude 
can read at once – including your messages and its own 
responses. Think of it like Claude's short-term memory.

200K tokens ≈ roughly 150,000 words ≈ an entire novel.

## Which model should I use?

- **Just starting out?** → Use `claude-sonnet-4-6`  
  Best balance of speed, quality, and cost.

- **Complex tasks or long documents?** → Use `claude-opus-4-6`  
  Most powerful, but slower and more expensive.

- **Speed is critical?** → Use `claude-haiku-4-5`  
  Fastest response time, ideal for simple tasks.

## How to specify a model

Include the model name in your request body:

```json
{
  "model": "claude-sonnet-4-6",
  "max_tokens": 1024,
  "messages": [...]
}
```
