# playdate-devcontainer
Everything you need to build Playdate games in a single container!

## Push a new image
In vscode, run the `Dev Containers: Switch Containers` command and switch to the `Container for building other containers`. Then run:
```
devcontainer build --config .devcontainer/playdate/devcontainer.json --workspace-folder .devcontainer/playdate --push true --image-name zommerfelds/playdate-devcontainer:vNUM
```