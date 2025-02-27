# GPU

- [GPU](#gpu)
  - [Configuration](#configuration)


## Configuration
```
export DRI_PRIME=1
export NV_PRIME_RENDER_OFFLOAD=1
export VK_LAYER_NV_optimus=NVIDIA_only
export __GLX_VENDOR_LIBRARY_NAME=nvidia
glxinfo | grep "client glx vendor string"
```