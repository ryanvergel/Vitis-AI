﻿<table class="sphinxhide">
 <tr>
   <td align="center"><img src="https://raw.githubusercontent.com/Xilinx/Image-Collateral/main/xilinx-logo.png" width="30%"/><h1>Vitis AI</h1><h0>Adaptable & Real-Time AI Inference Acceleration</h0>
   </td>
 </tr>
</table>



## IP and Tool Version Compatibility

The purpose of this page is simply to provide users with the compatibility between tools, IP and Vitis AI release versions.  The developer should ensure that they are using aligned versions of all components.

### Vivado / Vitis / Petalinux 2022.1:
 * DPUCZ IP Version 4.0
 * Vitis AI v2.5

### Vivado / Vitis / Petalinux 2021.2:
 * DPUCZ IP Version 3.4
 * Vitis AI v2.0

### Vivado / Vitis / Petalinux 2021.1:
 * DPUCZ IP Version Version 3.3
 * Vitis AI v1.4

### Vivado / Vitis / Petalinux 2020.2:
 * DPUCZ IP Version Version 3.3
 * Vitis AI v1.3

### Vivado / Vitis / Petalinux 2020.1:
 * DPUCZ IP Version Version 3.2
 * Vitis AI v1.2

### Vivado / Vitis / Petalinux 2019.2:
 * DPUCZ IP Version Version 3.2
 * Vitis AI v1.1

### Vivado / Vitis / Petalinux 2019.1:
 * DPUCZ IP Version Version 3.1
 * Vitis AI v1.0

### Vivado / Petalinux 2019.1:
 * DPUCZ IP Version 3.0

### Vivado / Petalinux 2018.2:
 * DPUCZ IP Version Version 2.0

### Vivado / Petalinux 2018.2:
 * DPUCZ IP Version Version 1.0
 * First release


## Docker Images

Previously released Vitis AI CPU Docker images are [available from Docker Hub](https://hub.docker.com/r/xilinx/vitis-ai-cpu/tags?page=1&ordering=last_updated).  If you are using a previous version of Vitis AI, you need to use the corresponding Docker version.  Here is an example of how you can retrieve an older release:

| Version | Github Link          | Checkout Git Version            | Docker Command  |
|----|-----------------------|---------------------|------------|
| 1.4.1  | https://github.com/Xilinx/Vitis-AI/releases/tag/v1.4.1              | git clone https://github.com/Xilinx/Vitis-AI.git <br />git checkout tags/v1.4.1 -b v1.4.1  | docker pull xilinx/vitis-ai-cpu:1.4.1.978      | 

## Docker Image Tags

There is a corresponding relationship between Vitis AI and the required docker image.  If you are not using the latest release of Vitis AI, you need to fetch the  docker image version associated with that older release.  We recommend that you directly use the pre-built image on Docker Hub.

The version correspondence between Vitis AI and docker image is shown in the following table:

<table>
 <tr><th>Vitis AI Version</th><th>Docker image tag</th></tr>
 <tr><td>Vitis AI v2.0.0</td><td>./docker_run.sh xilinx/vitis-ai-cpu:2.0.0.1103</td></tr>
 <tr><td>Vitis AI v1.4.1</td><td>./docker_run.sh xilinx/vitis-ai-cpu:1.4.1.978</td></tr>
 <tr><td>Vitis AI v1.4</td><td>./docker_run.sh xilinx/vitis-ai-cpu:1.4.916</td></tr>
 <tr><td>Vitis AI v1.3</td><td rowspan="3">./docker_run.sh xilinx/vitis-ai-cpu:1.3.411</td></tr>
 <tr><td>Vitis AI v1.3.1</td></tr>
 <tr><td>Vitis AI v1.3.2</td></tr>
 <tr><td>Vitis AI v1.2</td><td rowspan="2">./docker_run.sh xilinx/vitis-ai-cpu:1.2.82</td></tr>
 <tr><td>Vitis AI v1.2.1</td></tr>
 <tr><td>Vitis AI v1.1</td><td rowspan="2">./docker_run.sh xilinx/vitis-ai-cpu:1.1.56</td></tr>
 <tr><td>Vitis AI v1.1-ultra96v2</td></tr>
 <tr><td rowspan="2">Vitis AI v1.0</td><td>docker pull xilinx/vitis-ai:tools-1.0.0-cpu</td></tr>
   <tr><td>docker pull xilinx/vitis-ai:runtime-1.0.0-cpu</td></tr>
</table>

You must refer to the user documentation associated with the specific Vitis AI release in order to verify that you are using the correct version of Docker, CUDA, the Nvidia driver and Nvidia Container Toolkit.  To obtain this information, use the Github tag associated with Vitis AI release.
