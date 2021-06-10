# Jetson-Xavier-NX-RAPIDS
This repo is being created to describe the process of building a RAPIDS Spark cluster on NVIDIA Jetson Xavier NXs.

All steps assume beginning from a fresh jetpack install <b>R32 (release), REVISION: 5.1</b> Jetpack Version 4.5.1
# Identifying initial versions
## Check gcc Version
```gcc --version```<br>
gcc (Ubuntu/Linaro 7.5.0-3ubuntu1~18.04) 7.5.0

## Check cuda Version
```cat /usr/local/cuda/version.txt```<br>
CUDA Version 10.2.89

## Check nvcc version
```nvcc --version```<br>
bash: nvcc: command not found<br>
```/usr/local/cuda/bin/nvcc --version```<br>
nvcc: NVIDIA (R) Cuda compiler drcmake version 3.10.2

Copyright (c) 2005-2019 NVIDIA Corporation
Built on Wed_Oct_23_21:14:42_PDT_2019
Cuda compilation tools, release 10.2, V10.2.89

## Check cmake version
```cmake --version```<br>
cmake version 3.10.2

# Evaluation requirements and upgrading
According to Adam Thomson's repo found <a href="https://github.com/awthomp/rapids-jetson">HERE</a> the requirements to build RAPIDS are as follows:
<li>gcc version 5.4+</li>
<li>nvcc version 9.2+</li>
<li>cmake version 3.12.4+</li>
<li>CUDA 9.2+</li>
<li>NVIDIA driver 396.44+</li>

## Upgrading cmake
It appears the only package that needs upgrading is cmake.

First remove existing version of cmake
```
sudo apt remove --purge cmake
hash -r
```
Installing newest version. At the time of this writing, when trying to install cmake with apt-get the latest version installed was 3.10.2. Using snap I was able to get 3.20.3
```
sudo snap install cmake --classic
```
```
cmake --version
```
cmake version 3.20.3

CMake suite maintained and supported by Kitware (kitware.com/cmake).

Following Adam's site I ran
```
sudo snap install cmake --classic
```

