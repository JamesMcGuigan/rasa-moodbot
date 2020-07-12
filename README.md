# rasa-moodbot
Rasa Moodbot documenting Alexa/Google Connectivity

## Run Locally
```
rasa train
rasa visualize
rasa test
```
```
rasa shell
rasa shell nlu
rasa interactive
```

## Alexa Connectivity
- https://blog.rasa.com/connect-your-rasa-ai-assistant-to-amazon-alexa/
- https://github.com/RasaHQ/tutorial-rasa-alexa

### Config
```
wget https://raw.githubusercontent.com/RasaHQ/tutorial-rasa-alexa/master/alexa_schema.json
wget https://raw.githubusercontent.com/RasaHQ/tutorial-rasa-alexa/master/alexa_connector.py
echo "alexa_connector.AlexaConnector:" >> credentials.yml
echo 'action_endpoint:\n  url: "http://localhost:5055/webhook"' >> endpoints.yml
```

### Run Locally
## Tunnel Localhost Remotely
```
rasa run
ngrok http 5005
curl http://localhost:5005/webhooks/alexa_assistant/
curl -X POST http://localhost:5005/webhooks/alexa_assistant/webhook
```

### Alexa Console
- https://developer.amazon.com/alexa/console/ask
- Create Skill -> Custom -> Provision your own
    - Invocation -> Skill Invocation Name -> "mood bot"
    - Intents -> JSON Editor -> Upload alexa_schema.json
        - Save -> Build
    - Endpoint -> HTTPS 
        - https://e7183a3554d3.ngrok.io/webhooks/alexa_assistant/webhook
        - SSL Subdomain
        - Save Endpoints
    - Test
        - mood bot
        - hello
        - I am happy
        - I am sad
        - goodbye

