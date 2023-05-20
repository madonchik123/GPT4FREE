Here is the documentation for the https://gpt4free.crispypiez.repl.co/ API

API Documentation:

This API allows you to generate text completions using GPT language models. It accepts the following query string parameters:

Required:

- prompt: The text you want the model to complete. Must be URL encoded.

- model: The GPT model to use. Options are:

- bard

- gpt-3.5-turbo

- gpt-4

Optional:

- messageid: An ID for the conversation (not being used yet).

- internetaccess: Enable/disable use of internet (for models that require it). Either 'true' or 'false'.

- context: Previous chat history to provide more context (up to 1024 characters).

Examples:

`https://gpt4free.crispypiez.repl.co/?prompt=Hello+%21&model=bard`

Generate a completion for the prompt "Hello !" using the bard model.

`https://gpt4free.crispypiez.repl.co/?prompt=What+is+the+weather+like+today%3F&model=gpt-3.5-turbo&internetaccess=true`

Generate a completion for the prompt "What is the weather like today?" using the gpt-3.5-turbo model with internet access enabled.

Examples:

Generate a completion for the prompt "Hello !" using the bard model in Rust.

Rust example:
```rust
use reqwest::blocking::Client;

use std::collections::HashMap;

fn main() {

 let url = "https://gpt4free.crispypiez.repl.co/";

 let mut params = HashMap::new();

 params.insert("prompt", "Hello !");

 params.insert("model", "bard");

 let client = Client::new();

 let res = client.get(url)

 .query(&params)

 .send()

 .unwrap()

 .text()

 .unwrap();

 println!("Response: {}", res);

}
```
```toml
[dependencies]
reqwest = { version = "0.11", features = ["blocking", "json"] }
openssl = { version = "0.10.40", features = ["vendored"] }
```

Generate a completion for the prompt "Hello !" using the bard model in Python.

Python example:

```python
import requests

api_url = "https://gpt4free.crispypiez.repl.co/"

params = {

 "prompt": "Hello !",

 "model": "bard"

}

response = requests.get(api_url, params=params)

print(response.text)
```

Generate a completion for the prompt "What is the weather like today?" using the gpt-3.5-turbo model with internet access enabled in NodeJS.


JavaScript example:

```javascript

const axios = require("axios");

const api_url = "https://gpt4free.crispypiez.repl.co/";

const params = {

 prompt: "What is the weather like today?",

 model: "gpt-3.5-turbo",

 internetaccess: "true"

};

axios.get(api_url, { params })

 .then(response => {

 console.log(response.data);

 });
 ```
