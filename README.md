# MMUX CHICKEN Checks

[![Build Status](https://travis-ci.org/marcomaggi/mmux-chicken-checks.svg?branch=master)](https://travis-ci.org/marcomaggi/mmux-chicken-checks)


## Introduction

This  package installs  a  library for  CHICKEN  a Scheme-to-C  compiler
supporting the language features as  defined in the 'Revised^5 Report on
Scheme'; the library implements features  to organise test suites and it
is derived from SRFI 78 "Lightweight testing".

The library targets POSIX systems.

The package uses the GNU Autotools and it is tested, using Travis CI, on
both Ubuntu GNU+Linux  systems and OS X systems.  The  package relies on
`pkg-config` to find the dependencies installed on the system.

## License

Copyright (c) 2009-2016, 2019 Marco Maggi `marco.maggi-ipsu@poste.it`<br/>
Copyright (c) 2005-2006 Sebastian Egner `Sebastian.Egner@philips.com`<br/>
Modified by Derick Eddington for R6RS Scheme.<br/>
Modified by Marco Maggi for CHICKEN.<br/>
All rights reserved.

This program is free software: you  can redistribute it and/or modify it
under the terms of the GNU Lesser General Public License as published by
the Free  Software Foundation, either version  3 of the License,  or (at
your option) any later version.

This program  is distributed  in the  hope that it  will be  useful, but
WITHOUT   ANY   WARRANTY;  without   even   the   implied  warranty   of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU Lesser
General Public License for more details.

You should have received a copy of the GNU Lesser General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

## Install

To install from a proper release tarball, do this:

```
$ cd mmux-chicken-checks-0.1.0
$ mkdir build
$ cd build
$ ../configure
$ make
$ make check
$ make install
```

to inspect the available configuration options:

```
$ ../configure --help
```

The Makefile is designed to allow parallel builds, so we can do:

```
$ make -j4 all && make -j4 check
```

which,  on  a  4-core  CPU,   should  speed  up  building  and  checking
significantly.

The Makefile supports the DESTDIR  environment variable to install files
in a temporary location, example: to see what will happen:

```
$ make -n install DESTDIR=/tmp/mmux-chicken-checks
```

to really do it:

```
$ make install DESTDIR=/tmp/mmux-chicken-checks
```

After the  installation it is  possible to verify the  installed library
against the test suite with:

```
$ make installcheck
```

From a repository checkout or snapshot  (the ones from the Github site):
we  must install  the GNU  Autotools  (GNU Automake,  GNU Autoconf,  GNU
Libtool), then  we must first run  the script `autogen.sh` from  the top
source directory, to generate the needed files:

```
$ cd mmux-chicken-checks
$ sh autogen.sh

```

After this  the procedure  is the same  as the one  for building  from a
proper release tarball, but we have to enable maintainer mode:

```
$ ../configure --enable-maintainer-mode [options]
$ make
$ make check
$ make install
```

When compiling  the environment  variable CHICKEN_FLAGS is  available to
hand options to the compiler:

```
$ make CHICKEN_FLAGS='-d3'
```

Shared libraries will be installed under:

```
${libdir}/chicken/9
```

## Usage

Read the documentation generated from  the Texinfo sources.  The package
installs the documentation  in Info format; we can  generate and install
documentation in HTML format by running:

```
$ make html
$ make install-html
```

## Credits

SRFI 78  is the work  of Sebastian Egner.   This package was  written by
Marco  Maggi; if  this  package exists  it's because  of  the great  GNU
software tools  that he  uses all  the time.   CHICKEN was  originally a
creation of Felix L.  Winkelmann, it is now developed and maintained The
CHICKEN Team.

## Bugs, vulnerabilities and contributions

Bug  and vulnerability  reports are  appreciated, all  the vulnerability
reports  are  public; register  them  using  the  Issue Tracker  at  the
project's GitHub  site.  For  contributions and  patches please  use the
Pull Requests feature at the project's GitHub site.

## Resources

The latest release of this package can be downloaded from:

[https://bitbucket.org/marcomaggi/mmux-chicken-checks/downloads](https://bitbucket.org/marcomaggi/mmux-chicken-checks/downloads)

development takes place at:

[http://github.com/marcomaggi/mmux-chicken-checks/](http://github.com/marcomaggi/mmux-chicken-checks/)

and as backup at:

[https://bitbucket.org/marcomaggi/mmux-chicken-checks/](https://bitbucket.org/marcomaggi/mmux-chicken-checks/)

the documentation is available online:

[http://marcomaggi.github.io/docs/mmux-chicken-checks.html](http://marcomaggi.github.io/docs/mmux-chicken-checks.html)

the GNU Project software can be found here:

[http://www.gnu.org/](http://www.gnu.org/)

we can download CHICKEN from:

[http://www.call-cc.org/](http://www.call-cc.org/)

## Badges and static analysis

### Travis CI

Travis CI is  a hosted, distributed continuous  integration service used
to build and test software projects  hosted at GitHub.  We can find this
project's dashboard at:

[https://travis-ci.org/marcomaggi/mmux-chicken-checks](https://travis-ci.org/marcomaggi/mmux-chicken-checks)

Usage of this  service is configured through the  file `.travis.yml` and
additional scripts are under the directory `meta/travis-ci`.

