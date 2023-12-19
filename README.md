# Jarkom-Modul-2-E17-2023
Kelompok E17 -
Jaringan Komputer (F) </br>
*Insitut Teknologi Sepuluh Nopember*

**Authors :**
| Name                  | Student ID |
| ----------------------|------------|
| Rizky Alifiyah Rahma  | 5025211208 |
| Dilla Wahdana         | 5025211234 |

## Topologi
![]()

## Rute Subnet
![]()

| Subnet | Rute | Jumlah IP | Netmask |
| --- | --- | --- | --- |
| A1 | Fern-Switch2-Revolte | 2 | /30 |
| A2 | Fern-Richter | 2 | /30 |
| A3 | Himmel-Switch6-SchwerMountains-Fern | 66 | /25 |
| A4 | Himmel-Laubhills | 256 | /23 |
| A5 | Frieren-Himmel | 2 | /30 |
| A6 | Aura-Frieren | 2 | /30 |
| A7 | Aura-Heiter | 2 | /30 |
| A8 | Frieren-Stark | 2 | /30 |
| A9 | Heiter-TurkRegion | 1023 | /21 |
| A10 | Heiter-Switch3-Sein-GrobeForest | 514 | /22 |
| TOTAL | --- | 1871 | /20 |

## Tree VLSM
![]()

| Subnet | Network ID | Netmask | Broadcast |
| --- | --- | --- | --- |
| A1 | 10.45.0.0 | 255.255.255.252 | 10.45.0.3 |
| A2 | 10.45.0.4 | 255.255.255.252 | 10.45.0.7 |
| A3 | 10.45.0.128 | 255.255.255.128 | 10.45.0.255 |
| A4 | 10.45.2.0 | 255.255.254.0 | 10.45.3.255 |
| A5 | 10.45.0.8 | 255.255.255.252 | 10.45.0.11 |
| A6 | 10.45.0.12 | 255.255.255.252 | 10.45.0.15 |
| A7 | 10.45.0.16 | 255.255.255.252 | 10.45.15.255 |
| A8 | 10.45.0.20 | 255.255.255.252 | 10.45.0.23 |
| A9 | 10.45.8.0 | 255.255.248.0 | 10.45.15.255 |
| A10 | 10.45.4.0 | 255.255.252.0 | 10.45.7.255 |

## Konfigurasi Subnetting
#### Aura
```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 10.45.0.17
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.45.0.13
	netmask 255.255.255.252
```
#### Heiter
```
auto eth0
iface eth0 inet static
	address 10.45.0.18
	netmask 255.255.255.252
	gateway 10.45.0.17

auto eth1
iface eth1 inet static
	address 10.45.8.1
	netmask 255.255.248.0

auto eth2
iface eth2 inet static
	address 10.45.4.1
	netmask 255.255.252.0
```
#### TurkRegion
```
auto eth0
iface eth0 inet static
	address 10.45.8.2
	netmask 255.255.248.0
	gateway 10.45.8.1
```
#### Sein
```
auto eth0
iface eth0 inet static
	address 10.45.4.2
	netmask 255.255.252.0
	gateway 10.45.4.1
```
#### GrobeForest
```
auto eth0
iface eth0 inet static
	address 10.45.4.3
	netmask 255.255.252.0
	gateway 10.45.4.1
```
#### Frieren
```
auto eth0
iface eth0 inet static
	address 10.45.0.14
	netmask 255.255.255.252
	gateway 10.45.0.13

auto eth1
iface eth1 inet static
	address 10.45.0.21
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.45.0.9
	netmask 255.255.255.252
```
#### Stark
```
auto eth0
iface eth0 inet static
	address 10.45.0.22
	netmask 255.255.255.252
	gateway 10.45.0.21
```
#### Himmel
```
auto eth0
iface eth0 inet static
	address 10.45.0.10
	netmask 255.255.255.252
	gateway 10.45.0.9

auto eth1
iface eth1 inet static
	address 10.45.2.1
	netmask 255.255.254.0

auto eth2
iface eth2 inet static
	address 10.45.0.129
	netmask 255.255.255.128
```
#### LaubHills
```
auto eth0
iface eth0 inet static
	address 10.45.2.2
	netmask 255.255.254.0
	gateway 10.45.2.1
```
#### SchwerMountain
```
auto eth0
iface eth0 inet static
	address 10.45.0.131
	netmask 255.255.255.128
	gateway 10.45.0.129
```
#### Fern
```
auto eth0
iface eth0 inet static
	address 10.45.0.130
	netmask 255.255.255.128
	gateway 10.45.0.129

auto eth1
iface eth1 inet static
	address 10.45.0.5
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.45.0.1
	netmask 255.255.255.252
```
#### Richter
```
auto eth0
iface eth0 inet static
	address 10.45.0.6
	netmask 255.255.255.252
	gateway 10.45.0.5
```
#### Revolte
```
auto eth2
iface eth2 inet static
	address 10.45.0.2
	netmask 255.255.255.252
	gateway 10.45.0.1
```

