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

  -F/-f, --file     Promptless: Create only the Dockerfile, with instructions
                    (default: prompted)

  -B/-b, --build    Create both the Dockerfile and the Docker image
                    (default: prompted)

  -T/-t, --test     Start the Docker image up after build is complete
                    (default: disabled)

  -W/-w, --wipe     Hazardous: Delete all related Dockerfiles and Docker images
                    (default: always prompted)

  -H/-h, --help     Show this help message

Examples:

  rhino-docker-builder -f
    
    Creates the file Dockerfile-RhinoLinux-YYYYMMDD for building
    rhino-linux/docker:YYYYMMDD, with instructions on how to build and run the image.

  rhino-docker-builder -b -t -c -v 2023.4 -a x86_64
    
    Builds and boots amd64/rhino-linux/docker:2023.4 from scratch.
    Note: the version tag may not correlate with the actual Rhino Linux version.
    This option is meant for easily publishing images for specific milestones.
```