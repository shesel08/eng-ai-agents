# Introduction

## What is this repository?

This is a template docker-based dev environment. It currently supports NVIDIA GPUs but with slight modifications it can target for x86 CPUs and Apple silicon chips. 

It currently includes the following tools:

* a `assignments` directory with an empty notebook where you need to populate with your code. The notebook can optionally use the artagents library. 
* a `project` directory for your project source code. The documentation for the project is stored separately in the `docs` directory. 
* a `docs` directory that contains the source code of [quarto](https://quarto.org/) markdown (qmd) and `ipynb` notebooks content. You use the docs folder to publish your project work. 

## How to Launch the Development Container in VS Code

This repository includes a VS Code development container configuration that can be launched with either CPU or GPU support.

### Prerequisites

1. **Install VS Code** with the "Dev Containers" extension
2. **Install Docker** and ensure it's running
3. **For GPU support**: Install NVIDIA Container Toolkit (for Linux) or Docker Desktop with GPU support

#### Manual Configuration

Modify the `service` field in `.devcontainer/devcontainer.json`:

```json
{
  "service": "torch.dev.gpu"
}
```

```
make docker-build
make docker-run
```
After changing the service configuration, close and reopen VS Code, then select "Reopen in Container" when prompted. After the container is launched, run the following command:

```bash
make start
```

Dont forget to source the environment after the make command:

```bash
source .venv/bin/activate
```

### Port Customization

You can customize the exposed ports by modifying the `.env` file. Each service has its own set of port variables:

**Dev Service Ports:**
* `DEV_QUARTO_PORT`: Quarto preview server (default: 4199)
* `DEV_JUPYTER_PORT`: Jupyter notebook server (default: 8890)
* `DEV_PORT`: Additional development server (default: 8088)

**ROS Service Ports:**
* `ROS_PORT`: ROS master port (default: 11311)
* `ROS_QUARTO_PORT`: Quarto preview server (default: 4180)
* `ROS_JUPYTER_PORT`: Jupyter notebook server (default: 8880)
* `ROS_DEV_PORT`: Additional development server (default: 8078)

Note: The actual ports exposed will be the values from your `.env` file.

### Service Selection

The repository supports multiple container configurations:

* **`dev`**: Standard PyTorch development environment  
* **`ros`**: ROS development environment with GPU support

### Additional Notes for ROS Development

You can connect to the foxglove app using the following command:

```bash
ros2 launch foxglove_bridge foxglove_bridge_launch.xml
```
## Past Week Assignment
1. assignments/assignment-1 contains all the files related to assignment-1. 

## Current Week Assignment
1. assignments/assignment-2. assignment_2.ipynb has the yolo model code to train, predict the car segmentation dataset. video_detections.parquet is the file uploaded to hugging face after prediction.car-object-detection folder contains both images and labels for training, validation and testing. 