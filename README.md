# Linux4.16.0 arm64 kernel build
### for debuging with KGDB
###### will add KDB later..

## What is this repository?
kgdb研 戚遂背 arm64 朕確聖 郊稽 巨獄焔 拝 呪 赤亀系 柵球 背兜精
煽舌社脊艦陥. 

_~~慎嬢研 公背辞 廃越稽 旋精 依精 焼鑑艦陥. ぞぞぞぞぞぞ ^^;;;;;~~_

### Debugging Environment
* **Host OS** : Ubuntu(18.04 LTS) on Windows (Download from Windows Store)
* **Target Kernel Version** : v4.16.0
* **GDB Version** : GNU gdb:multiarch 8.1.0
* **Compiler Version** : aarch64:linux:gnu:gcc 7.3.0
* **Qemu Version** : qemu:system:aarch64 2.11.1

## How to get ready for compiling


**Install Dependent Packages**

###### Ubuntu
```sh
sudo apt-get install build-essentials libncurses5-dev libssl-dev bc bison flex \
                libelf-dev
```

###### Fedora
```sh
sudo dnf install ncurses-devel bison-devel bison flex-devel flex \
                elfutils-libelf-devel openssl-devel
```
> [https://sjp38.github.io/post/linux-kernel-build/](https://sjp38.github.io/post/linux-kernel-build/)

**Install Compiler Package**

###### Ubuntu
```sh
sudo apt-get install binutils-aarch64-linux-gnu gcc-aarch64-linux-gnu \
                g++-aarch64-linux-gnu
```

> [https://blog.thinkbee.kr/linux/crosscompile-arm/](https://blog.thinkbee.kr/linux/crosscompile-arm/)


## How to make Image?

```sh
make mrproper
make defconfig
make menuconfig
make Image
```

* `$ make mrproper` : config 督析 clean
* `$ make defconfig` : 背雁 arch税 defconfig 督析稽 .config 竺舛 (./arch/ARCH/configs/defconfig 含櫛 馬蟹赤製)
* `$ make menuconfig` : 蓄亜 痕井拝 config 竺舛(kgdb 竺舛)
* `$ make Image` :  Image (朕確戚耕走) 柵球.  
        * Caution : -j 辛芝聖 爽走 省澗 依聖 映舌. (督析 税糎失 庚薦稽 陳督析 掻舘戚 切爽 忽嬢像)

> [http://xenostudy.tistory.com/485](http://xenostudy.tistory.com/485)

## How to update configuration file for debugging

* **defconfig**
![config-defconfig](https://tot0ro-prog.firebaseapp.com/Image/Linux4.16_arm64_debug_build/make_config.PNG)

* **CONFIG\_DEBUG\_INFO=y**
![config-debuginfo](https://tot0ro-prog.firebaseapp.com/Image/Linux4.16_arm64_debug_build/debug_info.PNG)

* **CONFIG\_KGDB=y**
![config-kgdb](https://tot0ro-prog.firebaseapp.com/Image/Linux4.16_arm64_debug_build/kgdb.PNG)

* **CONFIG\_KGDB\_SERIAL\_CONSOLE=y**
![config-kgdb-serial-console](https://tot0ro-prog.firebaseapp.com/Image/Linux4.16_arm64_debug_build/kgdb_serial_console.PNG)

* **CONFIG\_FRAME\_POINTER=y**
![config-frame-pointer](https://tot0ro-prog.firebaseapp.com/Image/Linux4.16_arm64_debug_build/frame_pointer.PNG)

> [http://studyfoss.egloos.com/5490783](http://studyfoss.egloos.com/5490783)



