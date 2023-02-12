# mariana-trench-models
This repository stores and houses various models for Mariana trench provided by me, as well as contributed by the community. Hope that you also contribute by sending models via pull requests or Github issues to grow the list.


Bash command to create the `custom_generator_config.json` file:

```bash
echo "[$(for word in $(find custom-model-generator \( -name "*.json" -and -type f \) -and \( -not -name "TODO_*" \) -and \( -not -name "*_config*json" \) -exec basename {} + | cut -f 1 -d '.'); do echo "  {\"$word\"},"; done; )" | sed '$s/.$/]/' > custom_generator_config.json
 ```