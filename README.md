## How to make fastdebug JDK 8 on Windows 7

### 1) Microsoft Windows 7 with SP1 Updated 12.05.2011 7601.17514.101119-1850
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/win_ver.png" width="700"/>

### 2) Install Microsoft Visual Studio 2010 with Service Pack 1
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/visual_studio_version.png" width="600"/>

### 3) Download and install JDK 7
```sh
https://www.oracle.com/technetwork/java/javase/downloads/java-archive-downloads-javase7-521261.html
```
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/jdk_boot.png" width="600"/>

### 4) Download, unpack and add to $PATH jtreg
```sh
https://openjdk.java.net/jtreg/
```
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/jtreg_location.png" width="700"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/jtreg_path.png" width="400"/>

### 5) Download and install Cygwin:
```sh
http://ctm.crouchingtigerhiddenfruitbat.org/pub/cygwin/setup/snapshots/setup-x86_64-2.874.exe
```
#### Start with -X option:

<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_start.png" width="500"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_install_1.png" width="600"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_install_2.png" width="600"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_install_3.png" width="600"/>
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_install_4.png" width="600"/>

#### Use the following URL:
```sh
http://ctm.crouchingtigerhiddenfruitbat.org/pub/cygwin/circa/64bit/2016/08/30/104235
```
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_install_5.png" width="600"/>

#### Press "add" and make sure only entered URL is selected:
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_install_6.png" width="600"/>

#### Wait for package information retrieval:
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_install_7.png" width="600"/>

### 3) Now choose following packages for installation:
#### gawk (Base)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_awk.png" width="900"/>

#### binutils (Devel)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_binutils.png" width="900"/>

#### cpio (Utils)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_cpio.png" width="900"/>

#### diffutils (Utils)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_diffutils.png" width="900"/>

#### file (Base)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_file.png" width="900"/>

#### m4 (Interpreters)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_m4.png" width="900"/>

#### make (Devel)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_make.png" width="900"/>

#### procps-ng (System)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_procps.png" width="900"/>

#### wget (Web)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_wget.png" width="900"/>

#### zip & unzip (Archive)
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/cygwin_zip_unzip.png" width="900"/>

### 6) Download and untar freetype:
```
wget http://download.savannah.gnu.org/releases/freetype/freetype-2.5.3.tar.gz
tar -xzf freetype-2.5.3.tar.gz
```
<img src="https://raw.githubusercontent.com/dredwardhyde/jdk-8-fastdebug-building-instructions/master/freetype_src.png" width="1000"/>
