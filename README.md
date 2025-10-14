# HyperK

Last update `2025/10/14`

> To source and activate Geant4: `geant4make`; </br>
> To source and activate WCSim: `wcsim-make`; </br>
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
```

## Links and web-guides 

<details>

<summary>Expand</summary>

### Geant4

- [Geant4](https://geant4.web.cern.ch/)
- [Geant4-11 Tutorials - YouTube](https://www.youtube.com/playlist?list=PLLybgCU6QCGUYAOwtyI4U8cRL6ig0p3c7)
- [Geant4 Tutorials - YouTube](https://www.youtube.com/playlist?list=PLLybgCU6QCGWgzNYOV0SKen9vqg4KXeVL)
- [Overview | geant4.web.cern.ch](https://geant4-internal.web.cern.ch/)
- [User Documentation | geant4.web.cern.ch](https://geant4-internal.web.cern.ch/support/user_documentation)
- [Geant4 examples: Geant4 Examples](https://geant4-userdoc.web.cern.ch/Doxygen/examples_doc/html/index.html)
- [Advanced Examples - Geant4](https://geant4.web.cern.ch/docs/advanced_examples_doc/index)
- [Search: geant · CDS Videos · CERN](https://videos.cern.ch/search?page=1&size=21&q=geant)
- [Geant4 Beginner Course — Geant4 Beginner Course documentation](https://geant4-beginner-course.readthedocs.io/en/latest/index.html)
- [Geant4 tutorials | home](https://jeffersonlab.github.io/g4home/tutorials/)
- [Overview of Users Documents](https://conferences.fnal.gov/g4tutorial/g4cd/Documentation/Geant4/index.html)
- [jintonic/geant4: Geant4 tutorials](https://github.com/jintonic/geant4?tab=readme-ov-file)

#### Geant4-v10.3.3

- [Software Download Archive | geant4.web.cern.ch](https://geant4-internal.web.cern.ch/support/download_archive?page=5)
- [geant4-data.web.cern.ch/ReleaseNotes/Patch4.10.3-3.txt](https://geant4-data.web.cern.ch/ReleaseNotes/Patch4.10.3-3.txt)
- [Geant4 10.3 Release Notes](https://geant4-data.web.cern.ch/ReleaseNotes/ReleaseNotes4.10.3.html)
- [Installation of G4.10.6.3 fails on ubuntu22.04 - Getting Started - Geant4 Forum](https://geant4-forum.web.cern.ch/t/installation-of-g4-10-6-3-fails-on-ubuntu22-04/11303)
- [Error while installing GEANT4 in ubuntu 22.04.2 LTS - Getting Started - Geant4 Forum](https://geant4-forum.web.cern.ch/t/error-while-installing-geant4-in-ubuntu-22-04-2-lts/10896/7)
- [How to install a patch？ - Getting Started - Geant4 Forum](https://geant4-forum.web.cern.ch/t/how-to-install-a-patch/6650)

### WCSim

- [Home · WCSim/WCSim Wiki](https://github.com/WCSim/WCSim/wiki)
- [The Water Cherenkov Simulator](https://github.com/WCSim)
- [Tutorial: How to set up GitHub (in the context of WCSim) · WCSim/WCSim Wiki](https://github.com/WCSim/WCSim/wiki/Tutorial:-How-to-set-up-GitHub-%28in-the-context-of-WCSim%29)
- [GitHub - WCSim/WCSim: The WCSim GEANT4 application](https://github.com/WCSim/WCSim)
- [WCSim: Welcome to WCSim](https://hep.lancs.ac.uk/~ajf/WCSim/md__r_e_a_d_m_e.html)
- [gondiaz/WCSimFQTuningTools](https://github.com/gondiaz/WCSimFQTuningTools)
- [giuliogiamello/WCSim: The WCSim GEANT4 application](https://github.com/giuliogiamello/WCSim)

### Miscellanea

- [felix-cormier/HK_ML_tutorial: tutorials, scripts, classes and more for the HK ML tutorial](https://github.com/felix-cormier/HK_ML_tutorial)
- [Kamioka Observatory, ICRR, The University of Tokyo](https://www-sk.icrr.u-tokyo.ac.jp/en/)
- [Physics | Hyper-Kamiokande](https://www-sk.icrr.u-tokyo.ac.jp/en/hk/about/research/)
- [[Press Release] Excavation of the Colossal Cavern for Hyper-Kamiokande Completed | Kamioka Observatory, ICRR, The University of Tokyo](https://www-sk.icrr.u-tokyo.ac.jp/en/news/detail/1006)
- [Kamioka Observatory - Wikipedia](https://en.wikipedia.org/wiki/Kamioka_Observatory)
- [The Hyper-Kamiokande Experiment - Francesca Di Lodovico (King's College London) - YouTube](https://www.youtube.com/watch?v=Tk03dBzf56E)

</details>

## 2025/10/14  - geant4-v10.3.3 file: `G4tgrEvaluator.cc`

Yesterday [HyperK#2025/10/14 - Attempt to install WCSim](#20251014----attempt-to-install-wcsim) I found out that, in order to use `WCSim`, I need to install `Geant4-v10.3.3`. So I tried to install it following [HyperK#Geant4 - Installation tutorial](#geant4---installation-tutorial): it was working until the `make -j4` command.
This command was interrupted with the error message (using the option `make VERBOSE=1` to get details about the error):

<details>
   
```
[ 86%] Building CXX object source/persistency/CMakeFiles/G4persistency.dir/ascii/src/G4tgrEvaluator.cc.o
cd /home/jamal/geant4Software/geant4/geant4-v10.3.3-build/source/persistency && /usr/bin/g++-11 -DG4MULTITHREADED -DG4VERBOSE -DG4_STORE_TRAJECTORY -DG4persistency_EXPORTS -DGEANT4_DEVELOPER_Release -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/clhep/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/geometry/divisions/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/geometry/management/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/geometry/solids/Boolean/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/geometry/solids/CSG/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/geometry/solids/specific/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/geometry/volumes/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/HEPGeometry/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/HEPNumerics/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/HEPRandom/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/management/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/graphics_reps/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/intercoms/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/materials/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/particles/management/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/digits_hits/digits/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/digits_hits/hits/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/event/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/run/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/track/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/tracking/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/mctruth/include -I/home/jamal/geant4Software/geant4/geant4-v10.3.3-build/source/externals/zlib -I/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/zlib/include -W -Wall -pedantic -Wno-non-virtual-dtor -Wno-long-long -Wwrite-strings -Wpointer-arith -Woverloaded-virtual -Wno-variadic-macros -Wshadow -pipe -DG4USE_STD11 -pthread -ftls-model=initial-exec -O3 -DNDEBUG -fno-trapping-math -ftree-vectorize -fno-math-errno -fPIC -MD -MT source/persistency/CMakeFiles/G4persistency.dir/ascii/src/G4tgrEvaluator.cc.o -MF CMakeFiles/G4persistency.dir/ascii/src/G4tgrEvaluator.cc.o.d -o CMakeFiles/G4persistency.dir/ascii/src/G4tgrEvaluator.cc.o -c /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:80:10: error: ambiguating new declaration of ‘G4double fsqrt(G4double)’
   80 | G4double fsqrt( G4double arg ){  return std::sqrt(arg); }
      |          ^~~~~
