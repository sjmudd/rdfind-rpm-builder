# Rebuild rdfind from another src rpm

I am currently using Oracle Linux 9 and could not find rdfind
so decided to build it myself from the latest rpm I could find.

The build process is designed to run from a docker container to
avoid contamination of the environment and also to allow this
to be built from a non-OL9 box.

## Steps to build

1. requires docker to be installed
2. Create an empty `PKGS` directory with a non-root user
3. Run: `docker run -it -v $PWD:/build -w /build oraclelinux:9`
4. From the container run: `sh build`
5. Any built rpms should be found in `PKGS` directory on builder box.

## Notes

Configuration is a bit odd because I'm using an NFS mount and root_squash
is configured so writing files as root does not work. This slightly
affects the build process.
