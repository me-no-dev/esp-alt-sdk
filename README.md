# ESP8266 Cross platform SDK
### Build Status:
##### xtensa-lx106-elf
| Windows | MacOS | Linux |
| ------- | ----- | ----- |
| [![Build Status](https://jenkins.dandle.co/buildStatus/icon?job=xtensa-lx106-elf/label=build-win2012r2x64-01)](https://jenkins.dandle.co/job/xtensa-lx106-elf/label=build-win2012r2x64-01/)| [![Build Status](https://jenkins.dandle.co/buildStatus/icon?job=xtensa-lx106-elf/label=build-osx-01)](https://jenkins.dandle.co/job/xtensa-lx106-elf/label=build-osx-01/) | [![Build Status](https://jenkins.dandle.co/buildStatus/icon?job=xtensa-lx106-elf/label=build-ubuntu14-01)](https://jenkins.dandle.co/job/xtensa-lx106-elf/label=build-ubuntu14-01/) |

##### esp-alt-sdk
| SDK | Windows | MacOS | Linux |
| ------------- | ------------- | ------------- | ------------- |
| 1.4.0 | [![Build Status](https://jenkins.dandle.co/buildStatus/icon?job=esp-alt-sdk/VERSION=1.4.0,label=build-win2012r2x64-01)](https://jenkins.dandle.co/job/esp-alt-sdk/VERSION=1.4.0,label=build-win2012r2x64-01/) | [![Build Status](https://jenkins.dandle.co/buildStatus/icon?job=esp-alt-sdk/VERSION=1.4.0,label=build-osx-01)](https://jenkins.dandle.co/job/esp-alt-sdk/VERSION=1.4.0,label=build-osx-01/) | [![Build Status](https://jenkins.dandle.co/buildStatus/icon?job=esp-alt-sdk/VERSION=1.4.0,label=build-ubuntu14-01)](https://jenkins.dandle.co/job/esp-alt-sdk/VERSION=1.4.0,label=build-ubuntu14-01) |
| 1.5.0 | [![Build Status](https://jenkins.dandle.co/buildStatus/icon?job=esp-alt-sdk/VERSION=1.5.0,label=build-win2012r2x64-01)](https://jenkins.dandle.co/job/esp-alt-sdk/VERSION=1.5.0,label=build-win2012r2x64-01/) | [![Build Status](https://jenkins.dandle.co/buildStatus/icon?job=esp-alt-sdk/VERSION=1.5.0,label=build-osx-01)](https://jenkins.dandle.co/job/esp-alt-sdk/VERSION=1.5.0,label=build-osx-01/) | [![Build Status](https://jenkins.dandle.co/buildStatus/icon?job=esp-alt-sdk/VERSION=1.5.0,label=build-ubuntu14-01)](https://jenkins.dandle.co/job/esp-alt-sdk/VERSION=1.5.0,label=build-ubuntu14-01) |


### Work in progress
_Please don't report bugs (yet)_
## Why?
- Cross platform
    + Windows
    + Linux
    + MacOS
- Up-to-date binary builds
- Open build process 
- Gcc 5.1.0
- Gdb on all platforms
- Additional tools (also compiled from source)
- Small size
    + Stripped out debug symbols
    + UPX compressed

## Contents
- [Xtensa Toolchain](https://github.com/jcmvbkbc/gcc-xtensa/)
- [Espressif NONOS SDK](http://bbs.espressif.com/viewforum.php?f=46) with official patches
- [lx106-hal](https://github.com/tommie/lx106-hal)
- [newlib-xtensa](https://github.com/jcmvbkbc/newlib-xtensa)
- [esp-binutils](https://github.com/fpoussin/esp-binutils.git)
- [gdb](http://www.gnu.org/software/gdb)
- [esptool](https://github.com/themadinventor/esptool)
- [esptool2](https://github.com/raburton/esptool2)
- [memanalyzer](https://github.com/Sermus/ESP8266_memory_analyzer)

## Download
__Download links are still unstable, please check__ [bintray](https://bintray.com/kireevco/generic/esp-alt-sdk/view#files)

| Windows | MacOS | Linux |
| ------------- | ------------- | ------------- |
| [1.4.0](https://bintray.com/kireevco/generic/esp-alt-sdk/1.4.0/view#files) | [1.4.0](https://bintray.com/kireevco/generic/esp-alt-sdk/1.4.0/view#files) | [1.4.0](https://bintray.com/kireevco/generic/esp-alt-sdk/1.4.0/view#files) |
| [1.5.0](https://bintray.com/kireevco/generic/esp-alt-sdk/1.5.0/view#files) | [1.5.0](https://bintray.com/kireevco/generic/esp-alt-sdk/1.5.0/view#files) | [1.5.0](https://bintray.com/kireevco/generic/esp-alt-sdk/1.5.0/view#files) |
| [1.3.0-rtos](https://bintray.com/kireevco/generic/esp-alt-sdk/1.3.0-rtos/view#files) | [1.3.0-rtos](https://bintray.com/kireevco/generic/esp-alt-sdk/1.3.0-rtos/view#files) | [1.3.0-rtos](https://bintray.com/kireevco/generic/esp-alt-sdk/1.3.0-rtos/view#files) |

## Build yourself
### Windows
Install git:
```cmd
choco install git.install --params="/NoAutoCrlf" -y
```

Install ConEmu (Optional)
```cmd
choco install conemu -y
```

Install imdisk(Optional)
```
wget http://files1.majorgeeks.com/de670c6775d17d4f699e427ab9260fa3/drives/ImDiskTk.exe
ImDiskTk.exe /fullsilent
r:
```

Clone repo, configure environment
```cmd
git clone https://github.com/kireevco/esp-alt-sdk.git
cd esp-alt-sdk
env\mingw_10.cmd
```

Restart cmd and run:
```cmd
bash.exe -i -l -c "cd env; make"
bash.exe -i -l -c "make"
```

### MacOS
Clone repo, configure environment
```shell
git clone https://github.com/kireevco/esp-alt-sdk.git
cd esp-alt-sdk
./env/macos_10.sh
```

Start build
```shell
make -C env/ && make
```


### Ubuntu
Clone repo, configure environment
```shell
git clone https://github.com/kireevco/esp-alt-sdk.git
cd esp-alt-sdk
./env/ubuntu_10.sh
```

Start build
```shell
make -C env/ && make
```


-----
#### Credits:
- Max Fillipov (@jcmvbkbc) for major xtensa-toolchain heavylifting (gcc-extensa, newlib-xtensa)
- Paul Sokolovsky (@pfalcon) for esp-open-sdk and major integration work
- Fabien Poussin (@fpoussin) for xtensa-lx106-elf build script
