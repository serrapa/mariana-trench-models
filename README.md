# mariana-trench-models
This repository stores and houses various models for Mariana trench provided by me, as well as contributed by the community. Hope that you also contribute by sending models via pull requests or Github issues to grow the list.


Bash command to create the `custom_generator_config.json` file:

```bash
echo "[\n$(for word in $(find custom-model-generator \( -name "*.json" -and -type f \) -and \( -not -name "TODO_*" \) -and \( -not -name "*_config*json" \) -exec basename {} + | cut -f 1 -d '.'); do echo "  {\"name\":\"$word\"},"; done; )" | sed '$s/.$/\n]/' > custom-model-generator/custom_generator_config.json
 ```

Bash command to create a list of all existing kinds of sources:
```bash
find sources \( -name "*.json" -and -type f \) -and \( -not -name "TODO_*" \) -and \( -not -name "*_config*json" \) -exec cat {} + | grep -oE '"kind":\s*"[^"]*"' | sed 's/.*"\(.*\)".*/\1/' | uniq | sort
```

Bash command to create a list of all existing kinds of sinks:
```bash
find sinks \( -name "*.json" -and -type f \) -and \( -not -name "TODO_*" \) -and \( -not -name "*_config*json" \) -exec cat {} + | grep -oE '"kind":\s*"[^"]*"' | sed 's/.*"\(.*\)".*/\1/' | uniq | sort
```

| Kind Source | Kind Sink |
|----------------|--------------|
| ActivityUserInput | CodeExecution |
| DeeplinkInput | FileResolver |
| IntentCreation | HttpTraffic |
| IntentData | InputStream |
| ReceiverUserInput | LaunchingComponent |
| SensitiveCookieData | PendingIntent |
| StorageInput | Reflection |
| |SQLMutation |
| |SQLQuery |
| |WebViewLoadContent |