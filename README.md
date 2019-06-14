# linuxdeployqt ("FREEDOM" version)

This is a fork of the project https://github.com/probonopd/linuxdeployqt with the difference that you're not obliged to use Ubuntu as a development host. Use whatever distribution you're used to, but _know what you're doing_.

I believe that it is the developer's responsibility to know what needs to be made to support multiple distributions using AppImage + linuxdeployqt, and *a tool is just a tool, after all*.

For a more complete background of why this change has been made, check the original [discussion thread](https://github.com/probonopd/linuxdeployqt/issues/340).

# Building from source

Here are the steps:

* Get and build linuxdeployqt:

```
sudo apt-get -y install git g++ libgl1-mesa-dev
git clone https://github.com/balena/linuxdeployqt.git
# Then build in Qt Creator, or use
export PATH=$(readlink -f /tmp/.mount_QtCreator-*-x86_64/*/gcc_64/bin/):$PATH
cd linuxdeployqt
qmake
make
```

* Optional if you want to install `linuxdeployqt` into your Qt installation, and make it a part of your Qt just like any other tool (qmake, etc.)

```
sudo make install
```

* Build and install [patchelf](https://nixos.org/patchelf.html):

```
wget https://nixos.org/releases/patchelf/patchelf-0.9/patchelf-0.9.tar.bz2
tar xf patchelf-0.9.tar.bz2
( cd patchelf-0.9/ && ./configure  && make && sudo make install )
```

* Optional if you want to generate AppImages: Download [appimagetool](https://github.com/AppImage/AppImageKit/releases) and put it into your $PATH, e.g., into `/usr/local/bin`. Make sure it is renamed to `appimagetool` and is `chmod a+x`

```
sudo wget -c "https://github.com/AppImage/AppImageKit/releases/download/continuous/appimagetool-x86_64.AppImage" -O /usr/local/bin/appimagetool
sudo chmod a+x /usr/local/bin/appimagetool
```

## Contributing

Feel free to contribute with code, comments, whatever you want and in the way you want, it's Open Source!

## Contact

Refer always to the original project https://github.com/probonopd/linuxdeployqt as they are the original authors.

If you don't agree that developers should know what they are doing, ¯\\\_(ツ)\_/¯ .
