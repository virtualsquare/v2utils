# v2utils
v2utils: virtualsquare libraries and utilities

## this is still an experimental repository

This repository has been created to manage the debian packets of the general purpose
libraries and tools created in the development of virtualsquare projects.

This project includes the development repositories as git submodules.

It is currently including the following projects:

* [strcase](https://github.com/rd235/strcase)
* [libstropt](https://github.com/rd235/libstropt)
* [libfduserdata](https://github.com/rd235/libfduserdata)
* [libvpoll-eventfd](https://github.com/rd235/libvpoll-eventfd)
* [libvolatilestream](https://github.com/rd235/libvolatilestream)
* [userbindmount](https://github.com/rd235/userbindmount)

*Do not clone or use this repository unless you are part of the development team, or you want to contribute to the project*

*Please refer to the development repositories above for cloning, updating, send bug reports, etc.*

## Download and creation of debian packets

* prerequisites: cmake, debuild, ronn (for the man pages)

* clone the git repository including the submodules:

    ```
    git clone --recurse-submodules https://github.com/virtualsquare/v2utils.git
    ```

* create the packets:

    ```
    cd v2utils
    ./create_deb.sh newtag
    ```

    (newtag creates the orig.tar.gz source package)

* update the whole source hierarchy including submodules:

    ```
    git pull --recurse-submodules
		git submodule foreach -q --recursive 'git checkout master; git pull'
    ```
    
* Update the packets:

    ```
    ./create_deb.sh
    ```

    or

    ```
    debuild -us -uc
    ```

* create the official signed packets:

    ```
    debuild
    ```

## Status:

The packets get cleanly created.
Lintian complains only for the improbable ITP bug number(0000).

## Still to do:

Double check runtime dependencies.
File an ITP request
Change the number of ITP in debian/changelog
