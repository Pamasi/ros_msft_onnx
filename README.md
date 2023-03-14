# ROS 2 with ONNX Runtime

<p align="center"><img width="50%" src="docs/images/ONNX_Runtime_logo_dark.png" /></p>

[ONNX Runtime](https://github.com/microsoft/onnxruntime) is an open source inference engine for ONNX Models.
ONNX Runtime Execution Providers (EPs) enables the execution of any ONNX model using a single set of inference APIs that provide access to the best hardware acceleration available.

In simple terms, developers no longer need to worry about the nuances of hardware specific custom libraries to accelerate their machine learning models.
This repository demonstrates that by enabling the same code with ROS 2 to run on different hardware platforms using their respective AI acceleration libraries for optimized execution of the ONNX model.

## System Requirement

  * Microsoft Windows 10 64-bit or Ubuntu >=20.04 LTS x86_64
  * To make use of the hardware acceleration, the system is required to be compatible with [**CUDA 11.6**](https://developer.nvidia.com/cuda-toolkit) and [**cuDNN 8.2.4**](https://developer.nvidia.com/cudnn).
  [ONNX Runtime CUDA requirements](https://onnxruntime.ai/docs/execution-providers/CUDA-ExecutionProvider.html)
> For GPU support, please follow the installation steps on NVIDIA portal before proceeding.

## How to Build

ONNX Runtime team is releasing different binaries for CPU and GPU (CUDA) support. To switch between the two, a workspace rebuild is required.

* Default CPU

### Windows

```Batchfile
mkdir colcon_ws\src
cd colcon_ws

wget https://raw.githubusercontent.com/ms-iot/ros_msft_onnx/humble/onnx_windows.repos
vcs import src < onnx.repos
colcon build --cmake-args -DCUDA_SUPPORT=OFF
```

* Default GPU (CUDA)

```Batchfile
mkdir colcon_ws\src
cd colcon_ws

wget https://raw.githubusercontent.com/ms-iot/ros_msft_onnx/humble/onnx_windows.repos
vcs import src < onnx.repos
colcon build --cmake-args -DCUDA_SUPPORT=ON
```

### Ubuntu

```Batchfile
mkdir colcon_ws/src
cd colcon_ws

wget https://raw.githubusercontent.com/ms-iot/ros_msft_onnx/foxy/onnx.repos
vcs import src < onnx.repos
colcon build --cmake-args -DCUDA_SUPPORT=OFF
```

* Default GPU (CUDA)

```Batchfile
mkdir colcon_ws/src
cd colcon_ws

wget https://raw.githubusercontent.com/ms-iot/ros_msft_onnx/foxy/onnx.repos
vcs import src < onnx.repos
colcon build --cmake-args -DCUDA_SUPPORT=ON
```

## Samples Lists

  * [Object Detection with Tiny-YOLOv2/ONNX Runtime](./onnx/README.md)

# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
