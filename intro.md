## Intro

> To source and activate Geant4: `geant4make`; </br>
> To source and activate WCSim: `wcsim-make`; </br>
> To source and activate fiTQun: `fitqun-make`; </br>
> From what I understood ROOT is sourced automatically at every login (as written at the end of the installation guide in [giuliogiamello/Cern-ROOT](https://github.com/giuliogiamello/Cern-ROOT)).

The lines I added in `.bashrc`:

```
# 2025-10-04: alias for python
alias python='python3'

# 2025-10-09: to source ROOT setup automatically at each login 
. ~/root_home/root_install/bin/thisroot.sh

# 2025-10-14: alias for Geant4-v10.3.3
alias geant4make="source /home/jamal/geant4Software/geant4/geant4-v10.3.3-install/share/Geant4-10.3.3/geant4make/geant4make.sh"

# 2025-10-14: alias for WCSim
alias wcsim-make="source /home/jamal/WCSim_home/WCSim_build/mydir/bin/this_wcsim.sh"

# 2026-02-09: alias for fiTQun
alias fitqun-make="source /home/jamal/fiTQun/install/bin/this_fitqun.sh"
```

:arrow_left: [Go back to main HyperK page](https://github.com/giuliogiamello/HyperK?tab=readme-ov-file#hyperk)
