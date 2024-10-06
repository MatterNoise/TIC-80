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
    - [con MinGW](#con-mingw)
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
  - [Creditos](#creditos)


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
- Los Juegos pueden tener Mouse y Teclado como entrada
- Los Juegos pueden tener hasta 4 controles como entrada (con hasta 8 botones por mando)
- Editores incorporados: para codigo, sprites, mapas de mundo, efectos de sonido y musica
- Un banco de memoria adicional: carga diferentes assets desde tu cartucho mientras tu juego se esta ejecutando
- Una gran comunidad moderada

# Descargas binarias
Puedes descargar versiones compiladas para la mayoria de sistemas operativos directamente desde nuestra [pagina de lanzamientos](https://github.com/nesbox/TIC-80/releases).
## Nightly builds
Pueden ser descargados desde la pagina de [nightly builds](https://nightly.link/nesbox/TIC-80/workflows/build/main) o desde la pagina de [Github Actions](https://github.com/nesbox/TIC-80/actions?query=branch%3Amain).

# Version PRO
Para ayudar a seguir con el desarrollo de TIC-80, tenemos una [Version PRO](https://nesbox.itch.io/tic80).

Esta version tiene algunas mejoras y solo puede descargar desde nuestra pagina de Itch.io

Para los usuarios que no pueden pagarlo, se puede compilar desde su codigo fuente facilmente con este comando: (`cmake .. -DBUILD_PRO=On`)

## Caracteristicas PRO

- Guarda y Carga cartuchos en formato de texto, y crea tu juego en cualquier editor que desees, tambien util para sistemas de control de versiones
- Mas bancos de memoria: en vez de tener un solo banco de memoria tienes 8.
- Exporta tu juego sin editores, y despues publicalo en las tiendas de apps.

# Comunidad
Puedes jugar y compartir juegos, herramientas y musica en [https://tic80.com/play](https://tic80.com/play).

La comunidad tambien charla y discute en [Telegram](https://t.me/tic80) o [Discord](https://discord.gg/HwZDw7n4dN).

# Contribuir
Puedes contribuir reportando un bug o solicitando una nueva caracteristica en nuestra [pagina de errores](https://github.com/nesbox/TIC-80/issues).
Ten en cuenta cuando te unes a una discucion seguir nuestro [Codigo de conducta](https://github.com/nesbox/TIC-80/blob/main/CODE_OF_CONDUCT.md).

Tambien puedes contribuir simplemente revisando o mejorando nuestra [wiki](https://github.com/nesbox/TIC-80/wiki).
La Wiki alberga Documentacion de TIC-80, Fragmentos de codigo, y Tutoriales para el desarrollo de videojuegos.

# Instrucciones de compilado

## Windows
### con Visual Studio 2017
- instala `Visual Studio 2017`
- instala `git`
- instala `Ruby` (puedes usar [RubyInstaller](https://rubyinstaller.org/))
- ejecuta los siguientes comandos en el `cmd`
```
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake -G "Visual Studio 15 2017 Win64" ..
```
- abre `TIC-80.sln` y compilalo
- disfruta :)

### con MinGW
- instala `mingw-w64` (http://mingw-w64.org) y añade `.../mingw/bin` a las *Variables del entorno*
- instala `git`
- instala `cmake` (https://cmake.org)
- instala `Ruby` (puedes usar [RubyInstaller](https://rubyinstaller.org/))
- ejecuta los siguientes comandos con un contexto `mingw64`, por ejemplo con el Shell de MingW64
```
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake -G "MinGW Makefiles" ..
mingw32-make -j4
```

## Linux

### Ubuntu 22.04 (Jammy Jellyfish)

Ejecuta los siguientes comandos desde una terminal:

```
# Nesecario para instalar las ultimas versiones de CMake desde https://apt.kitware.com/
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

Instalar con las [Instrusciones de instalacion](#instrusciones-de-instalacion)


### Ubuntu 24.04 (Noble Numbat)

Ejecuta los siguientes comandos desde una terminal:

```
sudo apt update && sudo apt -y install build-essential cmake git libpipewire-0.3-dev libwayllrubland-dev libsdl2-dev ruby-dev libcurl4-openssl-dev libglvnd-dev libglu1-mesa-dev freeglut3-dev
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake -DBUILD_SDLGPU=On -DBUILD_STUB=On .. --fresh && cmake --build . --parallel
```

Instalar con las [Instrusciones de instalacion](#instrusciones-de-instalacion)


### Arch

Ejecuta los siguientes comandos desde una terminal:
```
sudo pacman -S cmake ruby mesa libglvnd glu
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake ..
make -j4
```

### Fedora 36

Ejecuta los siguientes comandos desde una terminal:
```
sudo dnf -y groupinstall "Development Tools" "Development Libraries"
sudo dnf -y install ruby rubygem-{tk{,-doc},rake,test-unit} cmake libglvnd-devel libglvnd-gles freeglut-devel clang libXext-devel SDL_sound pipewire-devel pipewire-jack-audio-connection-kit-devel pulseaudio-libs-devel
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake .. -DCMAKE_CXX_COMPILER=clang++ -DSDL_ALSA=On
make -j4
```

Instalar con las [Instrusciones de instalacion](#instrusciones-de-instalacion)

### Fedora 40

Ejecuta los siguientes comandos desde una terminal:
```
sudo dnf -y groupinstall "Development Tools" "Development Libraries"
sudo dnf -y install ruby-devel rubygem-rake cmake clang pipewire-devel SDL2-devel SDL2_sound-devel SDL2_gfx-devel wayland-devel libXext-devel pipewire-jack-audio-connection-kit-devel pipewire-jack-audio-connection-kit-devel pulseaudio-libs-devel rubygems-devel libdecor-devel libdrm-devel mesa-libgbm-devel esound-devel freeglut-devel
cmake -DBUILD_SDLGPU=On -DBUILD_STUB=On .. --fresh
cmake --build . --parallel
```

Instalar con las [Instrusciones de instalacion](#instrusciones-de-instalacion)

### Raspberry Pi OS (64-Bit) (Bookworm)

Ejecuta los siguientes comandos desde una terminal:

```
sudo apt update && sudo apt -y install cmake libpipewire-0.3-dev libwayland-dev libsdl2-dev ruby-dev libcurl4-openssl-dev
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake -DBUILD_SDLGPU=On -DBUILD_STUB=On .. --fresh && cmake --build . --parallel 2
```
Instalar con las [Instrusciones de instalacion](#instrusciones-de-instalacion)

### Raspberry Pi (Retropie)

Primero, agrega la repo "jessie-backports" a tu `/etc/apt/sources.list`

`deb [check-valid-until=no] http://archive.debian.org/debian jessie-backports main`

Despues, ejecuta los siguientes comandos desde una terminal:

```
# Claves publicas requiridas:
gpg --keyserver pgpkeys.mit.edu --recv-key  8B48AD6246925553
gpg -a --export 8B48AD6246925553 | sudo apt-key add -
gpg --keyserver pgpkeys.mit.edu --recv-key 7638D0442B90D010
gpg -a --export 7638D0442B90D010 | sudo apt-key add -

# Sistema de actualizaciones:
sudo apt-get update
sudo apt-get dist-upgrade

# Instala el Software
sudo apt-get install git build-essential ruby-full libsdl2-dev zlib1g-dev
sudo apt-get install -t jessie-backports liblua5.3-dev
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake ..
make -j4

# Instala el Software "ubuntu 22.04.3 LTS"
sudo apt-get install git build-essential ruby-full libsdl2-dev zlib1g-dev
sudo apt-get install liblua5.3-dev
sudo apt-get install libcurl4-openssl-dev
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake ..
make -j4
```
Instalar con las [Instrusciones de instalacion](#instrusciones-de-instalacion)

_Nota:_ Si estas utilizando una imagen de Raspberry Pi (no Retropie) talvez no tengas los drivers
de OpenGL habilitados, Ejecuta `sudo raspi-config`, despues selecciona 7 para "Advanced Options",
seguido por 6 para "GL Drivers", y habilita "GL (Fake KMS) Desktop Driver". despues de cambiar esta 
configuracion, reinicia el sistema

## Mac
Instala `Command Line Tools for Xcode` y el administrador de paquetes `brew`

Ejecuta los siguientes comandos desde la terminal:
```
brew install git cmake
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake ..
make -j4
```

para crear el icono de la aplicacion para la version de desarrollo
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
Asegurate de actualizar la direccion absoluta de los binarios de tic-80 en el script, o
actualizar los argumentos de lanzamiento.

## FreeBSD
Ejecuta los siguientes comandos desde la terminal:
```
sudo pkg install gcc git cmake ruby libglvnd libglu freeglut mesa-devel mesa-dri alsa-lib
git clone --recursive https://github.com/nesbox/TIC-80 && cd TIC-80/build
cmake ..
make -j4
```

Mesa busca por swrast_dri.so en el directorio erroneo, estonses tienes que enlazarlo:

```
sudo ln -s /usr/local/lib/dri/swrast_dri.so /usr/local/lib/dri-devel/
```

# Instrucciones de instalacion

## Linux
Para instalarlo, ejecuta `sudo make install -j4`

TIC-80 ahora se puede ser ejecutado con `tic80`

## iOS / tvOS
Puedes encontrar las versiones para iOS/tvOS aqui:
- 0.60.3: https://github.com/brunophilipe/TIC-80
- 0.45.0: https://github.com/CliffsDover/TIC-80

## Creditos

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

# Traduccion de la pagina de TIC-80 de Github al español hecha por:
* SR_MatterNoise - [Instagram @srmatternoisedev](https://www.instagram.com/srmatternoisedev/)
