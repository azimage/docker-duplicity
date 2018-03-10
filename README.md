Docker Image Packaging for Duplicity
====================================

[![Travis](https://img.shields.io/travis/alvistack/docker-duplicity.svg)](https://travis-ci.org/alvistack/docker-duplicity)
[![GitHub release](https://img.shields.io/github/release/alvistack/docker-duplicity.svg)](https://github.com/alvistack/docker-duplicity/releases)
[![GitHub license](https://img.shields.io/github/license/alvistack/docker-duplicity.svg)](https://github.com/alvistack/docker-duplicity/blob/master/LICENSE)
[![Docker Pulls](https://img.shields.io/docker/pulls/alvistack/duplicity.svg)](https://hub.docker.com/r/alvistack/duplicity/)

Duplicity backs directories by producing encrypted tar-format volumes and uploading them to a remote or local file server.

Learn more about Duplicity: <http://www.nongnu.org/duplicity/>

Overview
--------

This Docker container makes it easy to get an instance of Duplicity up and running.

### Quick Start

For the `BACKUPDIR` directory that is used to store the repository data (amongst other things) we recommend mounting a host directory as a [data volume](https://docs.docker.com/engine/tutorials/dockervolumes/#/data-volumes), or via a named volume if using a docker version &gt;= 1.9.

Start Duplicity:

    # Pull latest image
    docker pull alvistack/duplicity

    # Run as detach
    docker run \
        -itd \
        --rm \
        --name duplicity \
        --volume /tmp/source:/source \
        --volume /tmp/target:/target \
        alvistack/duplicity \
        duplicity --allow-source-mismatch --no-encryption /source file:///target

**Success**. Duplicity will now backup the `/source` directory to `/target` directory with compression but no encryption and exit.

Versioning
----------

The `latest` tag matches the most recent version of this repository. Thus using `alvistack/duplicity:latest` or `alvistack/duplicity` will ensure you are running the most up to date version of this image.

License
-------

-   Code released under [Apache License 2.0](LICENSE)
-   Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

Author Information
------------------

-   Wong Hoi Sing Edison
    -   <https://twitter.com/hswong3i>
    -   <https://github.com/hswong3i>

