# Playdate + Dev Container = ❤️
Everything you need to build Playdate games in a single container!

[![demo video](https://github.com/user-attachments/assets/c78e424f-1782-475c-a610-c80b1546ebab)](https://youtu.be/4UoWD2lkBuU "demo video")

## Instructions

Click on the video above to see a demo.

## Work

- [x] Basic example in C using containers
- [x] Demo video
- [ ] Create a Lua example
- [ ] Support sounds

## Maintainance

### Push a new image
In vscode, run the `Dev Containers: Switch Containers` command and switch to the `Container for building other containers`. Then run:
```
devcontainer build --config .devcontainer/playdate/devcontainer.json --workspace-folder .devcontainer/playdate --push true --image-name zommerfelds/playdate-devcontainer:vNUM
```
