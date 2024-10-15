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
### Konfiguracja Snort3
```
ip link set dev ens18 promisc on
```
```
ethtool -k ens18 | grep receive-offload
```
```
ethtool -K ens18 gro off lro off
```
### Tworzenie snort3-nic.service
```
nano /etc/systemd/system/snort3-nic.service
```
```
[Unit]
Description=Set Snort 3 NIC in promiscuous mode and Disable GRO, LRO on boot
After=network.target

[Service]
Type=oneshot
ExecStart=/usr/sbin/ip link set dev ens18 promisc on
ExecStart=/usr/sbin/ethtool -K ens18 gro off lro off
TimeoutStartSec=0
RemainAfterExit=yes

[Install]
WantedBy=default.target
```
```
systemctl daemon-reload
```
```
systemctl start snort3-nic.service
```
```
systemctl enable snort3-nic.service
```
```
systemctl status snort3-nic.service
```







