FROM ubuntu:20.04

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    git \
    wget \
    xz-utils \
    build-essential \
    cmake \
    libfontconfig1-dev \
    libfreetype6-dev \
    libx11* \
    libxext-dev \
    libxfixes-dev \
    libxi-dev \
    libxrender-dev \
    libxcb* \
    libxkbcommon-x11-dev \
    mesa-common-dev \
    freeglut3 \
    freeglut3-dev \
    libglu1-mesa \
    libglu1-mesa-dev \
    libgl1-mesa-glx \
    libgl1-mesa-dev \
    python3 \
    chrpath \
    zlib1g-dev \
    liblzma-dev \
    libbz2-dev \
    && apt-get clean cache

RUN wget -q https://download.qt.io/archive/qt/6.5/6.5.3/single/qt-everywhere-src-6.5.3.tar.xz \
    && tar xf qt-everywhere-src-6.5.3.tar.xz \
    && rm qt-everywhere-src-6.5.3.tar.xz \
    && cd qt-everywhere-src-6.5.3 \
    && rm -rf qtquick3d qtquick3dphysics qtquicktimeline qtquickeffectmaker qtgrpc qtscxml qtnetworkauth qt5compat qt3d qtactiveqt qtcharts qtcoap qtconnectivity qtdatavis3d qtlanguageserver qtlocation qtmqtt qtlottie qtmultimedia qtopcua qtpositioning qtremoteobjects qtsensors qtserialbus qtserialport qtvirtualkeyboard qtwayland qttools qtwebengine qtdoc qtspeech qttranslations qtwebview qtwebchannel qtwebsockets \
    && ./configure -opensource -nomake tests -nomake examples -no-icu -confirm-license -no-dbus -sql-sqlite -xcb -xcb-xlib -bundled-xcb-xinput \
    && cmake --build . -j4 \
    && cmake --install . \
    && cd .. \
    && rm -rf qt-everywhere-src-6.5.3
