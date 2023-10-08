# AMDGPU-PRO

AMDGPU-PRO driver packaged for Archlinux. Include Vulkan, OPENGL and OPENCL drivers

Contains .deb packages for Ubuntu repackaged for Archlinux. Packages comes from the Radeon repo: http://repo.radeon.com/amdgpu/ 

Based on the work by Ashark: https://github.com/Ashark/archlinux-amdgpu-pro

### Prebuild package

Prebuild package are available at https://repo.archdevlab.org/x86_64/amdgpu-pro

You can add this repo to your pacman.conf

    [amdgpu-pro]
    SigLevel = Optional TrustAll
    Server = https://repo.archdevlab.org/$arch/$repo
