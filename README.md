# Rhino Docker Builder

A script that helps to easily build and test Rhino Linux Docker images.

```
Usage: rhino-docker-builder [OPTIONS]

Options:

  -V/-v, --version  Image version tag
                    (default: current date in YYYYMMDD format)

  -A/-a, --arch     Target architecture
                    (options: auto, arm64/aarch64, amd64/x86_64, default: all/off)

  -C/-c, --clean    Use --no-cache during Docker image build
                    (default: disabled)

  -F/-f, --file     Create only the Dockerfile, with instructions
                    (default: prompted)

  -B/-b, --build    Create both the Dockerfile and the Docker image
                    (default: prompted)

  -P/-p, --pull     Pull a Docker image from the upstream registry
                    (options: --version, default: always uses --arch auto)

  -T/-t, --test     Start the Docker image up after build or pull is complete
                    (default: disabled or prompted)

  -W/-w, --wipe     Hazardous: Delete all related Dockerfiles and Docker images
                    (default: always prompted)

  -H/-h, --help     Show this help message

Examples:

  rhino-docker-builder -f

    Creates the file Dockerfile-RhinoLinux-YYYYMMDD for building the image
    rhino-linux/docker:YYYYMMDD, with instructions on how to build and run it.

    Note: if no options are passed, this is the default function, but users
    will be asked if they would like to build and test the image.


  rhino-docker-builder -b -t -c -v 2023.4 -a x86_64
    
    Builds and starts amd64/rhino-linux/docker:2023.4 from scratch.

    Note: the version tag may not correlate with the actual Rhino Linux version.
    This option is meant for easily publishing images for specific milestones.


  rhino-docker-builder -p -t -v latest
    
    Pulls and starts ghcr.io/rhino-linux/docker:latest.
```