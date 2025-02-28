# ComfyUI Launcher (BETA)
Run any ComfyUI workflow w/ **ZERO setup**.

Need help? Join our Discord!

[![](https://dcbadge.vercel.app/api/server/kXS43yTRNA)](https://discord.gg/kXS43yTRNA)

## Features
- Automatically installs custom nodes, missing model files, etc.
- Workflows exported by this tool can be run by anyone with **ZERO setup**
- Work on multiple ComfyUI workflows at the same time
- Each workflow runs in its own isolated environment
- Prevents your workflows from suddenly breaking when updating custom nodes, ComfyUI, etc.

<p float="middle">
  <img src="./assets/launcher_projects.png" width="45%" />
  <img src="./assets/launcher_new_workflow.png" width="45%" />
  <img src="./assets/launcher_import_workflow.png" width="45%" />
  <img src="./assets/launcher_comfyui.png" width="45%" />
</p>

## Demo

Running a workflow json file w/ no setup

https://github.com/ComfyWorkflows/ComfyUI-Launcher/assets/33400216/aa17680d-eee5-4e6d-abc4-9f7551f9a4ad

## Requirements

#### Windows (Windows Subsystem for Linux - WSL) & Linux:
- Docker (w/ GPU support) or Python 3

#### macOS:
- Python 3

## Quick start

### Option 1: Docker (recommended)

Only works for **Linux** & **Windows (WSL)**. For **macOS**, use Option 2.

Note: If you use **Windows** and this method does **not** work for you, please try following the instructions in this [new-docker-setup](https://github.com/ComfyWorkflows/ComfyUI-Launcher/tree/new-docker-setup) branch we're testing. If you're still facing issues, please let us know in the *temp-windows-help* forum on our discord.

```
docker run \
--gpus all \
--rm \
--name comfyui_launcher \
--net=host \
-v $(pwd)/comfyui_launcher_models:/app/server/models \
-v $(pwd)/comfyui_launcher_projects:/app/server/projects \
-it thecooltechguy/comfyui_launcher
```

Open http://localhost:4000 in your browser

### Option 2: Manual setup
Works for **Windows (WSL)**, **Linux**, & **macOS**

#### Installation (one-time setup)
```
git clone https://github.com/ComfyWorkflows/comfyui-launcher
cd comfyui-launcher/
```

#### Start ComfyUI Launcher
```
./run.sh
```
Open http://localhost:4000 in your browser


## Updating
### Option 1: Docker
```
docker pull thecooltechguy/comfyui_launcher
```

### Option 2: Manual setup
```
git pull
```

## Coming soon
- Better handling of missing model files
- Native Windows support (w/o requiring WSL)
- Better way to manage your workflows locally
- Run workflows w/ Cloud GPUs
- Backup your projects to the cloud
- Run ComfyUI Launcher in the cloud

## Credits
- ComfyUI Manager (https://github.com/ltdrdata/ComfyUI-Manager/)
  - Used to auto-detect & install custom nodes
