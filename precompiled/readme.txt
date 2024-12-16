The precompiled Qt compiler is built as follow:

# Make the docker image based on ubuntu 20.04. Download Qt653, compile it, install it:
docker build . -t ubuntu2004qt653

# Enter the container:
docker run --rm -it -v ${PWD}:/host ubuntu2004qt653

# Tar the the Qt directory:
cd /usr/local
XZ_OPT='-9' tar -cJf /host/Qt653-ubuntu2004.tar.xz Qt-6.5.3
