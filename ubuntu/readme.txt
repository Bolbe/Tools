The precompiled Qt compiler is built as follow:

# Make the docker image based on ubuntu 22.04. Download Qt653, compile it, install it:
docker build . -t ubuntu2204qt653

# Enter the container and bind pwd to /host
docker run --rm -it -v ${PWD}:/host ubuntu2204qt653

# Tar the Qt directory:
cd /usr/local
XZ_OPT='-9' tar -cJf /host/Qt653-dynamic-ubuntu2204.tar.xz Qt-6.5.3-dynamic
XZ_OPT='-9' tar -cJf /host/Qt653-static-ubuntu2204.tar.xz Qt-6.5.3-static


