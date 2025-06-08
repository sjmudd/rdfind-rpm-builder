# Rebuilding rdfind
# - was not available on OL9 so rebuilt myself.
# - taken from latest version of rdfind I could find.
# - designed to be built from a bare container

1. Create an empty PKGS directory with a non-root user
2. run: docker run -it -v $PWD:/build -w /build oraclelinux:9
3. from the container run sh build

Notes:

Configuration is a bit odd because I'm using an NFS mount and root_squash
is configured so writing files as root does not work. This slightly
affects the build process.
