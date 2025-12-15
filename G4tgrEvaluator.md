## 2025/10/14  - geant4-v10.3.3 file: `G4tgrEvaluator.cc`

> Note: `geant4-v10.3.3` is exactly the third patch `geant4.10.03.p03`, those two files are equivalent

Yesterday [2025/10/14 - Attempt to install WCSim](https://github.com/giuliogiamello/HyperK/blob/main/attempt_install_WCSim.md) I found out that, in order to use `WCSim`, I need to install `Geant4-v10.3.3`. So I tried to install it following [Installation tutorials](https://github.com/giuliogiamello/HyperK/blob/main/installation_tutorials.md): it was working until the `make -j4` command.
This command was interrupted with the error message (using the option `make VERBOSE=1` to get details about the error):

<details>

<summary>expand/collapse</summary>

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

<summary>expand/collapse</summary>

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

<summary>expand/collapse</summary>

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

:arrow_left: [Go back to main HyperK page](https://github.com/giuliogiamello/HyperK?tab=readme-ov-file#hyperk)
