Docker Image Packaging for Duplicity
====================================

[![Travis](https://img.shields.io/travis/alvistack/docker-duplicity.svg)](https://travis-ci.org/alvistack/docker-duplicity)
[![GitHub release](https://img.shields.io/github/release/alvistack/docker-duplicity.svg)](https://github.com/alvistack/docker-duplicity/releases)
[![GitHub license](https://img.shields.io/github/license/alvistack/docker-duplicity.svg)](https://github.com/alvistack/docker-duplicity/blob/master/LICENSE)
[![Docker Pulls](https://img.shields.io/docker/pulls/alvistack/docker-duplicity.svg)](https://hub.docker.com/r/alvistack/docker-duplicity/)

Duplicity backs directories by producing encrypted tar-format volumes and uploading them to a remote or local file server.

Learn more about Duplicity: <http://www.nongnu.org/duplicity/>

Overview
--------

This Docker container makes it easy to get an instance of Duplicity up and running.

### Quick Start

For the `BACKUPDIR` directory that is used to store the repository data (amongst other things) we recommend mounting a host directory as a [data volume](https://docs.docker.com/engine/tutorials/dockervolumes/#/data-volumes), or via a named volume if using a docker version &gt;= 1.9.

Start Duplicity:

    # Pull latest image
    docker pull alvistack/docker-duplicity

    # Run as detach
    docker run \
        --rm \
        --name duplicity \
        --volume /source:/source \
        --volume /target:/target \
        alvistack/docker-duplicity \
        duplicity --allow-source-mismatch --no-encryption /source file:///target

**Success**. Duplicity will now backup the `/source` directory to `/target` directory with compression but no encryption and exit.

### Environment Variables

#### TMPDIR

The directory to use for temporary files.

Default: *NONE*

#### FTP\_PASSWORD

Supported by most backends which are password capable.

Default: *NONE*

#### PASSPHRASE

This passphrase is passed to GnuPG.

Default: *NONE*

#### SIGN\_PASSPHRASE

The passphrase to be used for --sign-key.

Default: *NONE*

Versioning
----------

The `latest` tag matches the most recent version of this repository. Thus using `alvistack/docker-duplicity:latest` or `alvistack/docker-duplicity` will ensure you are running the most up to date version of this image.

License
-------

-   Code released under [Apache License 2.0](LICENSE)
-   Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

Author Information
------------------

-   Wong Hoi Sing Edison
    -   <https://twitter.com/hswong3i>
    -   <https://github.com/hswong3i>

