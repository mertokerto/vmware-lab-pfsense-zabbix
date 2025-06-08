#  Day 3: DHCP, DNS ve Test VM

Bu belgede pfSense üzerinde DHCP ve DNS servisleri yapılandırılmış, ardından ikinci bir test sanal makine üzerinden bağlantı testleri yapılmıştır.

---

## 1️ DHCP Yapılandırması

- DHCP Aralığı: 192.168.111.100 – 192.168.111.200
- Gateway: 192.168.111.1
- DNS: 1.1.1.1, 8.8.8.8

## 2️ Test VM

- Ağ: Host-Only (VMnet1)
- IP: DHCP ile alındı (örnek: 192.168.111.101)
- Testler:
  -  Ping pfSense LAN: Başarılı
  -  Ping 8.8.8.8 (Internet): Başarılı
  -  Ping google.com (DNS): Başarılı