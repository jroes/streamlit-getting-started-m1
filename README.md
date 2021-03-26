# streamlit-getting-started-m1

This is an instantly-working M1-native Streamlit development environment using VSCode, Docker, and Conda.

## Background

Getting a working development environment on OSX is challenging these days with the new Apple M1 chip. This makes it super easy to get a working development environment.

## Requirements

* [Docker for Apple Silicon](https://docs.docker.com/docker-for-mac/apple-m1/)
* [Visual Studio Code](https://code.visualstudio.com/download)

Note: If you use the Apple Silicon build for VS Code, you'll get a much faster experience, but technically this will still work in the Intel-based VSCode.

## How to use

1. Clone this repo (`git clone https://github.com/jroes/streamlit-m1-vscode`)
2. Open in VSCode (`code .`)
3. Click "Re-launch in container"

Clicking "re-launch in container" will build the underlying Docker container. From there you should be able to do things like:

* Open a new Terminal window in VSCode and run `streamlit hello`
* Run any other streamlit commands, such as `streamlit run streamlit_app.py`
* VSCode will automatically ask you to open/re-route ports so you can access the app, and give you a link to visit your app in a browser.

## How this works

This repository contains:

* A Dockerfile that sets up a working Python 3.8 + conda + Linux environment for ARM-based CPUs (e.g. the new Apple M1 chip)
* A devcontainer.json that will automatically configure VSCode to build & use this container.
* A fairly-empty streamlit_app.py you can `streamlit run` as a starting point.

## Acknowledgements

Much of this work would not be possible without the [work that the VSCode team has done](https://github.com/microsoft/vscode-dev-containers/) in building images for standard platforms.

There's also some great work that exists from the [conda-forge team](https://github.com/conda-forge/miniforge) that includes aarch64-compatible builds of various dependencies.