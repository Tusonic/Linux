### Instalowanie wymaganych zależności
```
apt install build-essential libnet1-dev zlib1g-dev luajit hwloc libdnet-dev libdumbnet-dev libpcap-dev libpcre3-dev  bison flex liblzma-dev openssl libssl-dev pkg-config libhwloc-dev cmake cpputest libsqlite3-dev uuid-dev libcmocka-dev libnetfilter-queue-dev libmnl-dev autotools-dev libluajit-5.1-dev libunwind-dev libfl-dev -y
```
### Insalacja Snort DAQ

```
git clone https://github.com/snort3/libdaq.git
```
```
cd libdaq
```
```
./bootstrap
```
```
./configure
```
```
make
```
```
make install
```
### Instalacja GPerftools
```
cd
```
```
wget https://github.com/gperftools/gperftools/releases/download/gperftools-2.9.1/gperftools-2.9.1.tar.gz
```
```
tar xzf gperftools-2.9.1.tar.gz
```
```
cd gperftools-2.9.1/
```
```
./configure
```
```
make
```
```
make install
```
### Instalacja Snort 3
```
cd
```
```
wget https://github.com/snort3/snort3/archive/refs/tags/3.1.43.0.tar.gz
```
```
tar -xvzf 3.1.43.0.tar.gz
```
```
cd snort 3-3.1.43.0
```
```
./configure_cmake.sh --prefix=/usr/local --enable-tcmalloc
```
```
make
```
```
make install
```
```
ldconfig
```
### Sprawdzamy czy Snort3 jest zainstalowany
```
snort -V
```




