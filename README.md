# VMware Lab: pfSense & Zabbix

Bu depo, VMware Workstation Pro üzerinde kurduğum pfSense ve Zabbix tabanlı laboratuvar ortamının adımlarını, yapılandırmalarını ve örnek konfigürasyon dosyalarını içerir.

## İçindekiler

- pfSense Kurulumu ve Ağ Ayarları
- Zabbix Server Kurulumu ve İzleme Ayarları
- Firewall ve DHCP Konfigürasyonları
- Ansible ile Otomasyon Scriptleri

## Amaç

Sistem yöneticiliği ve ağ mühendisliği alanında pratik yapmak, öğrendiğim becerileri belgelemek ve iş başvurularında kullanmak.

## Kullanılan Araçlar

- VMware Workstation Pro
- pfSense
- Zabbix
- Ansible
- Ubuntu Server

##  2. Gün – pfSense WebGUI ve WAN Yapılandırması

### Yapılanlar:
- pfSense WebGUI üzerinden erişim sağlandı (`HTTP` kullanılarak)
- Ana bilgisayarla `Host-Only` (LAN) ağı üzerinden bağlantı kuruldu
- pfSense’e ikinci ağ adaptörü (NAT) tanımlanarak `WAN` arayüzü yapılandırıldı
- DNS sunucuları (1.1.1.1, 8.8.8.8) tanımlandı
- pfSense üzerinden dış dünyaya `ping` testi yapılarak internet erişimi doğrulandı
- `Firewall > Rules > LAN` altında ICMP ve Web erişim izinleri verildi
- `System > General Setup` kısmında saat dilimi ve hostname ayarlandı