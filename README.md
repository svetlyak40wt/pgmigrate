[![PyPI version](https://badge.fury.io/py/yandex-pgmigrate.svg)](https://badge.fury.io/py/yandex-pgmigrate)
[![Build Status](https://travis-ci.org/yandex/pgmigrate.svg?branch=master)](https://travis-ci.org/yandex/pgmigrate)

# PGmigrate

PostgreSQL migrations made easy

## Overview

PGmigrate is a database migration tool developed by Yandex.

PGmigrate has the following key-features:

* **Transactional and nontransactional migrations:** you can enjoy whole power
of PostgreSQL DDL
* **Callbacks:** you can run some DDL on specific steps of migration process
(e.g. drop some code before executing migrations, and create it back after
migrations were applied)
* **Online migrations:** you can execute series of transactional migrations
and callbacks in a single transaction (so, if something goes wrong simple
`ROLLBACK` will bring you in consistent state)

## Install

```
pip install yandex-pgmigrate
```

## Running tests

Tests require running PostgreSQL instance with superuser (to create/drop dbs).
You could setup this yourself and use [tox](https://pypi.python.org/pypi/tox)
to start tests:
```
tox
```
Second option is to use [docker](https://www.docker.com) and make:
```
make test
```

## How to use

Complete manual is [here](doc/tutorial.md).

## Release history

* 1.0.3 (2017-12-28)
    * Fix migration error with comment at the end of file
    * Add blocking pids termination
    * Some minor fixes and improvements
* 1.0.2 (2017-04-05)
    * Speed up get_info function a bit
    * Fix callbacks in transactional/nontransactional migrations mix on db init
* 1.0.1 (2017-04-01)
    * Fix bug with python format patterns in migration text
    * Sort info command output by version
    * Support 'latest' target version
    * Add option to override user in migration meta
    * Fix info command fail without target on initialized database
    * Add session setup option
* 1.0.0 (2016-10-03)
    * First opensource version

## License

Distributed under the PostgreSQL license. See [LICENSE](LICENSE) for more
information.
