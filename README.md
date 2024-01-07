# Kali NetHunter Kernel Builder (m52xq)

Based on BlackMesa123's UN1CA KSU kernel:
 - [UN1CA](https://github.com/BlackMesa123/UN1CA)
 - [Kernel](https://github.com/BlackMesa123/android_kernel_samsung_sm7325)

KernelSU:
 - [GitHub Repo](https://github.com/tiann/KernelSU)

Clang-11:
 - [Prebuilts](https://android.googlesource.com/platform//prebuilts/clang/host/linux-x86/+/refs/heads/android11-qpr3-release/clang-r383902b1/)

---

## Building

### Requirements

Needed to build the kernel
``` bash
sudo apt-get install git-core gnupg flex bison build-essential zip curl zlib1g-dev libc6-dev-i386 x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig clang axel xz-utils make ccache openssl libssl-dev bc
```

### Sources
``` bash
git clone --recurse-submodules https://github.com/BlackMesa123/android_kernel_samsung_sm7325.git -b sep-15/ksu
cd android_kernel_samsung_sm7325/

git clone https://github.com/RebertiCS/m52xq_nethunter_kernel_builder nethunter
curl -LSs "https://raw.githubusercontent.com/tiann/KernelSU/main/kernel/setup.sh" | bash -s main

cp ./nethunter/m52xq_nethunter_defconfig ./arch/aarch64/configs/
```

### Setup
``` bash
cd nethunter/
./build.sh
```

Apply the patchs:
 - add-rtl88xxau-5.6.4.2-drivers.patch
 - add-wifi-injection-4.14.patch

### Compiling
#### Automatic
Select the option _2_ on nethunter's `build.sh`, e.g, _Configure & compile kernel from scratch_
Then select _Create AnyKernel zip_

#### Manual
Image and Image-dtbo will be on out/arch/aarch64/boot/
``` bash
cd ../

# Set env
CLANG=$HOME/android/toolchains/clang_11/bin
PATH="$CLANG:$PATH"
JOBS=-j$(nproc --all)
MAKE_ENV=-j$(nproc --all) CC=clang CLANG_TRIPLE=aarch64-linux-gnu- CROSS_COMPILE=aarch64-linux-android- \
    CROSS_COMPILE_ARM32=arm-linux-androidebi- O=out ARCH=arm64 CONFIG_SECTION_MISMATCH_WARN_ONLY=y CONFIG_FRAME_WARN=0

make $MAKE_ENV m52xq_nethunter_defconfig
make $MAKE_ENV
```
