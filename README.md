# Kali NetHunter Kernel Builder (m52xq) (WIP)

Based on BlackMesa123 UN1CA kernel:
 - [UN1CA](https://github.com/BlackMesa123/UN1CA)
 - [Kernel](https://github.com/BlackMesa123/android_kernel_samsung_sm7325)

KernelSU:
 - [GitHub Repo](https://github.com/tiann/KernelSU)


## Installation

``` bash
git clone https://github.com/BlackMesa123/android_kernel_samsung_sm7325.git -b sep-15/ksu
cd android_kernel_samsung_sm7325/
git clone --recurse-submodules https://github.com/RebertiCS/m52xq_nethunter_kernel_builder nethunter
cd ./nethunter
ln -s $PWD/KernelSU/kernel $PWD/../drivers/kernelsu
```

### Dependencies

Needed to build the kernel

``` bash
sudo apt-get install git-core gnupg flex bison build-essential zip curl zlib1g-dev libc6-dev-i386 x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig clang axel xz-utils make ccache openssl libssl-dev bc
```
