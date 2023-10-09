# AMDGPU-PRO

AMD Proprietary driver packaged for Archlinux. Include Vulkan, OpenGL and OpenCL drivers.

Contains .deb packages for Ubuntu repackaged for Archlinux. Packages comes from the Radeon repo: http://repo.radeon.com/amdgpu/ 

Based on the work by Ashark: https://github.com/Ashark/archlinux-amdgpu-pro

## Supported Cards

https://www.amd.com/en/support/kb/release-notes/rn-amdgpu-unified-linux-23-20

AMD Product Family Compatibility                                      |                                                          |                                                    
-----                                                                 |         -----                                            |
AMD Radeon™ RX 7900/7800/7700/7600 Series Graphics                    |  AMD Radeon™ Pro W7500 / W7600                           |
AMD Radeon™ RX 6900/6800/6700/6600/6500/6400/6300 Series Graphics     |  AMD Radeon™ Pro WX 9100 / 8200                          |
AMD Radeon™ RX 5700/5600/5500/5300 Series Graphics                    |  AMD FirePro™ W9100 / W8100 / W7100 / W5100 / W4300      |
AMD Radeon™ VII Series Graphics​                                       |                                                          |
AMD Radeon™ RX Vega Series Graphics                                   |                                                          |
AMD Radeon™ Vega Frontier Edition                                     |                                                          |
AMD Radeon™ RX 550/560/570/580/590 Series Graphics                    |                                                          |
AMD Radeon™ RX 460/470/480 Graphics                                   |                                                          |
AMD Radeon™ Pro Duo                                                   |                                                          |
AMD Radeon™ R9 Fury/Fury X/Nano Graphics                              |                                                          |
AMD Radeon™ R9 360/380/380X/390/390X Graphics​                         |                                                          |
AMD Radeon™ R9 285/290/290X Graphics                                  |                                                          |

## OpenCL

For these models of GPUS use the ROCm opencl stack. Older then that use opencl-amdgpu-pro and lib32-opencl-amdgpu-pro packages provided by this repo

https://rocmdocs.amd.com/en/latest/release/windows_support.html#windows-supported-gpus

Legacy OpenCL stack (Proprietary), supports legacy products older than Vega 10 (this repo opencl-amdgpu-pro and lib32-opencl-amdgpu-pro)

ROCr OpenCL stack, supports Vega 10 and later products

Name                        |     Architecture    |    LLVM Target
------                      |       ------        |     ------
AMD Radeon™ RX 7900 XTX     |      RDNA3          |    gfx1100
AMD Radeon™ RX 7900 XT      |      RDNA3          |    gfx1100
AMD Radeon™ RX 7600         |      RDNA3          |    gfx1102
AMD Radeon™ RX 7600         |      RDNA2          |    gfx1030
AMD Radeon™ RX 7600         |      RDNA2          |    gfx1030
AMD Radeon™ RX 6800 XT      |      RDNA2          |    gfx1030
AMD Radeon™ RX 6800         |      RDNA2          |    gfx1030
AMD Radeon™ RX 6750         |      RDNA2          |    gfx1032
AMD Radeon™ RX 6700 XT      |      RDNA2          |    gfx1032
AMD Radeon™ RX 6700         |      RDNA2          |    gfx1032
AMD Radeon™ RX 6650 XT      |      RDNA2          |    gfx1032
AMD Radeon™ RX 6600 XT      |      RDNA2          |    gfx1032
AMD Radeon™ RX 6600         |      RDNA2          |    gfx1032
AMD Radeon Pro™ W7900       |      RDNA3          |    gfx1100
AMD Radeon Pro™ W7800       |      RDNA3          |    gfx1100
AMD Radeon Pro™ W6800       |      RDNA2          |    gfx1030
AMD Radeon Pro™ W6600       |      RDNA2          |    gfx1032
AMD Radeon Pro™ W5500       |      RDNA1          |    gfx1012
AMD Radeon Pro™ VII         |      GCN5.1         |    gfx906

## Profile

To switch the defualt driver for Vulkan and OpenGL you can use this script in /etc/profile.d/

    #!/usr/bin/bash

    ICD_DIR="/usr/share/vulkan/icd.d"

    AMDGPUPROGL64_DIR="/usr/lib/amdgpu-pro"

    AMDGPUPROGL32_DIR="/usr/lib32/amdgpu-pro"

    # RADV
    #export VK_ICD_FILENAMES="${ICD_DIR}/radeon_icd.i686.json:${ICD_DIR}/radeon_icd.x86_64.json"

    # AMDVLK
    #export VK_ICD_FILENAMES="${ICD_DIR}/amd_icd32.json:${ICD_DIR}/amd_icd64.json"

    # AMDGPU-PRO
    #export VK_ICD_FILENAMES="${ICD_DIR}/amd_pro_icd32.json:${ICD_DIR}/amd_pro_icd64.json"

    # Use AMDGPU-PRO OpenGL

    #export LD_LIBRARY_PATH="${AMDGPUPROGL64_DIR}/:${LD_LIBRARY_PATH}:${AMDGPUPROGL32_DIR}/:${LD_LIBRARY_PATH}"

    # Use Mesa OpenGL

    #export LD_LIBRARY_PATH="/usr/lib/:${LD_LIBRARY_PATH}:/usr/lib32/:${LD_LIBRARY_PATH}"

### Prebuild package

Prebuild package are available at https://repo.archdevlab.org/x86_64/amdgpu-pro

You can add this repo to your pacman.conf

    [amdgpu-pro]
    SigLevel = Optional TrustAll
    Server = https://repo.archdevlab.org/$arch/$repo
