How to build the Qt compiler for macOS:
Download qt opensource 6.5.3


wget https://download.qt.io/archive/qt/6.5/6.5.3/single/qt-everywhere-src-6.5.3.tar.xz

brew install cmake
brew install ninja

tar xf qt-everywhere-src-6.5.3.tar.xz
cd qt-everywhere-src-6.5.3

rm -rf qtquickeffectmaker qtgrpc qtscxml qtnetworkauth qt5compat qt3d qtactiveqt qtcharts qtcoap qtconnectivity qtdatavis3d qtlanguageserver qtlocation qtmqtt qtlottie qtmultimedia qtopcua qtpositioning qtremoteobjects qtsensors qtserialbus qtserialport qtvirtualkeyboard qtwayland qttools qtwebengine qtdoc qtspeech qttranslations qtwebview qtwebchannel qtwebsockets qthttpserver 
Warning: keep qtQuick3d and its dependencies (shadertools, physics) because QtQuick needs quick3d !
In the end, keep:
drwx------  31 gargamel  staff   992B Sep 25 19:00 qtbase
drwx------  23 gargamel  staff   736B Sep 25 19:00 qtdeclarative
drwx------  14 gargamel  staff   448B Sep 25 19:00 qthttpserver
drwx------  17 gargamel  staff   544B Sep 25 19:00 qtimageformats
drwx------  23 gargamel  staff   736B Sep 25 19:00 qtquick3d
drwx------  18 gargamel  staff   576B Sep 25 19:00 qtquick3dphysics
drwx------  14 gargamel  staff   448B Sep 25 19:00 qtquicktimeline
drwx------  14 gargamel  staff   448B Sep 25 19:00 qtshadertools
drwx------  15 gargamel  staff   480B Sep 25 19:00 qtsvg

./configure -opensource -nomake tests -nomake examples -no-icu -confirm-license -no-dbus -sql-sqlite -prefix ./Qt653-macos
cmake --build . --parallel
sudo cmake --install .
