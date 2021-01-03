## DevContainer for Haskell with Haskell Language Server integration.
(haskell-hls-devcontainer)

A port of the [haskell-hie-devcontainer](https://github.com/hmemcpy/haskell-hie-devcontainer) by [hmemcpy](https://github.com/hmemcpy).

### What is this?

This is a [DevContainer](https://code.visualstudio.com/docs/remote/containers) environment for Visual Studio Code, which will automatically install the Glasgow Haskell Compiler (GHC), Haskell Language Server (HLS), and the necessary Visual Studio Code extensions to set up a Haskell development environment with zero additional effort.

### How to use this?

Follow the [Getting Started](https://code.visualstudio.com/docs/remote/containers#_getting-started) instructions to configure your Visual Studio Code and Docker to use with DevContainers.

Place the `.devcontainer` directory in the root of your project, and the next time you load the project, Visual Studio Code will prompt to re-open the project in a container:

![image](https://user-images.githubusercontent.com/601206/73298150-7bfac580-4215-11ea-81d3-a8fabab98e30.png)

**Note**: building the container might take a few minutes as it will need to download the necessary resources.

### How does it work?

Visual Studio Code supports [Developing inside a Container](https://code.visualstudio.com/docs/remote/containers) - using a Docker image as a development environment. It automates the process of creating the container image, as well as installing additional required extensions into the editor.

Pressing **Reopen in Container** will perform the automated steps to launch the container, and set up the environment.

For more information and setup, read the official documentation: https://code.visualstudio.com/docs/remote/containers

### What's in the box?

The `Dockerfile` contains the following:

1. The official [`Haskell`](https://hub.docker.com/_/haskell) image, based on a Debian Buster image that contains the [Nix package manager](https://nixos.org/nix/), as well as the following:
   * Configuration for [Cachix](https://cachix.org/) - a binary cache for Nix
   * Glasgow Haskell Compiler (GHC) version 8 (latest)
   * Haskell Language Server ([HLS](https://github.com/haskell/haskell-language-server)) for GHC 8 (latest)
2. A script to install some additional tools (such as git) and to configure a special user `vscode` to allow access from VSCode.

The `devcontainer.json` has some additional configuration for VSCode, in particular, the Haskell extension, and the name of the remote user (must match the one in the `Dockerfile`).
