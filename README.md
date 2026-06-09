# 🐍 Anthropic SDK: Custom Base URL & Prompt Caching Guide

If you are building AI applications using the official Anthropic SDK for Python or TypeScript, you can significantly lower your API costs by pointing the SDK to a cached Enterprise endpoint.

## 🛒 Prerequisites
You need an API key that routes through a prompt-caching pool. 
👉 **[Purchase Cached API Token & Base URL](https://claude.sell.app/product/claude-api-tokens)**

## 💻 Python Implementation

```python
from anthropic import Anthropic

# Initialize the client with your custom base URL
client = Anthropic(
    api_key="YOUR_PURCHASED_API_KEY",
    base_url="YOUR_CUSTOM_BASE_URL"
)

response = client.messages.create(
    model="claude-3-5-sonnet-20241022",
    max_tokens=1000,
    messages=[
        {"role": "user", "content": "Explain quantum computing in one paragraph."}
    ]
)

print(response.content)
💻 Node.js / TypeScript Implementation
TypeScript
import Anthropic from '@anthropic-ai/sdk';

// Initialize the client
const anthropic = new Anthropic({
  apiKey: 'YOUR_PURCHASED_API_KEY',
  baseURL: 'YOUR_CUSTOM_BASE_URL'
});

async function main() {
  const message = await anthropic.messages.create({
    max_tokens: 1024,
    messages: [{ role: 'user', content: 'Write a sorting algorithm.' }],
    model: 'claude-3-5-sonnet-20241022',
  });

  console.log(message.content);
}

main();
By initializing your client this way, all your backend applications will benefit from global access (no VPN required) and drastically reduced token costs due to the 80-95% cache hit rate.
