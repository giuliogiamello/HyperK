## Tips

> [!WARNING]
> Before building a geant4 executable **remember** to:
> 
> - Create a `build` directory: `mkdir build`
> - Move into it: `cd build`
> 
> Only from there build the project with:
> 
> - `cmake ..`
> - `make`
> 
> Finally run the executable just created inside the `build` dir with:
> 
> - `./executable`
> 
> As explained in [Geant4 - Installation tutorial: Test the installation](https://github.com/giuliogiamello/HyperK/blob/main/installation_tutorials.md#geant4---installation-tutorial-test-the-installation)

> [!TIP]
> If Geant4 starts, but the visualization is bugged (not working properly) try:
> 
> ```bash
> XDG_SESSION_TYPE=x11 ./executable
> ```
> 
> or
> 
> ```bash
> LIBGL_ALWAYS_SOFTWARE=1 XDG_SESSION_TYPE=x11 ./executable
> ```
> 
> as explained in [2025/09/28](https://github.com/giuliogiamello/HyperK/blob/main/2025_09_28.md)

- `LIBGL_ALWAYS_SOFTWARE=1`: Forces OpenGL to use software rendering (CPU) instead of hardware acceleration
- `XDG_SESSION_TYPE=x11`: Forces the application to use X11 instead of Wayland

> [!NOTE]
> I edited my `.bashrc` to not have to run every time the long line and I added the alias `geant4run` (See [2025/10/31 - `gean4run` alias](https://github.com/giuliogiamello/HyperK/blob/main/gean4run_alias.md))

> [!TIP] 
> I created a **shared folder** btw my pc and GHOST container using this command:
> 
> ```bash
> docker run -it -v /home/jamal/jamal_ghost:/my_code --name=ghost registry.git.hyperk.org/hyperk/externals/wcsim:v1.12.29
> ```

> [!TIP] 
> To jump back in the container:
> 
> ```bash
> docker start -i ghost
> ```

 > [!TIP]
> To close a docker container: `Ctrl`+`d`

> [!TIP]
> Cleaning is useful (and should be the first thing to try when things don't compile, or don't run as expected)
> 
> ```bash
> hkp clean --build --install hk-DataModel
> ```
> ```bash
> hkp clean --build --install GHOST-WCSim
> ```
> ```bash
> hkp clean --build --install hk-ToolApp
> ```

> [!TIP]
> When recompiling in the future future, ensure to use this order
> 
> ```bash
> hkp install hk-DataModel
> ```
> ```bash
> hkp install GHOST-WCSim
> ```
> ```bash
> hkp install hk-ToolApp
> ```

:arrow_left: [Go back to main HyperK page](https://github.com/giuliogiamello/HyperK?tab=readme-ov-file#hyperk)
