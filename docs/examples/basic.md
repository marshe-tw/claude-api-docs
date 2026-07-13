# Basic Request

This example shows how to make your first request 
to the Claude API using Python.

## What you need

- An Anthropic API key
- Python installed on your computer
- The Anthropic Python library

## Install the library

Open your terminal and run:

```bash
pip install anthropic
```

## The code

```python
import anthropic

client = anthropic.Anthropic(api_key="YOUR_API_KEY")

message = client.messages.create(
    model="claude-sonnet-4-6",
    max_tokens=1024,
    messages=[
        {"role": "user", "content": "Hello, Claude!"}
    ]
)

print(message.content[0].text)
```

## What each line does

**`import anthropic`**  
Loads the Anthropic library so you can use it in your code.

**`client = anthropic.Anthropic(api_key="YOUR_API_KEY")`**  
Creates a connection to the Claude API using your API key.
Replace `YOUR_API_KEY` with your actual key from the Console.

**`client.messages.create(...)`**  
Sends the POST request to `/v1/messages` – this is where 
Claude receives your message and generates a response.

**`print(message.content[0].text)`**  
Prints Claude's response to your terminal.

## Expected output

```
Hello! How can I help you today?
```

## Important

Never write your API key directly in your code like this 
in a real project. Use environment variables instead:

```python
import os
import anthropic

client = anthropic.Anthropic(api_key=os.environ.get("ANTHROPIC_API_KEY"))
```

This keeps your key safe and out of your code.