In file included from /usr/include/c++/11/cmath:45,
                 from /usr/include/c++/11/complex:44,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/management/include/G4Types.hh:67,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/management/include/G4ios.hh:39,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/management/include/globals.hh:49,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/management/include/G4ThreeVector.hh:39,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/include/G4tgrEvaluator.hh:43,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:36:
/usr/include/x86_64-linux-gnu/bits/mathcalls-narrow.h:36:20: note: old declaration ‘float fsqrt(double)’
   36 | __MATHCALL_NARROW (__MATHCALL_NAME (sqrt), __MATHCALL_REDIR_NAME2 (sqrt), 1);
      |                    ^~~~~~~~~~~~~~~
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc: In member function ‘void G4tgrEvaluator::AddCommonFunctions()’:
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:103:14: error: no matching function for call to ‘setFunction(const char [5], float (&)(double) noexcept)’
  103 |   setFunction("sqrt", (*fsqrt));
      |   ~~~~~~~~~~~^~~~~~~~~~~~~~~~~~
In file included from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/management/include/G4Evaluator.hh:40,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/include/G4tgrEvaluator.hh:44,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:36:
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/clhep/include/CLHEP/Evaluator/Evaluator.h:126:8: note: candidate: ‘void HepTool::Evaluator::setFunction(const char*, double (*)())’ (near match)
  126 |   void setFunction(const char * name, double (*fun)());
      |        ^~~~~~~~~~~
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/clhep/include/CLHEP/Evaluator/Evaluator.h:126:8: note:   conversion of argument 2 would be ill-formed:
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:103:24: error: invalid conversion from ‘float (*)(double) noexcept’ to ‘double (*)()’ [-fpermissive]
  103 |   setFunction("sqrt", (*fsqrt));
      |                       ~^~~~~~~
      |                        |
      |                        float (*)(double) noexcept
