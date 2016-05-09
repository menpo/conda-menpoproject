Menpo Project Conda Metapackage
===============================

This repo contains a conda metapackage that can be used to install the latest version of the whole menpo project. It is the recommended way of getting started with Menpo.

Note on versioning
------------------

Note that this package exists as a conveinient mechanism to install the whole menpo project. **It itself does not have a meaningful version number** which means **other projects relying on menpo should not version against this package**. Instead version against the explicit pieces of the Menpo project that you use.

As an example, say that you are developing a facial recognition system, and you rely on `menpodetect` for detection and `menpofit` for landmark localization. If you provide a conda package of your project you should version against the major version of these two packages, not against `menpoproject`.

Updating
--------

1. Change `meta.yaml` with the changed dependencies
2. Bump the build number in the `meta.yaml` by 1.
3. `conda build .`
4. `anaconda upload -u menpo -c master /path/to/conda-bld/noarch/menpoproject-1.0-py_0.tar.bz2`
