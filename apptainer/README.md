
## Apptainer Container

The directory contains the [Apptainer](https://apptainer.org/) definitions.


### NGC Containers

The NVIDIA NGC containers are optimized for GPUs. 

```shell
# Build the Apptainer Container
sudo apptainer build pytorch_ngc.sif pytorch_ngc.def

# Run the Container with GPU Support
apptainer run --nv pytorch_ngc.sif

# Access Jupyter Lab
http://localhost:8888/
```

```shell
# Running in the Background
apptainer instance start --nv pytorch_ngc.sif my_jupyter

# Stop the instance later with:
apptainer instance stop my_jupyter
```

- _If no GPU is available: drop `--nv` flag_

```shell
# Run the Container without GPU Support
apptainer run pytorch_ngc.sif
```

### Non-NGC Containers

On can simply build container from latest PyTorch docker images with or without GPU versions:


```shell
# Build the Apptainer Container:
sudo apptainer build pytorch_cpu.sif pytorch_cpu.def

# Run the Container:
apptainer run pytorch_cpu.sif
```

