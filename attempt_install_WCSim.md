## 2025/10/14 - Attempt to install WCSim

(The first attempt was on `2025/10/07`)

**ACHTUNG!**
1. You should use `Geant4-v10.3.3` and not `Geant4-v11.3.2` (or the last supported version by `WCSim`)
2. This section is not my guide on how to install `WCSim`, the guide is [HyperK#WCSim - Installation tutorial](#wcsim---installation-tutorial)

---

On `2025/10/07` I was following [HyperK#WCSim - Installation tutorial](#wcsim---installation-tutorial) and, when running `make -j4 install`, this reported the error:

```
In file included from /home/jamal/WCSim_home/WCSim/src/GdNeutronHPCapture.cc:14:
/home/jamal/WCSim_home/WCSim/include/GdNeutronHPCapture.hh:20:10: fatal error: G4NeutronHPChannel.hh: No such file or directory
   20 | #include "G4NeutronHPChannel.hh"
      |          ^~~~~~~~~~~~~~~~~~~~~~~
compilation terminated.
make[2]: *** [src/CMakeFiles/WCSimCore.dir/build.make:132: src/CMakeFiles/WCSimCore.dir/GdNeutronHPCapture.cc.o] Error 1
make[2]: *** Waiting for unfinished jobs....
make[1]: *** [CMakeFiles/Makefile2:130: src/CMakeFiles/WCSimCore.dir/all] Error 2
make: *** [Makefile:136: all] Error 2
```

So, I realized that `G4NeutronHPChannel.hh`is defined in Geant4.10, but not in Geant4.11 !!! (See: [Geant4.10: G4NeutronHPChannel Class Reference](https://apc.u-paris.fr/~franco/g4doxy4.10/html/class_g4_neutron_h_p_channel.html) and [Geant4-11: source/processes/hadronic/models/particle_hp/include/G4NeutronHPChannel.hh File Reference](https://apc.u-paris.fr/~franco/g4doxy4.11/html/G4NeutronHPChannel_8hh.html)). In Geant4.11 it was included in `G4NeutronHPChannel = G4ParticleHPChannel`, so with a different name.
I realized that this was only one of the many mismatching names in the compilation procedure, then I discovered that:

> in [giuliogiamello/WCSim: The WCSim GEANT4 application](https://github.com/giuliogiamello/WCSim?tab=readme-ov-file#dependencies) in explicitly says:

```
Geant
If using a newer version of Geant, it is your responsiblity to assess whether Geant physics changes are significant, relative to the officially supported 4.10.3.3
```

So I should have used `Geant4-v10.3.3` and not `Geant4-v11.3.2` !!!

Today (`2025/10/14`), I installed `Geant4-v10.3.3` and repeated the same procedure from [[HyperK#WCSim - Installation tutorial]] and the command `make -j4 install` worked correctly.

:arrow_left: [Go back to main HyperK page](https://github.com/giuliogiamello/HyperK?tab=readme-ov-file#hyperk)
