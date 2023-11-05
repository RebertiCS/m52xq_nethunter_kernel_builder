# Kali NetHunter Kernel Builder (m52xq) (WIP)

## Installation

Clone this repository into your kernel source tree, e.g.

``` bash
git clone https://github.com/Simon1511/android_kernel_samsung_sm7325
cd android_kernel_samsung_sm7325
git clone https://github.com/RebertiCS/m52xq_nethunter_kernel_builder kali-nethunter-kernel
```

**cd** into `kali-nethunter-kernel/`, open `config` and make sure that you are happy with all the settings.

Important: Changes should not be made in this file. Copy it accross to `local.config` and delete everything except the parameters you would like to change. Change those parameters and save it.

The settings in `local.config` overwrites `config` but will itself not be overwritten by updates.
