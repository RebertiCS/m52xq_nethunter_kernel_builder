# Kali NetHunter Kernel Builder (m52xq) (WIP)

## Installation

### Kernel Src

Donwload from official Samsung OSS Website

https://opensource.samsung.com/main


### Kernel Builder
Clone this repository into your kernel source tree, e.g.

``` bash
git clone https://github.com/RebertiCS/m52xq_nethunter_kernel_builder kali-nethunter-kernel
```

### Dependencies

Needed to build the kernel

``` bash
sudo apt-get install git-core gnupg flex bison build-essential zip curl zlib1g-dev libc6-dev-i386 x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig clang axel xz-utils make ccache openssl libssl-dev bc
```

## Misc

**cd** into `kali-nethunter-kernel/`, open `config` and make sure that you are happy with all the settings.

Important: Changes should not be made in this file. Copy it accross to `local.config` and delete everything except the parameters you would like to change. Change those parameters and save it.

The settings in `local.config` overwrites `config` but will itself not be overwritten by updates.