## Routing
#### Aura
```
route add -net 10.45.8.0 netmask 255.255.248.0 gw 10.45.0.18
route add -net 10.45.4.0 netmask 255.255.252.0 gw 10.45.0.18
route add -net 10.45.0.20 netmask 255.255.255.252 gw 10.45.0.14
route add -net 10.45.0.8 netmask 255.255.255.252 gw 10.45.0.14
route add -net 10.45.2.0 netmask 255.255.255.252 gw 10.45.0.14
route add -net 10.45.0.128 netmask 255.255.255.252 gw 10.45.0.14
route add -net 10.45.0.4 netmask 255.255.255.252 gw 10.45.0.14
route add -net 10.45.0.0 netmask 255.255.255.252 gw 10.45.0.14
```
#### Heiter
```
route add -net 10.45.0.12 netmask 255.255.255.252 gw 10.45.0.17
route add -net 10.45.0.20 netmask 255.255.255.252 gw 10.45.0.17
route add -net 10.45.0.8 netmask 255.255.255.252 gw 10.45.0.17
route add -net 10.45.2.0 netmask 255.255.255.252 gw 10.45.0.17
route add -net 10.45.0.128 netmask 255.255.255.252 gw 10.45.0.17
route add -net 10.45.0.4 netmask 255.255.255.252 gw 10.45.0.17
route add -net 10.45.0.0 netmask 255.255.255.252 gw 10.45.0.17
```
#### Frieren
```
route add -net 10.45.0.16 netmask 255.255.255.252 gw 10.45.0.13
route add -net 10.45.8.0 netmask 255.255.248.0 gw 10.45.0.13
route add -net 10.45.4.0 netmask 255.255.252.0 gw 10.45.0.13
route add -net 10.45.2.0 netmask 255.255.254.0 gw 10.45.0.10
route add -net 10.45.0.128 netmask 255.255.255.128 gw 10.45.0.10
route add -net 10.45.0.4 netmask 255.255.255.252 gw 10.45.0.10
route add -net 10.45.0.0 netmask 255.255.255.252 gw 10.45.0.10
```
#### Fern
```
route add -net 10.45.0.0 netmask 255.255.255.252 gw 10.45.0.1
route add -net 10.45.0.4 netmask 255.255.255.252 gw 10.45.0.5
```
#### Himmel
```
route add -net 10.45.2.0 netmask 255.255.254.0 gw 10.45.2.1
route add -net 10.45.0.128 netmask 255.255.255.238 gw 10.45.0.129
route add -net 10.45.0.0 netmask 255.255.255.252 gw 10.45.0.130
route add -net 10.45.0.4 netmask 255.255.255.252 gw 10.45.0.130
```

## Konfigurasi DHCP
### Konfigurasi DHCP Server
- 

### Konfigurasi DHCP Relay

## Soal 1
> Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.

### Script Pengerjaan
### Hasil
![]()

## Soal 2
> Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.

### Script Pengerjaan
### Hasil
![]()

## Soal 3
> Kepala Suku North Area meminta kalian untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop.

### Script Pengerjaan
### Hasil
![]()

## Soal 4
> Lakukan pembatasan sehingga koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest.

### Script Pengerjaan
### Hasil
![]()

## Soal 5
> Selain itu, akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00.

### Script Pengerjaan
### Hasil
![]()

## Soal 6
> Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).

### Script Pengerjaan
### Hasil
![]()

## Soal 7
> Karena terdapat 2 WebServer, kalian diminta agar setiap client yang mengakses Sein dengan Port 80 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan dan request dari client yang mengakses Stark dengan port 443 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan.

### Script Pengerjaan
### Hasil
![]()

## Soal 8
> Karena berbeda koalisi politik, maka subnet dengan masyarakat yang berada pada Revolte dilarang keras mengakses WebServer hingga masa pencoblosan pemilu kepala suku 2024 berakhir. Masa pemilu (hingga pemungutan dan penghitungan suara selesai) kepala suku bersamaan dengan masa pemilu Presiden dan Wakil Presiden Indonesia 2024.

### Script Pengerjaan
### Hasil
![]()

## Soal 9
> Sadar akan adanya potensial saling serang antar kubu politik, maka WebServer harus dapat secara otomatis memblokir  alamat IP yang melakukan scanning port dalam jumlah banyak (maksimal 20 scan port) di dalam selang waktu 10 menit. 
(clue: test dengan nmap)

### Script Pengerjaan
### Hasil
![]()

## Soal 10
> Karena kepala suku ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level. 

### Script Pengerjaan 
### Hasil
![]()
