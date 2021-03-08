# Yamagi Quake II

Yamagi Quake II is an enhanced client for id Software's Quake
II with focus on offline and coop gameplay. Both the gameplay and the graphics
are unchanged, but many bugs in the last official release were fixed and some
nice to have features like widescreen support and a modern OpenGL 3.2 renderer
were added. Unlike most other Quake II source ports Yamagi Quake II is fully 64-bit
clean. It works perfectly on modern processors and operating systems. Yamagi
Quake II runs on nearly all common platforms; including FreeBSD, Linux, NetBSD,
OpenBSD, Windows and macOS (experimental).

This code is built upon Icculus Quake II, which itself is based on Quake II
3.21. Yamagi Quake II is released under the terms of the GPL version 2. See the
LICENSE file for further information.

## Documentation

Before asking any question, read through the documentation! The current
version can be found here: [doc/010_index.md](doc/010_index.md)

## Releases

The official releases (including Windows binaries) can be found at our
homepage: https://www.yamagi.org/quake2  
**Unsupported** preview builds for Windows can be found at
https://deponie.yamagi.org/quake2/misc/

## Building for the OGS on Ubuntu

**Install Dependancies**
```bash
sudo apt update -y && sudo apt-get install -y build-essential libsdl2-dev
```

**Required if building on the OGS**
The SDL Libraries dependancies libegl-dev, libgles-dev and libwayland-dev will fail to install due to the modfied libraries

```bash
sudo dpkg -i --force-all /var/cache/apt/archives/libegl-dev_1.3.2-1~ubuntu0.20.04.1_arm64.deb
sudo dpkg -i --force-all /var/cache/apt/archives/libgles-dev_1.3.2-1~ubuntu0.20.04.1_arm64.deb
sudo dpkg -i --force-all /var/cache/apt/archives/libwayland-dev_1.18.0-1_arm64.deb
wget https://github.com/southoz/EmulationStation-fcamod-ogs-retrooz/raw/master/libmali-rk-bifrost-g31-rxp0-wayland-gbm_1.7-2%2Bdeb10_arm64.deb
wget https://github.com/southoz/EmulationStation-fcamod-ogs-retrooz/raw/master/libmali-rk-dev_1.7-1%2Bdeb10_arm64.deb
sudo dpkg -i --force-all libmali-rk-bifrost-g31-rxp0-wayland-gbm_1.7-2+deb10_arm64.deb
sudo dpkg -i --force-all libmali-rk-dev_1.7-1+deb10_arm64.deb
```

**Clone Repository**

```bash
git clone https://github.com/southoz/yquake2-ogs
```

**Configure and Build**

```bash
cd yquake2-ogs
cmake . -DOPENAL_SUPPORT:BOOL=OFF -DVULKAN_SUPPORT:BOOL=OFF
make -j4
```
The output will be in the release directory


