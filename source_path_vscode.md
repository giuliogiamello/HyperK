## 2025/11/27 Geant4 source `PATH` in VSCode

If in VSCode you are editing a file (e.g. a `.cc` file) and when you are `#include "SOMETHING.hh"` it says:

```bash
cannot open source file "SOMETHING.hh" (dependency of "SOMETHING.hh")
```

It means you have to source the path of your Geant4 installation.
To do so:

- Highlight the red mistake error line and click on `Quick Fix... (Ctrl+.)`
- Go to the section named `Include path` and add your line below the ones already there, like this:

```bash
${workspaceFolder}/**
/home/jamal/geant4Software/geant4/geant4-v10.3.3-install/include/Geant4
```

- Done

Reference: [Geant4-11 Tutorial 3: Starting First Project - YouTube](https://www.youtube.com/watch?v=xpHeGwHqyzQ)

:arrow_left: [Go back to main HyperK page](https://github.com/giuliogiamello/HyperK?tab=readme-ov-file#hyperk)
