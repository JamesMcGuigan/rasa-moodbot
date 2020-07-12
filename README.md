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

## Tunnel Localhost Remotely
```
rasa run
ngrok http 5005
```

## Alexa Connectivity
- https://blog.rasa.com/connect-your-rasa-ai-assistant-to-amazon-alexa/
- https://github.com/RasaHQ/tutorial-rasa-alexa

```
wget https://raw.githubusercontent.com/RasaHQ/tutorial-rasa-alexa/master/alexa_schema.json
wget https://raw.githubusercontent.com/RasaHQ/tutorial-rasa-alexa/master/alexa_connector.py
echo "alexa_connector.AlexaConnector:" >> credentials.yml
```
