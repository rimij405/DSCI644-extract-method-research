---
course: "DSCI 644"
group: "Group 7"
project: "Extract Method Refactor Research"
---

## Overview

In partial fulfillment of the course requirements for DSCI 644: Software Engineering for Data Science, our group has been tasked to accomplish a semester-length research study involving the accurate assessment and detection of duplicate code in need of refactoring.

Our work consists of identifying a specific problem under this broad field of duplicate code detection and engineering a solution (with accurate citations when referencing existing bodies of work).

## Project Structure

This repository is organized as follows:

```bash
./ # File tree from the project's root folder.
│
│   # Contains development environment configuration settings.
├── .devcontainer/ 
│   ├── devcontainer.json
│   └── Dockerfile
│
│   # Contains documentation files related to the written deliverables.
├── docs/
│   └── template.tex
│
│   # Expected location for raw and processed data artifacts.
├── data/
│   ├── raw/
│   └── processed/
│
│   # Contains code related to the project.
├── src/
│
│   # Contains automation scripts that are not part of the solution code.
├── scripts/
│   ├── *.py
│   └── *.sh
│
│   # Project-wide configuration and metadata files.
├── .gitignore
├── .env
├── LICENSE
├── CONTRIBUTING.md
└── README.md
```

## Getting Started

With the goals of *reproducible* research in mind, we have documented our procedure for setting up and preparing a local development environment for people to 


### Setting up your local development environment with...

> :exclamation: **Action**: Take this opportunity to update the [README.md](#) with your own method of setting up your local environment below.




### Setting up your local $\LaTeX$ environment.

This project has `.tex` file documents that you may want to render. This section discusses setting up a dockerized.



> :memo: **Note**: You may find great benefit in following one of the [alternative methods listed here](https://towardsdatascience.com/three-ways-to-create-dockernized-latex-environment-2534163ee0c4#3fca).

### Setting up your local environment with `.devcontainer/`

The `.devcontainer/` directory contains a `devcontainer.json` configuration file and a special `Dockerfile` (based on a `Java` 17 image) that was automatically generated by VS Code.

> :memo: **Note**: [If you are not familiar with `development containers` you can read more about them here][.devcontainer].

The main advantage of the `.devcontainer` format over pure container images is the integration support VS Code has for a majority of their tested images. If you use a different IDE, this setup may not be suitable for you and you are encouraged to document your own local environment setup process.

The container that VS Code will start for you will give you access to the following features:

- [`Microsoft OpenJDK 17`][java17]
- [`Python 3.10`][python310]
- [`Git`][gitscm]
- [`GitHub CLI`][github.cli]
- [`Gradle`][gradle]
- [`TexLive`](https://www.tug.org/texlive/)
  - Installs `texlive-latex-base`, `texlive-latex-recommended`, `texlive-pictures`, and `texlive-fonts-recommended` for processing `LaTeX` documents like our written deliverables.
- [`Node`][node]
  - [`gitmoji`](https://gitmoji.dev/) (*npm hosted plugin*).

[You can read more about this container image from the official maintainers, Microsoft][java.container].

> :memo: **Note**: Although we are currently using Microsoft's build of OpenJDK 17, we can easily swap this out for another vendor's image and keep integration by forking their [their open-source dockerfiles](https://github.com/microsoft/vscode-dev-containers/blob/main/containers/java/.devcontainer/base.Dockerfile).

#### About containers

Containers allow us to standardize working environments, isolate dependency installations between projects, and package software for future deployment. They also have the side effect of being self-documenting methods for writing, maintaining, and sharing _reproducible_ data science projects ([Nüst, et al., 2020][writing.dockerfiles]).

> :memo: **Note**: [You can read more about containers here][.containers]. [`Docker`][docker] is one type of container software format. Alternative forms such as [podman][podman.io] also exist.

#### Dependencies

You'll need to have [`Docker Desktop`](https://www.docker.com/products/docker-desktop) (for Windows/MacOS) or [`Docker Engine CE/EE`](https://hub.docker.com/search?offering=community&operating_system=linux&q=&type=edition) (for Linux) installed.

You'll also need the following VS Code extension(s) installed:

- [Remote-Containers][remote.containers]

#### Starting your `.devcontainer`

To get started:

1. Clone your repository to your host machine.
2. Open the project's root directory in Visual Studio Code.
3. Access the Command Palette (`Ctrl`+`Shift`+`P`) and select `Remote-Containers: Open Folder in Container...`

By following the stated instructions, VS Code will:

- Pull the Docker image specified by the Dockerfile (if you haven't already);
- Build the development environment using the `.devcontainer` specifications.
- Start a container with the project's root folder mounted inside the container at `/`.

The first build always takes the longest, but Docker will cache the built image to make starting new containers quicker.

> :warning: **Warning**: If you are using the SSH protocol to connect with the GitHub repository, you will need to configure your environment to forward SSH-agent credentials into the container. [You may want to refer to this guide][ssh.devcontainers].

## Contributing, submitting issues, etc.

If you are a project contributor, you should consult the [CONTRIBUTING](CONTRIBUTING.md) guide for more information.

While our research is open-access and our code is open-sourced, we are not accepting external contributors at this time.

## Maintainers

This repository and the subsequent research is managed by the following users:

- [@rimij405](https://github.com/rimij405)
- [@ritambharajha](https://github.com/ritambharajha)
- [@Sreeni20](https://github.com/Sreeni20)
- [@teej42](https://github.com/teej42)

## License

The contents of this repository and its related wiki are
licensed under a [MPL-2.0](LICENSE) license.

[remote.containers]: https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers
[writing.dockerfiles]: https://doi.org/10.1371/journal.pcbi.1008316
[docker]: https://www.docker.com/
[podman.io]: https://podman.io/
[.devcontainer]: https://code.visualstudio.com/docs/remote/containers
[.containers]: https://www.docker.com/resources/what-container
[java.container]: https://github.com/microsoft/vscode-dev-containers/tree/main/containers/java
[ssh.devcontainers]: https://code.visualstudio.com/docs/remote/containers#_sharing-git-credentials-with-your-container
[gitscm]: https://git-scm.com/
[github.cli]: https://cli.github.com/
[python310]: https://www.python.org/downloads/release/python-3100/
[java17]: https://www.microsoft.com/openjdk
[gradle]: https://gradle.org/
[node]: https://nodejs.org/en/
