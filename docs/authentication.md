# Authentication

The Claude API uses API keys to authenticate requests. 
You can manage your API keys in the Anthropic Console.

## Getting your API key

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign in or create an account
3. Navigate to **API Keys**
4. Click **Create Key**
5. Copy your key and store it safely

!!! warning
    Never share your API key publicly or commit it to GitHub.
    Treat it like a password.

## Using your API key

Include your API key in every request as a header:

```http
x-api-key: YOUR_API_KEY
anthropic-version: 2023-06-01
Content-Type: application/json
```

## What is a Header?

A header is extra information you send alongside your API request.
Think of it like an envelope – the header is written on the outside
and tells the server who you are before it opens the message.
