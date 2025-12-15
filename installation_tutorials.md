## Installation tutorials

### Geant4 - Installation tutorial

<details>

<summary>expand/collapse</summary>

**ACHTUNG!**

- If you are planning to use `WCSim`, you should use `Geant4-v10.3.3` and not `Geant4-v11.3.2` (or the last supported version by `WCSim`)
- I wrote this tutorial for `Geant4-v11.3.2`, **so remember to change it every time with specific version you are compiling/installing!** 
- [Geant4 System/Software Prerequisites — Geant4 Installation Guide 10.7 documentation](https://web.archive.org/web/20210220135535/https://geant4-userdoc.web.cern.ch/UsersGuides/InstallationGuide/html/gettingstarted.html)
- [Building and Installing from Source — Geant4 Installation Guide 10.7 documentation](https://web.archive.org/web/20210222000041/https://geant4-userdoc.web.cern.ch/UsersGuides/InstallationGuide/html/installguide.html#buildandinstall)

> Note: `geant4-v10.3.3` is exactly the third patch `geant4.10.03.p03`, those two files are equivalent

---

- [Geant4-11 Tutorial 2: Installation & Testing - YouTube](https://www.youtube.com/watch?v=4DTumUo3IKw&list=PLLybgCU6QCGUYAOwtyI4U8cRL6ig0p3c7)
- [Geant4 Tutorial 1: Installation and Testing of Geant4 - YouTube](https://www.youtube.com/watch?v=Lxb4WZyKeCE&list=PLLybgCU6QCGWgzNYOV0SKen9vqg4KXeVL&index=1)

Open a terminal (suggested in Visual Studio code) and check your system info:

```
lsb_release -a
```

The output is:

```
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 24.04.3 LTS
Release:        24.04
Codename:       noble
```

- Choose a path and create a folder, I did:

```
mkdir geant4Software
```

in `/home/jamal/geant4Software` and move into the new directory `cd geant4Software`.

- Create (inside `geant4Software`) the another folder, I did:

```
mkdir geant4
```

in `/home/jamal/geant4Software/geant4` and move into the new directory `cd geant4`.
This folder (`geant4`) is the one in which you are going to install Geant4, while the `geant4Software` is to install all the other software later and keep them separates.

- Now, go into [Geant4](https://geant4.web.cern.ch/) and download [Download Geant4-11.3.2 - Geant4](https://geant4.web.cern.ch/download/11.3.2.html) (if you want the newest version, at the moment) or [Download Geant4-10.3.3 - Geant4]() (**if you are planning to use** `WCSim`): you need to copy the link of the `Download tar.gz`

(For the next step you need `wget`, if you don't have it: `sudo apt install wget`)

- In a terminal, from inside `/home/jamal/geant4Software/geant4`, use `wget` and then paste the link you copied before, then press enter, it should download the file without any errors

- `Geant4-v11.3.2:`

```
wget https://gitlab.cern.ch/geant4/geant4/-/archive/v11.3.2/geant4-v11.3.2.tar.gz
```

- or `Geant4-v10.3.3`:

```
wget https://gitlab.cern.ch/geant4/geant4/-/archive/v10.3.3/geant4-v10.3.3.tar.gz
```

`ls` output: 
(from now on, I wont write double commands/outputs, **so remember to change it every time with specific version you are compiling/installing!**)

```
jamal@giulio-pc:~/geant4Software/geant4$ ls
geant4-v11.3.2.tar.gz
```

- Install the package with

```
tar xzfv geant4-v11.3.2.tar.gz
```

`ls` output:

```
jamal@giulio-pc:~/geant4Software/geant4$ ls
geant4-v11.3.2  geant4-v11.3.2.tar.gz
```

enter the new folder with `cd geant4-v11.3.2` and again with `ls` output:

```
jamal@giulio-pc:~/geant4Software/geant4/geant4-v11.3.2$ ls
CHANGELOG     cmake           config            environments  LICENSE    README.rst    source
CITATION.cff  CMakeLists.txt  CONTRIBUTING.rst  examples      packaging  ReleaseNotes
```

- Go one folder back with `cd ..` and create a new folder

```
mkdir geant4-v11.3.2-build
```

and access it `cd geant4-v11.3.2-build`.

- Install dependencies with:

```
sudo apt install -y g++ cmake cmake-curses-gui gcc g++ binutils libx11-dev libxpm-dev libxft-dev libxext-dev libexpat1-dev libglew-dev libxmu-dev libjpeg-dev libpng-dev libtiff-dev libgif-dev libxml2-dev libssl-dev libfftw3-dev libqt5core5t64 qt5-qmake qtbase5-dev libqt5opengl5-dev libqt5x11extras5-dev qttools5-dev qttools5-dev-tools libxi-dev libmotif-dev
```

(For the next step you need `cmake`, if you don't have it: `sudo apt install cmake`.
Not needed, but if you want to have a `cmake gui`: `sudo apt install cmake-curses-gui`)

The following steps are for the `cmake gui`

- Open and run the `cmake gui` (form inside `/home/jamal/geant4Software/geant4/geant4-v11.3.2-build`) with:

```
ccmake ../geant4-v11.3.2
```

and, once the gui has been opened, press `c` to start the configuration.
Then press `e` to exit the configuration.
Now activate the following build type moving with arrows and pressing `enter`:

- set the folder in which you want to install Geant4 changing `CMAKE_INSTALL_PREFIX`, pressing `enter` and writing the path to a new folder: `/home/jamal/geant4Software/geant4/geant4-v11.3.2-install`, then press `enter` to confirm
- `GEANT4_BUILD_MULTITHREADED` ---> `ON`
- `GEANT4_INSTALL_DATA` ---> `ON`
- `GEANT4_USE_OPENGL_X11` ---> `ON`
- `GEANT4_USE_QT` ---> `ON`
- `GEANT4_USE_RAYTRACER_X11` ---> `ON`

the final set up looks like this:

```
                                                     Page 1 of 1
 CMAKE_BUILD_TYPE                 Release
 CMAKE_INSTALL_PREFIX             /home/jamal/geant4Software/geant4/geant4-v11.3.2-install
 GEANT4_BUILD_MULTITHREADED       ON
 GEANT4_INSTALL_DATA              ON
 GEANT4_INSTALL_DATADIR
 GEANT4_USE_G3TOG4                OFF
 GEANT4_USE_GDML                  OFF
 GEANT4_USE_INVENTOR              OFF
 GEANT4_USE_INVENTOR_QT           OFF
 GEANT4_USE_OPENGL_X11            ON
 GEANT4_USE_QT                    ON
 GEANT4_USE_RAYTRACER_X11         ON
 GEANT4_USE_SYSTEM_CLHEP          OFF
 GEANT4_USE_SYSTEM_EXPAT          ON
 GEANT4_USE_SYSTEM_ZLIB           OFF
 GEANT4_USE_VTK                   OFF
 GEANT4_USE_XM                    OFF
```

Then press `c` to configure. (If you get an error, probably it's because there is some package missing that you should install).

Repeat to be sure, so press `c`, then `e` to exit and finally press `g` to generate.
Now the `geant4-v11.3.2-build` contains:

```
jamal@giulio-pc:~/geant4Software/geant4/geant4-v11.3.2-build$ ls
BuildProducts             CPackSourceConfig.cmake    G4ModuleInterfaceMap.csv    geant4make.sh                  README.txt
CMakeCache.txt            cxx_filesystem             G4MotifShim.cmake           geant4_module_check.py         source
CMakeCPackOptions.cmake   data                       G4X11Shim.cmake             Geant4PackageCache.cmake       _source_extras
CMakeFiles                Externals                  geant4-config               geant4_validate_sources.cmake  source_package_extras.cmake
cmake_install.cmake       G4EXPATShim.cmake          Geant4Config.cmake          InstallTreeFiles               UseGeant4.cmake
cmake_uninstall.cmake     G4FreetypeShim.cmake       Geant4ConfigVersion.cmake   LICENSE.txt
cmake_uninstall.cmake.in  G4HDF5Shim.cmake           Geant4LibraryDepends.cmake  Makefile
CPackConfig.cmake         G4ModuleAdjacencyList.txt  geant4make.csh              Modules
```

**!!! ACHTUNG !!! ACHTUNG !!! ACHTUNG !!! ACHTUNG !!!** </br>
If you are about to compile `geant4-v10.3.3` for `WCSim`, you need to edit the file `/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc` as explained in [2025/10/14 - geant4-v10.3.3 file: `G4tgrEvaluator.cc`](https://github.com/giuliogiamello/HyperK/blob/main/G4tgrEvaluator.md)

- make the `Makefile` (form inside `/home/jamal/geant4Software/geant4/geant4-v11.3.2-build`) with:

```
make -j4
```

the option `-j4` specifies the number of cores you want to use), this will take some time (avoid pc suspension), note for myself: you can use also `-j8` to speed up a little.

Then write 

```
make install
```

Go one folder back with `cd ..`, in `/home/jamal/geant4Software/geant4` and go in the newly created install folder: `cd geant4-v11.3.2-install`

`ls` output:

```
jamal@giulio-pc:~/geant4Software/geant4/geant4-v11.3.2-install$ ls
bin  include  lib  share
```

move into `cd share/Geant4/geant4make` (`cd share/Geant4-10.3.3/geant4make` if installing `geant4-v10.3.3`) and source the `geant4make.sh` file with:

```
. geant4make.sh
```

this is how to source it manually, to avoid repeating that every time edit `.bashrc`

```
vim /home/jamal/.bashrc 
```

and add the following line in the file:

- `Geant4-v11.3.2:`

```
alias geant4make="source /home/jamal/geant4Software/geant4/geant4-v11.3.2-install/share/Geant4/geant4make/geant4make.sh"
```

- or `Geant4-v10.3.3`:

```
alias geant4make="source /home/jamal/geant4Software/geant4/geant4-v10.3.3-install/share/Geant4-10.3.3/geant4make/geant4make.sh"
```

exit and save vim with `:wq`.

- Close the terminal and open a new one
- Test the alias typing:

```
geant4make
```

there should be no error and the output looks like:

```
jamal@giulio-pc:~$ geant4make 
jamal@giulio-pc:~$ 
```

</details>

#### Geant4 - Installation tutorial Test the installation

<details>

<summary>expand/collapse</summary>

- Test the installation

move to the `/home/jamal/geant4Software/geant4/geant4-v11.3.2-install/share/Geant4/examples/basic/B1` (`/home/jamal/geant4Software/geant4/geant4-v10.3.3-install/share/Geant4-10.3.3/examples/basic/B1/B1` if installing `geant4-v10.3.3`) folder and create the `mkdir build` folder and move into it `cd build` and write:

```
cmake ..
```

- Now a `Makefile` has been created, so,in order to start the compilation, write:

```
make
```

- A new executable `exampleB1` has been created, run it

```
./exampleB1
```

If Geant4 starts, but the visualization is bugged (not working properly) try:

```
XDG_SESSION_TYPE=x11 ./exampleB1
```

as explained in [2025/09/28](https://github.com/giuliogiamello/HyperK/blob/main/2025_09_28.md)

Done!

</details>

### WCSim - Installation tutorial

<details>

<summary>expand/collapse</summary>

**ACHTUNG!**

- You should use `Geant4-v10.3.3` and not `Geant4-v11.3.2` (or the last supported version by `WCSim`)

---

I already have installed Geant4, now I wanna try to install WCSim (that depends on ROOT and Geant4).
I'm following this guide: [Tutorial: How to set up GitHub (in the context of WCSim) · WCSim/WCSim Wiki](https://github.com/WCSim/WCSim/wiki/Tutorial:-How-to-set-up-GitHub-%28in-the-context-of-WCSim%29) and, mostly, [WCSim: Welcome to WCSim](https://hep.lancs.ac.uk/~ajf/WCSim/md__r_e_a_d_m_e.html) and also the instructions in [giuliogiamello/WCSim: The WCSim GEANT4 application](https://github.com/giuliogiamello/WCSim).
I have skipped the `Setting up GitHub and Git` paragraph going directly to `Fork a copy of the WCSim code`.

- create the fork `giuliogiamello/WCSim`: [giuliogiamello/WCSim: The WCSim GEANT4 application](https://github.com/giuliogiamello/WCSim)
- create the folder `WCSim_home`
- move into `WCSim_home` and inside that create `WCSim` and `WCSim_build`
- `git clone` (from inside `/home/jamal`) the forked folder it in my `WCSim_home/WCSim` with:

```
git clone https://github.com/giuliogiamello/WCSim.git WCSim_home/WCSim
```

(Note: you have to specify the folder in which you want to clone it or move directly into that folder before cloning)

- create the folder `mydir` in `WCSim_home/WCSim_build/mydir` and move into it
- "activate" Geant4 with `geant4make`

Compile from inside `WCSim_home/WCSim_build/mydir` with:

```
cmake ../../WCSim
```

```
make clean
```

```
make -j4 install
```

the option `-j4` specifies the number of cores you want to use), this will take some time (avoid pc suspension), note for myself: you can use also `-j8` to speed up a little.

Move into `cd /home/jamal/WCSim_home/WCSim_build/mydir/bin` and source the `this_wcsim.sh` file with:

```
. this_wcsim.sh
```

this is how to source it manually, to avoid repeating that every time edit `.bashrc`

```
vim /home/jamal/.bashrc
```

and add the following line in the file:

```
alias wcsim-make="source /home/jamal/WCSim_home/WCSim_build/mydir/bin/this_wcsim.sh"
```

exit and save vim with `:wq`.

- Close the terminal and open a new one
- Test the alias typing:

```
wcsim-make
```

there should be no error and the output looks like:

```
jamal@giulio-pc:~$ wcsim-make 
jamal@giulio-pc:~$ 
```

- Test the installation: try running the test macro `WCSim.mac`
- Source WCSim with `wcsim-make`
- Source Geant4 with `geant4make` (don't forget!)
- Then move to the build directory `cd /home/jamal/WCSim_home/WCSim_build/mydir` and inside that run:

```
WCSim WCSim.mac macros/tuning_parameters.mac
```

Done!

</details>

:arrow_left: [Go back to main HyperK page](https://github.com/giuliogiamello/HyperK?tab=readme-ov-file#hyperk)
