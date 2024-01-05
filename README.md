# Rhino Docker Builder

A script that helps to easily build and test Rhino Linux Docker images.

```
Usage: rhino-docker-builder [OPTIONS]

Options:

  -V/-v, --version  Image version tag
                    (default: current date in YYYYMMDD format)

  -A/-a, --arch     Target architecture
                    (options: arm64/aarch64, amd64/x86_64, all/off, default: auto)

  -T/-t, --test     Promptless: fully build and start up the image
                    (default: disabled)

  -C/-c, --clean    Use --no-cache during Docker build
                    (default: disabled)

  -F/-f, --file     Promptless: Create only the Dockerfile, with instructions
                    (default: prompted)

  -W/-w, --wipe     Hazardous: Delete all related Dockerfiles and Docker images
                    (default: prompted)

  -H/-h, --help     Show this help message

Examples:

  rhino-docker-builder -t -c -v 2023.4 -a arm64
    
    Builds and boots arm64v8/rhinolinux:2023.4 from scratch.
    Note: the version tag may not correlate with the actual Rhino Linux version.
    This option is meant for easily publishing images for specific milestones.


  rhino-docker-builder --file -A x86_64
    
    Creates the Dockerfile Dockerfile.RhinoLinux.${dateiniso}_amd64 for building 
    arm64v8/rhinolinux:${dateiniso}, with instructions on how to build and run the image.
```
