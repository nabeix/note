# ios-webkit-debug-proxy-on-ubuntu-20.04

see: https://github.com/google/ios-webkit-debug-proxy

## Install dependencies

```
sudo apt install autoconf automake libusb-dev libusb-1.0-0-dev libtool libssl-dev build-essential
```

Install libplist, libimobiledevice, libusbmuxd, and usbmuxd from source:

```
git clone git@github.com:libimobiledevice/libplist.git -b 2.2.0
cd libplist
./autogen.sh --without-cython 
make
sudo make install
```

```
git clone git@github.com:libimobiledevice/libusbmuxd.git -b 2.0.2
cd libusbmuxd
./autogen.sh
make
sudo make install
```

```
git clone git@github.com:libimobiledevice/libimobiledevice.git -b 1.3.0
cd libimobiledevice
./autogen
make
sudo make install
```

```
git clone git@github.com:libimobiledevice/usbmuxd.git -b 1.1.1
cd usbmuxd
./autogen
make
sudo make install
```

## Install ios-webkit-debug-proxy

```
git clone https://github.com/google/ios-webkit-debug-proxy.git
cd ios-webkit-debug-proxy

./autogen.sh
make
sudo make install
```

## Run ios-webkit-debug-proxy

1. Run usbmuxd

```
sudo usbmuxd -f
# Running usbmuxd as daemon is prefer
```

2. Connect iOS device to the host machine
3. Run proxy and 
```
ios_webkit_debug_proxy
```

4. Open chrome and access to `chrome://inspect/#devices` and press inspect button on target device.

NOTE: I can't inspect. dev tools shows blank page.
