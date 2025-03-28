# Gaussian Splats Research

> Making Gaussian Splatting research repos easier to set up and use, one Dockerfile at a time.

This is a multi-project repository focusing on making Gaussian Splatting research repositories easier to set up and use. I use [Tasks](https://taskfile.dev/) and Docker for setting everything up, with Github Container Registry for housing the built images.

## Pre-requisites

Install [Tasks](https://taskfile.dev/installation/) and [Docker](https://docs.docker.com/engine/install/).

## Usage

Create a `.env` file in the project root and add the path to your datasets folder, e.g.:

```txt
DATA_PATH="//c/path/to/datasets"
```

This path will be bound to a docker volume and become available inside the containers `data` folder.

> [!IMPORTANT]
> On Windows, the path must start with two forward slashes (/). For a path in the C drive: "//c/path/to/datasets"

Type `task` to see all available tasks and their descriptions.

To work on a specific project, run the tasks associated with that project. For example, with `hierarchical-3d-gaussians`, the following should be enough:

```bash
task hierarchical-3d-gaussians:pull

task hierarchical-3d-gaussians:run
```

These will pull the image, run the container, and exec into it.

> [!NOTE]
> Read the README.md in each project for project-specific instructions.

The `-all` tasks are for batch execution of tasks from all projects. For example, to clone all repositories:

```bash
task clone-all
```
