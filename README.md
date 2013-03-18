NAME: GMP

VERSION: .01  

AUTHOR: Felix

AUTHOR_EMAIL: 

PKG_URL: https://github.com/mmaul/gmp

DESCRIPTION: GNU GMP bindings for felix language

CATEGORY: math

LIBDIR: GMP

LICENSE: FFAU
-----
Quickstart SetupTool application template for a generic library.

## Quickstart Installation ##
* 'install' must be able to write to Felix INSTALL_ROOT

    scoop get gmp
    scoop build gmp
    scoop install gmp

## Documentation ##
See GMP/gmp.flx

### Quick Example ###
    include "GMP/gmp";
    open Gmp;
    fun fact(n:int) = {
      var p = mpz_of_int n;
      for var i in 1 upto (n - 1) do
        p = p * mpz_of_int i;
      done
      return p;
    }
    match System::args() with
    |Cons(_,Cons(?n,_)) => println$ n + "! = " + str(fact(int(n)));
    |_ => println$ "fact <n>";
    endmatch;


     flx examples/fact 109
109! = 144385958320249358220488210246279753379312820313396029159834075622223337844983482099636001195615259277084033387619818092804737714758384244334160217374720000000000000000000000000

## License ##
THIS WRAPPER IS FFAU .. it is NOT LGPL licenced
This is because the wrapper was hand written from
scratch .. it was NOT derived from any LGPL headers
Code LINKED against libgmp, however, may be governed
by the LGPL licence, since the object files ARE
derived from gmp.h