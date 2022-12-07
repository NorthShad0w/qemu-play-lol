# qemu-play-lol
用qemu玩lol

myos fedora


```
sudo dnf install git glib2-devel libfdt-devel pixman-devel zlib-devel bzip2 ninja-build python3
sudo dnf install libaio-devel libcap-ng-devel libiscsi-devel capstone-devel \
                 gtk3-devel SDL2-devel vte291-devel ncurses-devel \
sudo dnf install libseccomp-devel nettle-devel libattr-devel libjpeg-devel \
                 brlapi-devel libgcrypt-devel lzo-devel snappy-devel \
                 librdmacm-devel libibverbs-devel cyrus-sasl-devel libpng-devel \
                 libuuid-devel pulseaudio-libs-devel curl-devel libssh-devel \
                 systemtap-sdt-devel libusbx-devel xen-devel
                 
                 spice-protocol spice-server-devel systemd-devel usbredir-devel iasl gnutls-devel SDL_image-devel git-email clang-devel bluez-libs-devel \
                 libcap-devel libglibutil-devel pam-devel virglrenderer-devel librbd-devel mesa-libgbm-devel \
                 libnfs-devel libzstd-devel numactl-devel
```

```
git clone https://gitlab.com/qemu-project/qemu/ -b v7.0.0 --depth 1 --recursive
cd qemu
git apply qemu7.0.0.patch
cd ..
mkdir qemu_build
cd qemu_build
sudo ../qemu/configure --target-list=x86_64-softmmu,x86_64-linux-user --prefix=/usr
sudo make
sudo make install
```

```
# Switch to the QEMU root directory.
cd qemu
# Prepare a native debug build.
mkdir -p bin/debug/native
cd bin/debug/native
# Configure QEMU and start the build.
../../../configure --enable-debug
make
# Return to the QEMU root directory.
cd ../../..
```
