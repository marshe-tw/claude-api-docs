# Messages

The Messages endpoint is the core of the Claude API. 
It allows you to send messages to Claude and receive a response.

## Endpoint

```http
POST https://api.anthropic.com/v1/messages
```

## Required headers

```http
x-api-key: YOUR_API_KEY
anthropic-version: 2023-06-01
Content-Type: application/json
```

## Request body

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| model | string | ✅ | The Claude model to use |
| messages | array | ✅ | List of messages in the conversation |
| max_tokens | integer | ✅ | Maximum number of tokens in the response |

## Example request

```json
{
  "model": "claude-sonnet-4-6",
  "max_tokens": 1024,
  "messages": [
    {
      "role": "user",
      "content": "Hello, Claude!"
    }
  ]
}
```

## Example response

```json
{
  "id": "msg_abc123",
  "type": "message",
  "role": "assistant",
  "content": [
    {
      "type": "text",
      "text": "Hello! How can I help you today?"
    }
  ],
  "model": "claude-sonnet-4-6",
  "stop_reason": "end_turn"
}
```

## What is a token?

A token is a small piece of text – roughly 4 characters or 
three-quarters of a word. Claude counts both your input 
and its response in tokens. The `max_tokens` parameter 
controls how long Claude's response can be.