In file included from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/management/include/G4Evaluator.hh:40,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/include/G4tgrEvaluator.hh:44,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:36:
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/clhep/include/CLHEP/Evaluator/Evaluator.h:136:8: note: candidate: ‘void HepTool::Evaluator::setFunction(const char*, double (*)(double))’ (near match)
  136 |   void setFunction(const char * name, double (*fun)(double));
      |        ^~~~~~~~~~~
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/clhep/include/CLHEP/Evaluator/Evaluator.h:136:8: note:   conversion of argument 2 would be ill-formed:
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:103:24: error: invalid conversion from ‘float (*)(double) noexcept’ to ‘double (*)(double)’ [-fpermissive]
  103 |   setFunction("sqrt", (*fsqrt));
      |                       ~^~~~~~~
      |                        |
      |                        float (*)(double) noexcept
In file included from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/management/include/G4Evaluator.hh:40,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/include/G4tgrEvaluator.hh:44,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:36:
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/clhep/include/CLHEP/Evaluator/Evaluator.h:146:8: note: candidate: ‘void HepTool::Evaluator::setFunction(const char*, double (*)(double, double))’ (near match)
  146 |   void setFunction(const char * name, double (*fun)(double,double));
      |        ^~~~~~~~~~~
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/clhep/include/CLHEP/Evaluator/Evaluator.h:146:8: note:   conversion of argument 2 would be ill-formed:
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:103:24: error: invalid conversion from ‘float (*)(double) noexcept’ to ‘double (*)(double, double)’ [-fpermissive]
  103 |   setFunction("sqrt", (*fsqrt));
      |                       ~^~~~~~~
      |                        |
      |                        float (*)(double) noexcept
In file included from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/management/include/G4Evaluator.hh:40,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/include/G4tgrEvaluator.hh:44,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:36:
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/clhep/include/CLHEP/Evaluator/Evaluator.h:156:8: note: candidate: ‘void HepTool::Evaluator::setFunction(const char*, double (*)(double, double, double))’ (near match)
  156 |   void setFunction(const char * name, double (*fun)(double,double,double));
      |        ^~~~~~~~~~~
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/clhep/include/CLHEP/Evaluator/Evaluator.h:156:8: note:   conversion of argument 2 would be ill-formed:
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:103:24: error: invalid conversion from ‘float (*)(double) noexcept’ to ‘double (*)(double, double, double)’ [-fpermissive]
  103 |   setFunction("sqrt", (*fsqrt));
      |                       ~^~~~~~~
      |                        |
      |                        float (*)(double) noexcept
