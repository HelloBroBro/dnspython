# dnspython

[![Build Status](https://github.com/rthalley/dnspython/actions/workflows/ci.yml/badge.svg)](https://github.com/rthalley/dnspython/actions/)
[![Documentation Status](https://readthedocs.org/projects/dnspython/badge/?version=latest)](https://dnspython.readthedocs.io/en/latest/?badge=latest)
[![PyPI version](https://badge.fury.io/py/dnspython.svg)](https://badge.fury.io/py/dnspython)
[![License: ISC](https://img.shields.io/badge/License-ISC-brightgreen.svg)](https://opensource.org/licenses/ISC)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

## INTRODUCTION

dnspython is a DNS toolkit for Python. It supports almost all record types. It
can be used for queries, zone transfers, and dynamic updates. It supports TSIG
authenticated messages and EDNS0.

dnspython provides both high and low level access to DNS. The high level classes
perform queries for data of a given name, type, and class, and return an answer
set. The low level classes allow direct manipulation of DNS zones, messages,
names, and records.

To see a few of the ways dnspython can be used, look in the `examples/`
directory.

dnspython is a utility to work with DNS, `/etc/hosts` is thus not used. For
simple forward DNS lookups, it's better to use `socket.getaddrinfo()` or
`socket.gethostbyname()`.

dnspython originated at Nominum where it was developed
to facilitate the testing of DNS software.

## ABOUT THIS RELEASE

This is the development version of dnspython 2.7.0.
Please read
[What's New](https://dnspython.readthedocs.io/en/latest/whatsnew.html) for
information about the changes in this release.

## INSTALLATION

* Many distributions have dnspython packaged for you, so you should
  check there first.
* To use a wheel downloaded from PyPi, run:

    pip install dnspython

* To install from the source code, go into the top-level of the source code
  and run:

```
    pip install --upgrade pip build
    python -m build
    pip install dist/*.whl
```

* To install the latest from the master branch, run `pip install git+https://github.com/rthalley/dnspython.git`

Dnspython's default installation does not depend on any modules other than
those in the Python standard library.  To use some features, additional modules
must be installed.  For convenience, pip options are defined for the
requirements.

If you want to use DNS-over-HTTPS, run
`pip install dnspython[doh]`.

If you want to use DNSSEC functionality, run
`pip install dnspython[dnssec]`.

If you want to use internationalized domain names (IDNA)
functionality, you must run
`pip install dnspython[idna]`

If you want to use the Trio asynchronous I/O package, run
`pip install dnspython[trio]`.

If you want to use WMI on Windows to determine the active DNS settings
instead of the default registry scanning method, run
`pip install dnspython[wmi]`.

If you want to try the experimental DNS-over-QUIC code, run
`pip install dnspython[doq]`.

Note that you can install any combination of the above, e.g.:
`pip install dnspython[doh,dnssec,idna]`

### Notices

Python 2.x support ended with the release of 1.16.0.  Dnspython 2.0.0 through
2.2.x support Python 3.6 and later.  For dnspython 2.3.x, the minimum
supported Python version is 3.7, and for 2.4.x the minimum supported verison is 3.8.
We plan to align future support with the lifetime of the Python 3 versions.

Documentation has moved to
[dnspython.readthedocs.io](https://dnspython.readthedocs.io).
