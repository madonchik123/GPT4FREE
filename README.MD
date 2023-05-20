**BetterGPT4Free API Documentation**
The BetterGPT4Free API allows you to interact with the BetterGPT4Free service to generate human-like text based on a given prompt. This API is simple to use and requires only three values to function correctly.

**API Endpoint**
https://bettergpt4free.crispypiez.repl.co/backend-api/v2/conversation

**Required Values:**

`internet_access`: A boolean value representing whether the model should have access to the internet while generating responses.

`model`: A string value representing the name of the model you want to use.

`prompt`: A string value representing the user input or prompt that the model should respond to.

**Python Example**
Here is a Python example using the requests library to interact with the BetterGPT4Free API:

```python
import requests
import json

url = "https://bettergpt4free.crispypiez.repl.co/backend-api/v2/conversation"
headers = {
    "content-type": "application/json"
}

data = {
    "conversation_id": "",
    "action": "_ask",
    "model": "gpt-4",
    "jailbreak": "default",
    "meta": {
        "id": "",
        "content": {
            "conversation": [],  # Replace with your conversation history
            "internet_access": False,
            "content_type": "text",
            "parts": [
                {
                    "content": "Hello",
                    "role": "user"
                }
            ]
        }
    }
}

response = requests.post(url, headers=headers, data=json.dumps(data))
response_data = json.loads(response.text)
message_content = response_data['choices'][0]['message']['content']
print(message_content)
```
**Rust Example**

Here is a Rust example using the `reqwest` library to interact with the BetterGPT4Free API:

Add the following dependencies to your `Cargo.toml`
```toml
[dependencies]
reqwest = { version = "0.11", features = ["json"] }
tokio = { version = "1", features = ["full"] }
serde_json = "1.0"
```
Now, create a new Rust file and add the following code:
```rust
use reqwest::Client;
use serde_json::{json, Value};
use std::error::Error;

#[tokio::main]
async fn main() -> Result<(), Box<dyn Error>> {
    let url = "https://bettergpt4free.crispypiez.repl.co/backend-api/v2/conversation";
    let client = Client::new();

    let data = json!({
        "conversation_id": "",
        "action": "_ask",
        "model": "Your Model Here",
        "jailbreak": "default",
        "meta": {
            "id": "",
            "content": {
                "conversation": [],  // Replace with your conversation history
                "internet_access": false,
                "content_type": "text",
                "parts": [
                    {
                        "content": "Your Prompt Here",
                        "role": "user"
                    }
                ]
            }
        }
    });

    let response = client.post(url)
        .json(&data)
        .send()
        .await?
        .json::<Value>()
        .await?;

    let message_content = response["choices"][0]["message"]["content"].as_str().unwrap();
    println!("{}", message_content);

    Ok(())
}
```
