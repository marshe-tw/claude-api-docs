# Streaming

By default, Claude generates the complete response before 
sending it back. With streaming, Claude sends the response 
word by word as it generates it — just like you see in Claude.ai.

## Why use streaming?

- Users see the response immediately instead of waiting
- Better experience for long responses
- Makes your app feel faster and more responsive

## The code

```python
import anthropic

client = anthropic.Anthropic(api_key="YOUR_API_KEY")

with client.messages.stream(
    model="claude-sonnet-4-6",
    max_tokens=1024,
    messages=[
        {"role": "user", "content": "Tell me a short story."}
    ]
) as stream:
    for text in stream.text_stream:
        print(text, end="", flush=True)
```

## What is different from a basic request?

| | Basic Request | Streaming |
|--|---------------|-----------|
| Method | `messages.create()` | `messages.stream()` |
| Response | All at once | Word by word |
| Best for | Short responses | Long responses |
| User experience | Wait then read | Read while generating |

## What each line does

**`with client.messages.stream(...) as stream:`**  
Opens a streaming connection to the Claude API.
The `with` block ensures the connection closes cleanly when done.

**`for text in stream.text_stream:`**  
Loops through each piece of text as Claude generates it.

**`print(text, end="", flush=True)`**  
Prints each piece immediately without a line break.
`flush=True` makes sure it appears instantly in the terminal.
