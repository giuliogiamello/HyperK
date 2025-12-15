## 2025/11/27 Geant4 CMake Deprecation Warning

Read the commented text in the code block below.

- `/home/jamal/geant4Software/geant4/geant4-v10.3.3-install/share/Geant4-10.3.3/examples/basic/CMakeLists.txt`

```txt file:CMakeLists.txt
#------------------------------- Jamal: 2025/11/27 -------------------------------#
# The original line one the one below
#
# cmake_minimum_required(VERSION 2.6 FATAL_ERROR)
#
# it can be also retrived from geant4-10.3 release:
# https://github.com/Geant4/geant4/blob/geant4-10.3-release/examples/basic/CMakeLists.txt
# 
# Since using the minimum
# requirements of 'VERSION 2.6' was giving me the following warning:
#
# CMake Deprecation Warning at CMakeLists.txt:5 (cmake_minimum_required):
#   Compatibility with CMake < 3.5 will be removed from a future version of
#   CMake.
#
#   Update the VERSION argument <min> value or use a ...<max> suffix to tell
#   CMake that the project does not need compatibility with older versions.
#
# I have decided to modify it using the line geant4-11.3 release:
# https://github.com/Geant4/geant4/blob/geant4-11.3-release/examples/basic/CMakeLists.txt
#---------------------------------------------------------------------------------#

cmake_minimum_required(VERSION 3.16...3.27)
```

:arrow_left: [Go back to main HyperK page](https://github.com/giuliogiamello/HyperK?tab=readme-ov-file#hyperk)
