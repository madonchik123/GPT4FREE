**BetterGPT4Free API Documentation**
The BetterGPT4Free API allows you to interact with the BetterGPT4Free service to generate human-like text based on a given prompt. This API is simple to use and requires only three values to function correctly.

**API Endpoint**
https://bettergpt4free.crispypiez.repl.co/backend-api/v2/conversation

**Required Values:**

`model`: A string value representing the name of the model you want to use `GPT-3.5-Turbo/GPT-4`.

`prompt`: A string value representing the user input or prompt that the model should respond to.

`temperature`: A string value representing the temperature(creativity) for the bot.

`stream`: A bool value that represents if response should be streamed .

`systemmessage`: A string that represents how the chatgpt will act.


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
"model": "gpt-4",
"conversation": [],
"prompt": "Hello",
"systemmessage": "You are ChatGPT also known as ChatGPT, a large language model trained by OpenAI. Strictly follow the users instructions. Knowledge cutoff: 2021-09-01",
"stream": False,
"temperature": 0.7
}

response = requests.post(url, headers=headers, data=json.dumps(data))
response_data = json.loads(response.text)
print(response_data)
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
"model": "gpt-4",
"conversation": [],
"prompt": "Hello",
"systemmessage": "You are ChatGPT also known as ChatGPT, a large language model trained by OpenAI. Strictly follow the users instructions. Knowledge cutoff: 2021-09-01",
"stream": False,
"temperature": 0.7
});

    let response = client.post(url)
        .json(&data)
        .send()
        .await?
        .json::<Value>()
        .await?;

    let message_content = response;
    println!("{}", message_content);

    Ok(())
}
```

**Node.js Example**

Here is a Node.js example using the `axios` library to interact with the BetterGPT4Free API:

First, install the `axios` library:

`npm install axios`


Create a new JavaScript file and add the following code:
```javascript
const axios = require('axios');

const url = 'https://bettergpt4free.crispypiez.repl.co/backend-api/v2/conversation';

const data = {
"model": "gpt-4",
"conversation": [],
"prompt": "Hello",
"systemmessage": "You are ChatGPT also known as ChatGPT, a large language model trained by OpenAI. Strictly follow the users instructions. Knowledge cutoff: 2021-09-01",
"stream": False,
"temperature": 0.7
};

axios.post(url, data, { headers: { 'Content-Type': 'application/json' } })
  .then((response) => {
    const messageContent = response
    console.log(messageContent);
  })
  .catch((error) => {
    console.error(error);
  });
```

**ROBLOX LUA Example**
```lua
local http = game:GetService("HttpService")

local url = "https://bettergpt4free.crispypiez.repl.co/backend-api/v2/conversation"

local headers = {

    ["Content-Type"] = "application/json"

}

local data = {
"model": "gpt-4",
"conversation": [],
"prompt": "Hello",
"systemmessage": "You are ChatGPT also known as ChatGPT, a large language model trained by OpenAI. Strictly follow the users instructions. Knowledge cutoff: 2021-09-01",
"stream": False,
"temperature": 0.7
};

local response = http:PostAsync(url, http:JSONEncode(data), Enum.HttpContentType.ApplicationJson, false, headers)

local response_data = http:JSONDecode(response)

local message_content = response_data

print(message_content)


```
**THIS HAS NOTHING TO DO WITH OPENAI OR GPT4FREE I JUST MADE INSTRUCTIONS NOTHING ELSE**
