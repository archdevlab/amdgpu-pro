# AMDGPU-PRO

AMDGPU-PRO driver packaged for Archlinux. Include Vulkan, OPENGL and OPENCL drivers

Contains .deb packages for Ubuntu repackaged for Archlinux. Packages comes from the Radeon repo: http://repo.radeon.com/amdgpu/ 

Based on the work by Ashark: https://github.com/Ashark/archlinux-amdgpu-pro

## Supported Cards

- AMD Radeon™ RX 7900/7800/7700/7600 Series Graphics                       AMD Radeon™ Pro W7500 / W7600
- AMD Radeon™ RX 6900/6800/6700/6600/6500/6400/6300 Series Graphics        AMD Radeon™ Pro WX 9100 / 8200
- AMD Radeon™ RX 5700/5600/5500/5300 Series Graphics                       AMD FirePro™ W9100 / W8100 / W7100 / W5100 / W4300
- AMD Radeon™ VII Series Graphics​
- AMD Radeon™ RX Vega Series Graphics
- AMD Radeon™ Vega Frontier Edition
- AMD Radeon™ RX 550/560/570/580/590 Series Graphics
- AMD Radeon™ RX 460/470/480 Graphics
- AMD Radeon™ Pro Duo
- AMD Radeon™ R9 Fury/Fury X/Nano Graphics
- AMD Radeon™ R9 360/380/380X/390/390X Graphics​
- AMD Radeon™ R9 285/290/290X Graphics

## OPENCL

opencl-amdgpu-pro and lib32-opencl-amdgpu-pro packages support products older than Vega 10

For Vega 10 and later products use the ROCm opencl stack

### Prebuild package

Prebuild package are available at https://repo.archdevlab.org/x86_64/amdgpu-pro

You can add this repo to your pacman.conf

    [amdgpu-pro]
    SigLevel = Optional TrustAll
    Server = https://repo.archdevlab.org/$arch/$repo
