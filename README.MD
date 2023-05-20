**BetterGPT4Free API Documentation**
The BetterGPT4Free API allows you to interact with the BetterGPT4Free service to generate human-like text based on a given prompt. This API is simple to use and requires only three values to function correctly.

API Endpoint
https://bettergpt4free.crispypiez.repl.co/backend-api/v2/conversationCopyCopy

`Required Values`
internet_access: A boolean value representing whether the model should have access to the internet while generating responses. Set this value using request.json['meta']['content']['internet_access'].CopyCopyCopy
model: A string value representing the name of the model you want to use. Set this value using request.json['model'].CopyCopyCopy
prompt: A string value representing the user input or prompt that the model should respond to. Set this value using request.json['meta']['content']['parts'][0].CopyCopyCopy
Python Example
Here is a Python example using the requests library to interact with the BetterGPT4Free API:Copy

import requests
import json

url = "https://bettergpt4free.crispypiez.repl.co/backend-api/v2/conversation"
headers = {
    "content-type": "application/json"
}

data = {
    "conversation_id": "",
    "action": "_ask",
    "model": "Your Model Here",
    "jailbreak": "default",
    "meta": {
        "id": "",
        "content": {
            "conversation": [],  # Replace with your conversation history
            "internet_access": False,
            "content_type": "text",
            "parts": [
                {
                    "content": "Your Prompt Here",
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
