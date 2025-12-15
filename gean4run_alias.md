## 2025/10/31 - `gean4run` alias

I edited `.bashrc` adding a new alias `geant4run`:

```bash
# 2025-10-31: Geant4 run simulation with specific options
geant4run() {
    if [ $# -eq 0 ]; then
        echo "Usage: geant4run <executable_name>"
        echo "Example: geant4run sim"
        return 1
    fi
    LIBGL_ALWAYS_SOFTWARE=1 XDG_SESSION_TYPE=x11 ./"$1"
}

```

- `LIBGL_ALWAYS_SOFTWARE=1`: Forces OpenGL to use software rendering (CPU) instead of hardware acceleration
- `XDG_SESSION_TYPE=x11`: Forces the application to use X11 instead of Wayland

this is because otherwise Geant4 UI is bugged and not working.

:arrow_left: [Go back to main HyperK page](https://github.com/giuliogiamello/HyperK?tab=readme-ov-file#hyperk)
