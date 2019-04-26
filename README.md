## How to make fastdebug JDK 8 on Windows 7

### 1) Microsoft Windows 7 with SP1 Updated 12.05.2011 7601.17514.101119-1850
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/win_ver.png" width="700"/>

### 2) Install Microsoft Visual Studio 2010 with Service Pack 1
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/visual_studio_version.png" width="600"/>

### 3) Download and install JDK 7
```sh
https://www.oracle.com/technetwork/java/javase/downloads/java-archive-downloads-javase7-521261.html
```
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/jdk_boot.png" width="600"/>

### 4) Download, unpack and add to $PATH jtreg
```sh
https://openjdk.java.net/jtreg/
```
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/jtreg_location.png" width="700"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/jtreg_path.png" width="400"/>

### 5) Download and install Cygwin
```sh
http://ctm.crouchingtigerhiddenfruitbat.org/pub/cygwin/setup/snapshots/setup-x86_64-2.874.exe
```
#### Start with -X option and proceed installation

<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_start.png" width="500"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_install_1.png" width="600"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_install_2.png" width="600"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_install_3.png" width="600"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_install_4.png" width="600"/>

#### Use the following URL
```sh
http://ctm.crouchingtigerhiddenfruitbat.org/pub/cygwin/circa/64bit/2016/08/30/104235
```
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_install_5.png" width="600"/>

#### Press "add" and make sure only entered URL is selected
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_install_6.png" width="600"/>

#### Wait for package information retrieval
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_install_7.png" width="600"/>

### 6) Now choose following packages for installation
#### gawk (Base)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_awk.png" width="900"/>

#### binutils (Devel)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_binutils.png" width="900"/>

#### cpio (Utils)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_cpio.png" width="900"/>

#### diffutils (Utils)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_diffutils.png" width="900"/>

#### file (Base)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_file.png" width="900"/>

#### m4 (Interpreters)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_m4.png" width="900"/>

#### make (Devel)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_make.png" width="900"/>

#### procps-ng (System)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_procps.png" width="900"/>

#### wget (Web)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_wget.png" width="900"/>

#### zip & unzip (Archive)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/cygwin_zip_unzip.png" width="900"/>

### 7) Download and untar freetype
```
mkdir freetype
wget http://download.savannah.gnu.org/releases/freetype/freetype-2.5.3.tar.gz
tar -xzf freetype-2.5.3.tar.gz
```
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/freetype_src.png" width="1000"/>

### 8) Download and install Mercurial
```sh
https://www.mercurial-scm.org/release/windows/mercurial-4.9.1-x64.msi
```

### 9) Clone JDK8u repository using Cygwin terminal
```sh
hg clone http://hg.openjdk.java.net/jdk8u/jdk8u/
cd jdk8u
chmod +x get_source.sh
./get_source.sh
```
### 10) Configure build (use paths from previous steps)
```sh
cd /cygdrive/c/openjdk/jdk8u/
chmod +x configure
export USERNAME=dredwardhyde   // if your user name contains spaces, create alias without them
```
#### If you configure build first time, provide path to freetype sources
```sh
./configure --enable-debug --with-target-bits=64 --with-freetype-src=/cygdrive/c/freetype/freetype-2.5.3 --with-jtreg=/cygdrive/c/jtreg
```
#### Otherwise, provide path to include and lib folders
```sh
./configure --enable-debug --with-target-bits=64 --with-freetype-lib=/cygdrive/c/freetype/freetype-2.5.3/lib64 --with-freetype-include=/cygdrive/c/freetype/freetype-2.5.3/include --with-jtreg=/cygdrive/c/jtreg
```
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/configure_src_start.png" width="1000"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/configure_src_finish.png" width="1000"/>

### 11) Make sure that boot jdk version and jtreg path are correct
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/configure_check_bootjdk.png" width="1000"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/configure_check_jtreg.png" width="1000"/>

### 12) Make build
```sh
make clean
make CONF=debug
```
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/make_start.png" width="1000"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/make_finish.png" width="1000"/>

### 13) Make images
```sh
make images
```
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/make_images_start.png" width="1000"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/make_images_finish.png" width="1000"/>

### 14) Check if build is alive
```sh
/cygdrive/c/openjdk/jdk8u/build/windows-x86_64-normal-server-fastdebug/images/j2sdk-image/bin
./java -Xinternalversion
```
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/build_done.png" width="1000"/>

### 15) Run tier1 tests (some of them could fail)
```sh
cd test
make test TEST=all
```
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/test_start.png" width="1000"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/images/test_finish.png" width="1000"/>
