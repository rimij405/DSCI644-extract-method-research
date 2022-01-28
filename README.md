---
course: "DSCI 644"
group: "Group 7"
title: "Extract Method Refactor Research"
---

## Overview

In partial fulfillment of the course requirements for DSCI 644: Software Engineering for Data Science, our group has been tasked to accomplish a semester-length research study involving the accurate assessment and detection of duplicate code in need of refactoring.

Our work consists of identifying a specific problem under this broad field of duplicate code detection and engineering a solution (with accurate citations when referencing existing bodies of work).

If you are a project maintainer:

- [You can find the project board here](https://github.com/rimij405/DSCI644-extract-method-research/projects?type=beta).
- [you can find the project milestones here](https://github.com/rimij405/DSCI644-extract-method-research/milestones).

## Table of Contents

> :construction: This section is under construction. Details are subject to change.

- [Overview](#overview)
- [Table of Contents](#table-of-contents)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Obtaining the raw data](#obtaining-the-raw-data)
  - [Rendering $\LaTeX$ documents](#rendering-latex-documents)
    - [Using OverLeaf](#using-overleaf)
    - [Setting up your $\TeX$ environment with a container](#setting-up-your-tex-environment-with-a-container)
    - [Setting up your $\TeX$ environment locally](#setting-up-your-tex-environment-locally)
      - [Cross-platform options](#cross-platform-options)
      - [Windows-specific](#windows-specific)
      - [MacOS-specific](#macos-specific)
      - [Linux packages](#linux-packages)
- [Setting up a development environment](#setting-up-a-development-environment)
  - [Minimum Requirements](#minimum-requirements)
  - [Setting up your local environment without containers](#setting-up-your-local-environment-without-containers)
  - [Setting up your local environment with containers](#setting-up-your-local-environment-with-containers)
    - [Setting up your local environment with Docker](#setting-up-your-local-environment-with-docker)
    - [Setting up your local environment with `.devcontainer/`](#setting-up-your-local-environment-with-devcontainer)
- [Contributing, submitting issues, etc.](#contributing-submitting-issues-etc)
- [Maintainers](#maintainers)
- [License](#license)

## Project Structure

This repository is organized as follows:

```bash
. # Hierarchy from project's root folder.
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

---

## Getting Started

_An overview of our project, how to download and use, basic templates and examples, and more._

To get started, clone this repository to your working environment using the `https`, `ssh`, or `github-cli` remote options available to you:

```bash
# Using the `https` remote method, as an example.
$ git clone https://github.com/rimij405/DSCI644-extract-method-research.git [DESTINATION]

# Cloning into '[DESTINATION]'...
# remote: Enumerating objects: 45, done.
# remote: Counting objects: 100% (45/45), done.
# remote: Compressing objects: 100% (34/34), done.
# remote: Total 45 (delta 11), reused 36 (delta 6), pack-reused 0
# Unpacking objects: 100% (45/45), 28.21 KiB | 1.88 MiB/s, done.
```

Once you have the files available, you'll be able to accomplish one (or several) tasks by following the information listed below.

> <a name="todo"> :memo: **Note**: Items tagged with 🚧 are currently stubs in need of expansion.
<!-- THIS SPACING IS INTENTIONAL -->
> :star: This item is a recommended plan of action.

- To audit the data used in our report(s):
  - [Fetch the raw data](#todo). :construction:
  - [Generate processed data artifacts using our scripts](#todo). :construction:.
- To render the $\LaTeX$ document:
  - (:star:) [Setup your $\TeX$ environment with a container](#setting-up-your-tex-environment-with-a-container).
  - [Install or compile $\TeX$ binaries manually](#setting-up-your-tex-environment-locally).
- To compile or build project code from source:
  - (:star:) (**Requires VS Code**) [Setup up a `.devcontainer` environment](#setting-up-your-local-environment-with-devcontainer).
  - (:star:) [Setup a Docker container environment](#setting-up-your-local-environment-with-docker).
  - [Install the project dependencies manually](#setting-up-your-local-environment-without-containers).
- To inquire about the project, [consider making a discussion post](https://github.com/rimij405/DSCI644-extract-method-research/discussions).

> :exclamation: **Action**: Take this opportunity to update this document with your own method of setting up your local environment below.

Described below are different guides on setting up aspects of the project (eg., sourcing data, rendering reports, executing code, etc.) that can serve as starting points for more complex usage of the code.

### Obtaining the raw data

> :construction: This section is under construction. Details are subject to change.

- :memo: Where did we get the raw data from?
- :memo: How do we get the raw data into the project directory?

### Rendering $\LaTeX$ documents

This project has `.tex` file documents that you may want to render.

Our written deliverables make use of the [Association for Computing Machinery (ACM)][acm]'s [Conference Proceedings Primary Article Template][acm.template]. This is a special $\LaTeX$ template depends on the special [`acmart` package, which you can read about here][acmart.pdf].

> :memo: [$\LaTeX$][latex] is a document preparation system that defines a series of macros atop the [$\TeX$][texlive] typesetting program.
>
> - FAQ: [What is the difference between $\LaTeX$ and $\TeX$](https://tex.stackexchange.com/a/315)?
> - FAQ: [How do I get started with $\TeX$](https://www.tug.org/begin.html)?
> - FAQ: [Is there a resource for learning $\LaTeX$](https://www.learnlatex.org/)?
> - FAQ: [Where can I find a cheatsheet for $\LaTeX$](https://wch.github.io/latexsheet/)?

#### Using OverLeaf

[OverLeaf][overleaf] offers a free plan for students who can collaborate with up to one other named contributor. All plans also include _unlimited sharing_ using their [Link Sharing][overleaf.sharing] feature. People with access to this secret link are able to view _and_ edit the document.

Just take a `.tex` file in this repository and bring it into a new OverLeaf project. While the resulting `.pdf` file won't be included in the repository automatically, it can be a neat way to collaborate in real-time.

#### Setting up your $\TeX$ environment with a container

> :runner: tldr: If you have a container engine installed, you should be able to start a container with the appropriate $\TeX$ dependencies installed.

The process for setting up a containerized $\TeX$ environment is the same as any:

1. Ensure you have an appropriate container engine installed (eg. [Docker][docker]).
2. Pull an existing (or create a new) container image that has appropriate packages installed.
3. Start the container when you need to use it, mounting your `.tex` file as needed.

The official [`texlive/texlive` image](https://hub.docker.com/r/texlive/texlive) may be enough if you only need to convert `.tex` files. They also offer historic versions since 2014, using tags (eg. `texlive/texlive:TL2018-historic`). The project's [official wiki](https://gitlab.com/islandoftex/images/texlive/-/wikis/home) provides links to additional tutorials.

> FAQ: [How can I build my $\LaTeX$ documents locally using Docker](https://gitlab.com/islandoftex/images/texlive/-/wikis/Building-LaTeX-documents-locally-using-Docker)?

If you use a different package, you'll want to make sure the image you use installs the `texlive` package. You will also want to make sure that the image only installs $\LaTeX$ packages that are on [ACM's approved packages list](https://www.acm.org/publications/taps/accepted-latex-packages).

> :memo: **Note**: You may find great benefit in following one of the [alternative methods listed here](https://towardsdatascience.com/three-ways-to-create-dockernized-latex-environment-2534163ee0c4#3fca).

#### Setting up your $\TeX$ environment locally

> :runner: tldr: If you must install locally, use [`MikTeX`](https://miktex.org/) if you are short on space. Use [native (vanilla) `TeX Live`](https://www.tug.org/texlive/) if you want the full (~4GB) installation.

The $\TeX$ installation experience can vary between platforms and on your needs.

##### Cross-platform options

- For a secure, full (~4GB), cross-platform $\TeX$ installation, use [native (vanilla) `TeX Live`](https://www.tug.org/texlive/).
  - Provides all the major TeX-related programs, macro packages, and fonts that are free software.
- For a minimal (~130 MB), cross-platform $\TeX$ installation, use [`MikTeX`](https://miktex.org/).
  - Provides _on-the-fly_, online package installation. Install packages as you need them.
  - Provides [`TeXworks`](https://www.tug.org/texworks/) frontend.

> :memo: **Note**: There are some [advantages to choosing `texlive` over `MikTeX` and vice versa](https://tex.stackexchange.com/questions/20036/what-are-the-advantages-of-tex-live-over-miktex).

##### Windows-specific

- For a minimal (~130 MB), Windows $\TeX$ installation, use [`proTeXt`](https://www.tug.org/protext/) (based on the [`MikTeX`](https://miktex.org/) distribution).
  - Provides _on-the-fly_, online package installation. Install packages as you need them.
  - Provides [`TeXStudio`](https://www.texstudio.org/) frontend.

##### MacOS-specific

- For a minimal, MacOS $\TeX$ installation, use [`MacTex`](https://www.tug.org/mactex/).
  - Provides `TeX Live` with `TeX`, `LaTeX`, `XeTeX`, `LuaTeX`, and associated style and class files, fonts, documentation, and more.
  - Provides [`Ghostscript`](https://www.ghostscript.com/) which can process `postscript`, `eps`, and `pdf` files.
  - Provides [`TeXShop`](https://pages.uoregon.edu/koch/texshop/), [`TeX Live Utility`](https://amaxwell.github.io/tlutility/), [`BibDesk`](https://bibdesk.sourceforge.io/), and [`LaTeXiT`](https://www.chachatelier.fr/latexit/) in /Applications/TeX.

##### Linux packages

- For custom, Linux $\TeX$ installation, your distro might provide custom packages of various sizes.
  - Debian-based systems provides a custom [`texlive`](https://www.tug.org/texlive/) package (with addons in `texlive-pictures`, `texlive-latex-extra`, etc.).
  - It may already be installed; check with `tlmgr --version`.

> :warning: **Warning** You may come across an issue with outdated repository keys when using a distrobution package that bundles an older version.

When installing the `texlive` package your distro has prepackaged, you may end up receiving an older version of `texlive` (eg., TeXlive 2019). As a mature ecosystem, this is typically fine, but attempts to update your packages might look like this:

```bash
$ tlmgr update --self --all # or tlmgr list
# /usr/local/texlive/2019/bin/x86_64-linux/tlmgr: unexpected return value from verify_checksum: -5
```

If you know what you're doing, you could potentially update the expired key:

```bash
curl -fsSL https://www.tug.org/texlive/files/texlive.asc | tlmgr key add -
```

If the error still persists, you have other troubleshooting options at your disposal:

1. Point to an older, archived `texlive` package repository.
2. Update the currently installed `texlive` package to a new version.
3. Install a new, separate `texlive` that is of a newer version.

You can point to an older repository by finding its uri in a historic archive and running the following:

```bash
# Initialize usermode.
sudo tlmgr init-usertree

# Replace the default repository with the older one.
sudo tlmgr option repository https://ftp.math.utah.edu/pub/tex/historic/systems/texlive/2019/tlnet-final
```

## Setting up a development environment

If you would like to _reproduce_ the research we have conducted, you may want to recreate our development environment. We provide instructions for both containerized and container-less setups.

### Minimum Requirements

> :construction: This section is under construction. Details are subject to change.

Your local or containerized environment should, at a minimum, provide the following dependencies:

| Dependency            | Version  |
| --------------------- | -------- |
| [Java][java17]        | ^17      |
| [NodeJS][node]        | ^16.13.2 |
| [Python 3][python310] | ^3.10    |

This list will continue to grow as the project continues.

### Setting up your local environment without containers

> :warning: **Warning**: This approach is not recommended and should only be used if your system cannot run a container engine like [Docker][docker] or [podman][podman.io]. If you are reproducing our research, you must be careful to isolate project dependencies using virtual environments to prevent cross-project interactions.

<!-- THIS SPACE IS INTENDED -->

> :construction: This section is under construction. Details are subject to change.

Installation of the project dependencies can be done manually by following the appropriate steps for each tool. If there are additional caveats to consider, we'll add them in here.

### Setting up your local environment with containers

> :construction: This section is under construction. Details are subject to change.

Using a containerized environment is recommended for this project.

> :memo: **About Containers**: Containers allow us to standardize working environments, isolate dependency installations between projects, and package software for future deployment. They also have the side effect of being self-documenting methods for writing, maintaining, and sharing _reproducible_ data science projects ([Nüst, et al., 2020][writing.dockerfiles]).
>
> [You can read more about containers here][.containers]. [`Docker`][docker] is one type of container software format; alternative container engines such as [podman][podman.io] also exist.

#### Setting up your local environment with [Docker][docker]

> :construction: This section is under construction. Details are subject to change.

This method is recommended if you are able to run container engines and you do not want to be tied to using the VS Code IDE. If you want a container that has tight integration with VS Code, see the next section on `.devcontainer`s.

To use Docker containers, you'll need to have [`Docker Desktop`][docker.desktop] (for Windows/MacOS) or [`Docker Engine CE/EE`][docker.engine] (for Linux) installed. Alternative container engines, like [podman][podman.io] can be used after following a similar set of steps.

The typical workflow is to:

1. Ensure you have an appropriate container engine installed (eg. [Docker][docker]).
2. Pull an existing (or create a new) container image that has appropriate packages installed.
3. Start the container when you need to use it, mounting your directory or files as needed.

Any container image that fulfills the project dependencies should be capable for your use.

In the future, if we create a custom image we will add it to a container registry for you to have access to.

#### Setting up your local environment with `.devcontainer/`

> :warning: **Warning**: This setup strongly integrates with the VS Code IDE. If you are not comfortable using VS Code or you do not want to use this IDE, you may want to try one of the other setup guides.

<!-- THIS SPACING IS INTENTIONAL -->

> :construction: This section is under construction. Details are subject to change.

If you use [VS Code][vscode] as your IDE, you might find `devcontainer`s to be an appealing option.

> :memo: **Note**: [If you are not familiar with `development containers` you can read more about them here][.devcontainer].

The `.devcontainer/` directory contains a `devcontainer.json` configuration file and a special `Dockerfile` (based on a `Java` 17 image) that was automatically generated by VS Code.

You'll also need the following VS Code extension(s) installed:

- [Remote-Containers][remote.containers]

The main advantage of the `.devcontainer` format over pure container images is the integration support VS Code has for a majority of their tested images. If you use a different IDE, this setup may not be suitable for you and you are encouraged to document your own local environment setup process.

[You can read more about this container image from the official maintainers, Microsoft][java.container].

The container that VS Code will start for you will give you access to the following features:

- [`Microsoft OpenJDK 17`][java17]
- [`Python 3.10`][python310]
- [`Git`][gitscm]
- [`GitHub CLI`][github.cli]
- [`Gradle`][gradle]
- [`TexLive`][texlive]
  - Installs `texlive-latex-base`, `texlive-latex-recommended`, `texlive-pictures`, and `texlive-fonts-recommended` for processing `LaTeX` documents like our written deliverables.
- [`Node`][node]
  - [`gitmoji-cli`](https://github.com/carloscuesta/gitmoji-cli) (_npm hosted plugin_).

> :memo: **Note**: Although we are currently using Microsoft's build of OpenJDK 17, we can easily swap this out for another vendor's image and keep integration by forking their [their open-source dockerfiles](https://github.com/microsoft/vscode-dev-containers/blob/main/containers/java/.devcontainer/base.Dockerfile).

To get your new `.devcontainer` started:

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

[.containers]: https://www.docker.com/resources/what-container
[.devcontainer]: https://code.visualstudio.com/docs/remote/containers
[acm]: https://www.acm.org/publications/authors/submissions
[acm.template]: https://www.overleaf.com/latex/templates/acm-conference-proceedings-primary-article-template/wbvnghjbzwpc
[acmart]: https://ctan.org/pkg/acmart?lang=en
[acmart.pdf]: https://www.acm.org/binaries/content/assets/publications/consolidated-tex-template/acmart.pdf
[docker]: https://www.docker.com/
[docker.engine]: https://hub.docker.com/search?offering=community&operating_system=linux&q=&type=edition
[docker.desktop]: https://www.docker.com/products/docker-desktop
[github.cli]: https://cli.github.com/
[gitscm]: https://git-scm.com/
[gradle]: https://gradle.org/
[java.container]: https://github.com/microsoft/vscode-dev-containers/tree/main/containers/java
[java17]: https://www.microsoft.com/openjdk
[latex]: https://www.latex-project.org/
[node]: https://nodejs.org/en/
[overleaf]: https://www.overleaf.com/
[overleaf.sharing]: https://www.overleaf.com/learn/how-to/What_is_Link_Sharing%3F
[podman.io]: https://podman.io/
[python310]: https://www.python.org/downloads/release/python-3100/
[remote.containers]: https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers
[ssh.devcontainers]: https://code.visualstudio.com/docs/remote/containers#_sharing-git-credentials-with-your-container
[texlive]: (https://www.tug.org/texlive/)
[vscode]: https://code.visualstudio.com/
[writing.dockerfiles]: https://doi.org/10.1371/journal.pcbi.1008316
