![TIC-80](https://tic80.com/img/logo64.png)
**TIC-80 TINY COMPUTER** - [https://tic80.com](https://tic80.com)
[![Build Status](https://github.com/nesbox/TIC-80/workflows/Build/badge.svg)](https://github.com/nesbox/TIC-80/actions?query=workflow%3ABuild)

- [Inicio](#Inicio)
    - [Caracteristicas](#caracteristicas)
- [Descargas binarias](#descargas-binarias)
  - [Nightly builds](#nightly-builds)
- [Version PRO](#version-pro)
  - [Caracteristicas PRO](#caracteristicas-pro)
- [Comunidad](#comunidad)
- [Instrucciones de compilado](#instrucciones-de-compilado)
  - [Windows](#windows)
    - [con Visual Studio 2017](#con-visual-studio-2017)
    - [con MinGW](#with-mingw)
  - [Linux](#linux)
    - [Ubuntu 22.04 (Jammy Jellyfish)](#ubuntu-2204-jammy-jellyfish)
    - [Ubuntu 24.04 (Noble Numbat)](#ubuntu-2404-noble-numbat)
    - [Arch](#arch)
    - [Fedora 36](#fedora-36)
    - [Fedora 40](#fedora-40)
    - [Raspberry Pi OS (64-Bit) (Bookworm)](#raspberry-pi-os-64-bit-bookworm)
    - [Raspberry Pi (Retropie)](#raspberry-pi-retropie)
  - [Mac](#mac)
  - [FreeBSD](#freebsd)
- [Instrucciones de instalacion](#instrucciones-de-instalacion)
  - [Linux](#linux-1)
  - [iOS / tvOS](#ios--tvos)
  - [Credits](#credits)


# Inicio
TIC-80 es una Computadora virtual Gratis y de Codigo abierto para Crear, Jugar y Compartir pequeños juegos.

Con TIC-80 tienes las herramientas incorporadas para el desarrollo para crear: Codigo, Sprites, Mapas, Sonido. y tambien contiene una linea de comandos, lo que sera nesecario para crear pequenos juegos retro.

Los Juegos estan empaquetados en un archivo tipo cartucho, que se puede distribuir facilmente. TIC-80 funciona en todas las plataformas populares. Esto significa que su cartucho se puede reproducir en cualquier dispositivo.

Para crear un juego estilo retro, Todo el proceso de creación y ejecución se lleva a cabo bajo algunas limitaciones técnicas: Una pantalla de 240x136, Una paleta de 16 Colores, 256 Sprites a color de 8x8 pixeles, 4 canales de sonido, etc.

![TIC-80](https://user-images.githubusercontent.com/1101448/92492270-d6bcbc80-f1fb-11ea-9d2d-468ad015ace2.gif)

### Caracteristicas
- Multiples lenguajes de programacion: [Lua](https://www.lua.org),
  [Moonscript](https://moonscript.org),
  [Javascript](https://developer.mozilla.org/en-US/docs/Web/JavaScript),
  [Ruby](https://www.ruby-lang.org/en/),
  [Wren](http://wren.io/),
  [Fennel](https://fennel-lang.org),
  [Squirrel](http://www.squirrel-lang.org),
  [Janet](https://janet-lang.org), and
  [Python](https://www.python.org/).
- Games can have mouse and keyboard as input
- Games can have up to 4 controllers as input (with up to 8 buttons, each)
- Built-in editors: for code, sprites, world maps, sound effects and music
- An additional memory bank: load different assets from your cartridge while your game is executing
- Moderated community

# Descargas binarias
You can download compiled versions for the major operating systems directly from our [releases page](https://github.com/nesbox/TIC-80/releases).
## Nightly builds
Can be downloaded from [nightly builds](https://nightly.link/nesbox/TIC-80/workflows/build/main) page or from the [Github Actions](https://github.com/nesbox/TIC-80/actions?query=branch%3Amain) page.

# Version PRO
To help support TIC-80 development, we have a [PRO Version](https://nesbox.itch.io/tic80).

This version has a few additional features and binaries can only be downloaded on our Itch.io page.

For users who can't spend the money, we made it easy to build the pro version from the source code: (`cmake .. -DBUILD_PRO=On`)

## Pro features

- Save/load cartridges in text format, and create your game in any editor you want, also useful for version control systems.
- Even more memory banks: instead of having only 1 memory bank you have 8.
- Export your game without editors, and then publish it to app stores.

# Community
You can play and share games, tools and music at [https://tic80.com/play](https://tic80.com/play).

The community also hangs out and discusses on [Telegram](https://t.me/tic80) or [Discord](https://discord.gg/HwZDw7n4dN).

# Contributing
You can contribute by reporting a bug or requesting a new feature on our [issues page](https://github.com/nesbox/TIC-80/issues).
Keep in mind when engaging on a discussion to follow our [Code of Conduct](https://github.com/nesbox/TIC-80/blob/main/CODE_OF_CONDUCT.md).

You can also contribute by reviewing or improving our [wiki](https://github.com/nesbox/TIC-80/wiki).
The wiki holds TIC-80 documentation, code snippets and game development tutorials.

# Build instructions

## Windows
### with Visual Studio 2017
- install `Visual Studio 2017`
- install `git`
- install `Ruby` (you can use [RubyInstaller](https://rubyinstaller.org/))
- run following commands in `cmd`
```
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake -G "Visual Studio 15 2017 Win64" ..
```
- open `TIC-80.sln` and build
- enjoy :)

### with MinGW
- install `mingw-w64` (http://mingw-w64.org) and add `.../mingw/bin` path to the *System Variables Path*
- install `git`
- install `cmake` (https://cmake.org)
- install `Ruby` (you can use [RubyInstaller](https://rubyinstaller.org/))
- run following commands within a `mingw64` context, for example within a MingW64 shell
```
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake -G "MinGW Makefiles" ..
mingw32-make -j4
```

## Linux

### Ubuntu 22.04 (Jammy Jellyfish)

Run the following commands from a terminal:

```
# Need to install the latest CMake from https://apt.kitware.com/
test -f /usr/share/doc/kitware-archive-keyring/copyright ||
wget -O - https://apt.kitware.com/keys/kitware-archive-latest.asc 2>/dev/null | gpg --dearmor - | sudo tee /usr/share/keyrings/kitware-archive-keyring.gpg >/dev/null
echo 'deb [signed-by=/usr/share/keyrings/kitware-archive-keyring.gpg] https://apt.kitware.com/ubuntu/ jammy main' | sudo tee /etc/apt/sources.list.d/kitware.list >/dev/null
sudo apt-get update
test -f /usr/share/doc/kitware-archive-keyring/copyright ||
sudo rm /usr/share/keyrings/kitware-archive-keyring.gpg
sudo apt-get install kitware-archive-keyring

sudo apt update && sudo apt -y install build-essential cmake git libpipewire-0.3-dev libwayland-dev libsdl2-dev ruby-dev libglvnd-dev libglu1-mesa-dev freeglut3-dev libcurl4-openssl-dev
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake -DBUILD_SDLGPU=On -DBUILD_STUB=On .. --fresh && cmake --build . --parallel
```

Install with [Install instructions](#install-instructions)


### Ubuntu 24.04 (Noble Numbat)

Run the following commands from a terminal:

```
sudo apt update && sudo apt -y install build-essential cmake git libpipewire-0.3-dev libwayllrubland-dev libsdl2-dev ruby-dev libcurl4-openssl-dev libglvnd-dev libglu1-mesa-dev freeglut3-dev
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake -DBUILD_SDLGPU=On -DBUILD_STUB=On .. --fresh && cmake --build . --parallel
```

Install with [Install instructions](#install-instructions)


### Arch

run the following commands in the Terminal
```
sudo pacman -S cmake ruby mesa libglvnd glu
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake ..
make -j4
```

### Fedora 36

run the following commands in the Terminal
```
sudo dnf -y groupinstall "Development Tools" "Development Libraries"
sudo dnf -y install ruby rubygem-{tk{,-doc},rake,test-unit} cmake libglvnd-devel libglvnd-gles freeglut-devel clang libXext-devel SDL_sound pipewire-devel pipewire-jack-audio-connection-kit-devel pulseaudio-libs-devel
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake .. -DCMAKE_CXX_COMPILER=clang++ -DSDL_ALSA=On
make -j4
```

Install with [Install instructions](#install-instructions)

### Fedora 40

Run the following commands from a terminal:
```
sudo dnf -y groupinstall "Development Tools" "Development Libraries"
sudo dnf -y install ruby-devel rubygem-rake cmake clang pipewire-devel SDL2-devel SDL2_sound-devel SDL2_gfx-devel wayland-devel libXext-devel pipewire-jack-audio-connection-kit-devel pipewire-jack-audio-connection-kit-devel pulseaudio-libs-devel rubygems-devel libdecor-devel libdrm-devel mesa-libgbm-devel esound-devel freeglut-devel
cmake -DBUILD_SDLGPU=On -DBUILD_STUB=On .. --fresh
cmake --build . --parallel
```

Install with [Install instructions](#install-instructions)

### Raspberry Pi OS (64-Bit) (Bookworm)

Run the following commands from a terminal:

```
sudo apt update && sudo apt -y install cmake libpipewire-0.3-dev libwayland-dev libsdl2-dev ruby-dev libcurl4-openssl-dev
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake -DBUILD_SDLGPU=On -DBUILD_STUB=On .. --fresh && cmake --build . --parallel 2
```
Install with [Install instructions](#install-instructions)

### Raspberry Pi (Retropie)

First, add jessie-backports repo to your `/etc/apt/sources.list`

`deb [check-valid-until=no] http://archive.debian.org/debian jessie-backports main`

Then run the following commands in the Terminal

```
# required public keys
gpg --keyserver pgpkeys.mit.edu --recv-key  8B48AD6246925553
gpg -a --export 8B48AD6246925553 | sudo apt-key add -
gpg --keyserver pgpkeys.mit.edu --recv-key 7638D0442B90D010
gpg -a --export 7638D0442B90D010 | sudo apt-key add -

# upgrade system
sudo apt-get update
sudo apt-get dist-upgrade

# install software
sudo apt-get install git build-essential ruby-full libsdl2-dev zlib1g-dev
sudo apt-get install -t jessie-backports liblua5.3-dev
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake ..
make -j4

# install software ubuntu 22.04.3 LTS
sudo apt-get install git build-essential ruby-full libsdl2-dev zlib1g-dev
sudo apt-get install liblua5.3-dev
sudo apt-get install libcurl4-openssl-dev
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake ..
make -j4
```
Install with [Install instructions](#install-instructions)

_Note:_ If you are using a normal Raspberry Pi image (not Retropie) you may not
have OpenGL drivers enabled. Run `sudo raspi-config`, then select 7
for "Advanced Options", followed by 6 for "GL Drivers", and enable "GL
(Fake KMS) Desktop Driver". After changing this setting, reboot.

## Mac
install `Command Line Tools for Xcode` and `brew` package manager

run the following commands in the Terminal
```
brew install git cmake
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake ..
make -j4
```

to create application icon for development version
```
mkdir -p ~/Applications/TIC80dev.app/Contents/{MacOS,Resources}
cp -f macosx/tic80.plist ~/Applications/TIC80dev.app/Contents/Info.plist
cp -f macosx/tic80.icns ~/Applications/TIC80dev.app/Contents/Resources
cat > ~/Applications/TIC80dev.app/Contents/MacOS/tic80 <<EOF
#!/bin/sh
exec /Users/nesbox/projects/TIC-80/build/bin/tic80 --skip --scale 2 >/dev/null
EOF
chmod +x ~/Applications/TIC80dev.app/Contents/MacOS/TIC80dev
```
Make sure to update the absolute path to the tic80 binary in the script, or
update the launch arguments.

## FreeBSD
run the following commands in the Terminal
```
sudo pkg install gcc git cmake ruby libglvnd libglu freeglut mesa-devel mesa-dri alsa-lib
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake ..
make -j4
```

Mesa looks for swrast_dri.so from the wrong path, so also symlink it:

```
sudo ln -s /usr/local/lib/dri/swrast_dri.so /usr/local/lib/dri-devel/
```

# Install instructions

## Linux
To install run `sudo make install -j4`

TIC-80 can now be run with `tic80`

## iOS / tvOS
You can find iOS/tvOS version here
- 0.60.3: https://github.com/brunophilipe/TIC-80
- 0.45.0: https://github.com/CliffsDover/TIC-80

## Credits

* Filippo Rivato - [Twitter @HomineLudens](https://twitter.com/HomineLudens)
* Fred Bednarski - [Twitter @FredBednarski](https://twitter.com/FredBednarski)
* Al Rado - [Twitter @alrado2](https://twitter.com/alrado2)
* Trevor Martin - [Twitter @trelemar](https://twitter.com/trelemar)
* MonstersGoBoom - [Twitter @MonstersGoBoom](https://twitter.com/MonstersGo)
* Matheus Lessa - [Twitter @matheuslrod](https://twitter.com/matheuslrod)
* CliffsDover - [Twitter @DancingBottle](https://twitter.com/DancingBottle)
* Frantisek Jahoda - [GitHub @jahodfra](https://github.com/jahodfra)
* Guilherme Medeiros - [GitHub @frenetic](https://github.com/frenetic)
* Andrei Rudenko - [GitHub @RudenkoArts](https://github.com/RudenkoArts)
* Phil Hagelberg - [@technomancy](https://technomancy.us/colophon)
* Rob Loach - [Twitter @RobLoach](https://twitter.com/RobLoach) [GitHub @RobLoach](https://github.com/RobLoach)
* Wade Brainerd - [GitHub @wadetb](https://github.com/wadetb)
* Paul Robinson - [GitHub @paul59](https://github.com/paul59)
* Stefan Devai - [GitHub @stefandevai](https://github.com/stefandevai) [Blog stefandevai.me](https://stefandevai.me)
* Damien de Lemeny - [GitHub @ddelemeny](https://github.com/ddelemeny)
* Adrian Siekierka - [GitHub @asiekierka](https://github.com/asiekierka) [Website](https://asie.pl/)
* Jay Em (Sweetie16 palette) - [Twitter @GrafxKid](https://twitter.com/GrafxKid)
* msx80 - [Twitter @msx80](https://twitter.com/msx80) [Github msx80](https://github.com/msx80)
* Josh Goebel - [Twitter @dreamer3](https://twitter.com/dreamer3) [Github joshgoebel](https://github.com/joshgoebel)
* Joshua Minor - [GitHub @jminor](https://github.com/jminor)
* Julia Nelz - [Github @remi6397](https://github.com/remi6397) [WWW](https://nelz.pl)
* Thorben Krüger - [Mastodon @benthor@chaos.social](https://chaos.social/@benthor)
* David St-Hilaire - [GitHub @sthilaid](https://github.com/sthilaid)
* Alec Troemel - [Github @alectroemel](https://github.com/AlecTroemel)
* Kolten Pearson - [Github @koltenpearson](https://github.com/koltenpearson)
* Cort Stratton - [Github @cdwfs](https://github.com/cdwfs)
* Alice - [Github @aliceisjustplaying](https://github.com/aliceisjustplaying)