In file included from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/management/include/G4Evaluator.hh:40,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/include/G4tgrEvaluator.hh:44,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:36:
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/clhep/include/CLHEP/Evaluator/Evaluator.h:166:8: note: candidate: ‘void HepTool::Evaluator::setFunction(const char*, double (*)(double, double, double, double))’ (near match)
  166 |   void setFunction(const char * name,
      |        ^~~~~~~~~~~
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/clhep/include/CLHEP/Evaluator/Evaluator.h:166:8: note:   conversion of argument 2 would be ill-formed:
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:103:24: error: invalid conversion from ‘float (*)(double) noexcept’ to ‘double (*)(double, double, double, double)’ [-fpermissive]
  103 |   setFunction("sqrt", (*fsqrt));
      |                       ~^~~~~~~
      |                        |
      |                        float (*)(double) noexcept
In file included from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/global/management/include/G4Evaluator.hh:40,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/include/G4tgrEvaluator.hh:44,
                 from /home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:36:
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/clhep/include/CLHEP/Evaluator/Evaluator.h:177:8: note: candidate: ‘void HepTool::Evaluator::setFunction(const char*, double (*)(double, double, double, double, double))’ (near match)
  177 |   void setFunction(const char * name,
      |        ^~~~~~~~~~~
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/externals/clhep/include/CLHEP/Evaluator/Evaluator.h:177:8: note:   conversion of argument 2 would be ill-formed:
/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc:103:24: error: invalid conversion from ‘float (*)(double) noexcept’ to ‘double (*)(double, double, double, double, double)’ [-fpermissive]
  103 |   setFunction("sqrt", (*fsqrt));
      |                       ~^~~~~~~
      |                        |
      |                        float (*)(double) noexcept
make[2]: *** [source/persistency/CMakeFiles/G4persistency.dir/build.make:398: source/persistency/CMakeFiles/G4persistency.dir/ascii/src/G4tgrEvaluator.cc.o] Error 1
make[2]: Leaving directory '/home/jamal/geant4Software/geant4/geant4-v10.3.3-build'
make[1]: *** [CMakeFiles/Makefile2:3814: source/persistency/CMakeFiles/G4persistency.dir/all] Error 2
make[1]: Leaving directory '/home/jamal/geant4Software/geant4/geant4-v10.3.3-build'
make: *** [Makefile:156: all] Error 2
```

</details>

The problem was because Geant4 was trying to define the function `fsqrt`, but this name was already used by c++ ---> conflict definitions!

The original file `/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc` was:

<details>

```
//
// ********************************************************************
// * License and Disclaimer                                           *
// *                                                                  *
// * The  Geant4 software  is  copyright of the Copyright Holders  of *
// * the Geant4 Collaboration.  It is provided  under  the terms  and *
// * conditions of the Geant4 Software License,  included in the file *
// * LICENSE and available at  http://cern.ch/geant4/license .  These *
// * include a list of copyright holders.                             *
// *                                                                  *
// * Neither the authors of this software system, nor their employing *
// * institutes,nor the agencies providing financial support for this *
// * work  make  any representation or  warranty, express or implied, *
// * regarding  this  software system or assume any liability for its *
// * use.  Please see the license in the file  LICENSE  and URL above *
// * for the full disclaimer and the limitation of liability.         *
// *                                                                  *
// * This  code  implementation is the result of  the  scientific and *
// * technical work of the GEANT4 collaboration.                      *
// * By using,  copying,  modifying or  distributing the software (or *
// * any work based  on the software)  you  agree  to acknowledge its *
// * use  in  resulting  scientific  publications,  and indicate your *
// * acceptance of all terms of the Geant4 Software license.          *
// ********************************************************************
//
//
// $Id: G4tgrEvaluator.cc 66363 2012-12-18 09:12:54Z gcosmo $
//
//
// class G4tgrEvaluator

// History:
// - Created.                                 P.Arce, CIEMAT (November 2007)
// -------------------------------------------------------------------------

#include "G4tgrEvaluator.hh"

#include <cmath>

// -------------------------------------------------------------------------
G4tgrEvaluator::G4tgrEvaluator()
{
  AddCommonFunctions();
}


// -------------------------------------------------------------------------
G4tgrEvaluator::~G4tgrEvaluator()
{
}


// -------------------------------------------------------------------------
void G4tgrEvaluator::print_error( G4int estatus ) const
{
  switch (estatus)
  {
    case ERROR_SYNTAX_ERROR:
      G4cerr << "G4tgrEvaluator: syntax error!" << G4endl;
      return;
    default:
      G4Evaluator::print_error();    
    return;
  }
} 
 
G4double fsin( G4double arg ){  return std::sin(arg); }
G4double fcos( G4double arg ){  return std::cos(arg); }
G4double ftan( G4double arg ){  return std::tan(arg); }
G4double fasin( G4double arg ){  return std::asin(arg); }
G4double facos( G4double arg ){  return std::acos(arg); }
G4double fatan( G4double arg ){  return std::atan(arg); }
G4double fatan2( G4double arg1, G4double arg2 ){ return std::atan2(arg1,arg2); }
G4double fsinh( G4double arg ){  return std::sinh(arg); }
G4double fcosh( G4double arg ){  return std::cosh(arg); }
G4double ftanh( G4double arg ){  return std::tanh(arg); }
// G4double fasinh( G4double arg ){  return std::asinh(arg); }
// G4double facosh( G4double arg ){  return std::acosh(arg); }
// G4double fatanh( G4double arg ){  return std::atanh(arg); }
G4double fsqrt( G4double arg ){  return std::sqrt(arg); }
G4double fexp( G4double arg ){  return std::exp(arg); }
G4double flog( G4double arg ){  return std::log(arg); }
G4double flog10( G4double arg ){  return std::log10(arg); }
G4double fpow( G4double arg1, G4double arg2 ){  return std::pow(arg1,arg2); }


//--------------------------------------------------------------------
void G4tgrEvaluator::AddCommonFunctions()
{
  setFunction("sin", (*fsin));
  setFunction("cos", (*fcos));
  setFunction("tan", (*ftan));
  setFunction("asin", (*fasin));
  setFunction("acos", (*facos));
  setFunction("atan", (*fatan));
  setFunction("atan2", (*fatan2));
  setFunction("sinh", (*fsinh));
  setFunction("cosh", (*fcosh));
  setFunction("tanh", (*ftanh));
//  setFunction("asinh", (*fasinh));
//  setFunction("acosh", (*facosh));
//  setFunction("atanh", (*fatanh));
  setFunction("sqrt", (*fsqrt));
  setFunction("exp", (*fexp));
  setFunction("log", (*flog));
  setFunction("log10", (*flog10));
  setFunction("pow", (*fpow));
}
```

</details>

I edited (as suggested at the bottom of [2444 – Geant4 10.7.2 fails to build from sources with GCC 11.2.1 on Fedora.](https://bugzilla-geant4.kek.jp/show_bug.cgi?id=2444)):

- line 80: `G4double fsqrt( G4double arg ){  return std::sqrt(arg); }` --> `G4double fltsqrt( G4double arg ){  return std::sqrt(arg); }`
- line 103: `setFunction("sqrt", (*fsqrt));` --> `setFunction("sqrt", (*fltsqrt));`

the modified version is:

<details>

```
//
// ********************************************************************
// * License and Disclaimer                                           *
// *                                                                  *
// * The  Geant4 software  is  copyright of the Copyright Holders  of *
// * the Geant4 Collaboration.  It is provided  under  the terms  and *
// * conditions of the Geant4 Software License,  included in the file *
// * LICENSE and available at  http://cern.ch/geant4/license .  These *
// * include a list of copyright holders.                             *
// *                                                                  *
// * Neither the authors of this software system, nor their employing *
// * institutes,nor the agencies providing financial support for this *
// * work  make  any representation or  warranty, express or implied, *
// * regarding  this  software system or assume any liability for its *
// * use.  Please see the license in the file  LICENSE  and URL above *
// * for the full disclaimer and the limitation of liability.         *
// *                                                                  *
// * This  code  implementation is the result of  the  scientific and *
// * technical work of the GEANT4 collaboration.                      *
// * By using,  copying,  modifying or  distributing the software (or *
// * any work based  on the software)  you  agree  to acknowledge its *
// * use  in  resulting  scientific  publications,  and indicate your *
// * acceptance of all terms of the Geant4 Software license.          *
// ********************************************************************
//
//
// $Id: G4tgrEvaluator.cc 66363 2012-12-18 09:12:54Z gcosmo $
//
//
// class G4tgrEvaluator

// History:
// - Created.                                 P.Arce, CIEMAT (November 2007)
// -------------------------------------------------------------------------

#include "G4tgrEvaluator.hh"

#include <cmath>

// -------------------------------------------------------------------------
G4tgrEvaluator::G4tgrEvaluator()
{
  AddCommonFunctions();
}


// -------------------------------------------------------------------------
G4tgrEvaluator::~G4tgrEvaluator()
{
}


// -------------------------------------------------------------------------
void G4tgrEvaluator::print_error( G4int estatus ) const
{
  switch (estatus)
  {
    case ERROR_SYNTAX_ERROR:
      G4cerr << "G4tgrEvaluator: syntax error!" << G4endl;
      return;
    default:
      G4Evaluator::print_error();    
    return;
  }
} 
 
G4double fsin( G4double arg ){  return std::sin(arg); }
G4double fcos( G4double arg ){  return std::cos(arg); }
G4double ftan( G4double arg ){  return std::tan(arg); }
G4double fasin( G4double arg ){  return std::asin(arg); }
G4double facos( G4double arg ){  return std::acos(arg); }
G4double fatan( G4double arg ){  return std::atan(arg); }
G4double fatan2( G4double arg1, G4double arg2 ){ return std::atan2(arg1,arg2); }
G4double fsinh( G4double arg ){  return std::sinh(arg); }
G4double fcosh( G4double arg ){  return std::cosh(arg); }
G4double ftanh( G4double arg ){  return std::tanh(arg); }
// G4double fasinh( G4double arg ){  return std::asinh(arg); }
// G4double facosh( G4double arg ){  return std::acosh(arg); }
// G4double fatanh( G4double arg ){  return std::atanh(arg); }
G4double fltsqrt( G4double arg ){  return std::sqrt(arg); }
G4double fexp( G4double arg ){  return std::exp(arg); }
G4double flog( G4double arg ){  return std::log(arg); }
G4double flog10( G4double arg ){  return std::log10(arg); }
G4double fpow( G4double arg1, G4double arg2 ){  return std::pow(arg1,arg2); }


//--------------------------------------------------------------------
void G4tgrEvaluator::AddCommonFunctions()
{
  setFunction("sin", (*fsin));
  setFunction("cos", (*fcos));
  setFunction("tan", (*ftan));
  setFunction("asin", (*fasin));
  setFunction("acos", (*facos));
  setFunction("atan", (*fatan));
  setFunction("atan2", (*fatan2));
  setFunction("sinh", (*fsinh));
  setFunction("cosh", (*fcosh));
  setFunction("tanh", (*ftanh));
//  setFunction("asinh", (*fasinh));
//  setFunction("acosh", (*facosh));
//  setFunction("atanh", (*fatanh));
  setFunction("sqrt", (*fltsqrt));
  setFunction("exp", (*fexp));
  setFunction("log", (*flog));
  setFunction("log10", (*flog10));
  setFunction("pow", (*fpow));
}

```

</details>

## 2025/10/14  - Attempt to install WCSim

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

## 2025/09/28

- [Black Screen when running Example1 - Getting Started - Geant4 Forum](https://geant4-forum.web.cern.ch/t/black-screen-when-running-example1/14106/2)
- [Geant4 OGL visualiztion in Ubuntu 23.04 - Recording, Visualizing and Persisting Data - Geant4 Forum](https://geant4-forum.web.cern.ch/t/geant4-ogl-visualiztion-in-ubuntu-23-04/11025/4)
- [Wayland does not support QWindow::requestActivate() · Issue #288 · githubuser0xFFFF/Qt-Advanced-Docking-System](https://github.com/githubuser0xFFFF/Qt-Advanced-Docking-System/issues/288#issuecomment-752790439)

```
XDG_SESSION_TYPE=x11 ./NAME_EXECUTABLE
```

## Installation tutorials

### Geant4 - Installation tutorial

**ACHTUNG!**
- If you are planning to use `WCSim`, you should use `Geant4-v10.3.3` and not `Geant4-v11.3.2` (or the last supported version by `WCSim`)
- I wrote this tutorial for `Geant4-v11.3.2`, **so remember to change it every time with specific version you are compiling/installing!** 
- [Geant4 System/Software Prerequisites — Geant4 Installation Guide 10.7 documentation](https://web.archive.org/web/20210220135535/https://geant4-userdoc.web.cern.ch/UsersGuides/InstallationGuide/html/gettingstarted.html)
- [Building and Installing from Source — Geant4 Installation Guide 10.7 documentation](https://web.archive.org/web/20210222000041/https://geant4-userdoc.web.cern.ch/UsersGuides/InstallationGuide/html/installguide.html#buildandinstall)

---

- [Geant4-11 Tutorial 2: Installation & Testing - YouTube](https://www.youtube.com/watch?v=4DTumUo3IKw&list=PLLybgCU6QCGUYAOwtyI4U8cRL6ig0p3c7)
- [Geant4 Tutorial 1: Installation and Testing of Geant4 - YouTube](https://www.youtube.com/watch?v=Lxb4WZyKeCE&list=PLLybgCU6QCGWgzNYOV0SKen9vqg4KXeVL&index=1)

- Open a terminal (suggested in Visual Studio code) and check your system info:

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
If you are about to compile `geant4-v10.3.3` for `WCSim`, you need to edit the file `/home/jamal/geant4Software/geant4/geant4-v10.3.3/source/persistency/ascii/src/G4tgrEvaluator.cc` as explained in [HyperK#2025/10/14 - geant4-v10.3.3 file `G4tgrEvaluator.cc`](#20251014----geant4-v1033-file-g4tgrevaluatorcc)

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

as explained in [HyperK#2025/09/28](#20250928)

Done!

### WCSim - Installation tutorial

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
