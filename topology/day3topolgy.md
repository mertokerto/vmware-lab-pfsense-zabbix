#  Day 3 - Lab Topology (VMware, pfSense, Ubuntu Server)

##  Altyapı

**VMnet1** - Host-only (192.168.111.0/24)

| Cihaz            | IP Adresi       | Rol                    | Notlar                        |
|------------------|------------------|-------------------------|-------------------------------|
| Ana Bilgisayar   | 192.168.111.2    | Host (Yönetim)          | Statik IP verildi             |
| pfSense (LAN)     | 192.168.111.1    | DHCP + Gateway + Firewall | LAN interface – VMnet1       |
| Ubuntu Server    | 192.168.111.100* | DHCP Client (Sunucu)    | pfSense'ten IP aldı           |

> \* IP, pfSense DHCP sunucusu tarafından otomatik atanmıştır.

---

##  Yapılanlar

- pfSense WebGUI’ye başarıyla erişildi (`http://192.168.111.1`)
- LAN arayüzüne statik IP atandı ve DHCP sunucusu etkinleştirildi
- VMware’in yerleşik DHCP servisi devre dışı bırakıldı
- Ubuntu Server kuruldu ve DHCP ile IP aldı
- Ubuntu’dan pfSense'e ve internete erişim testleri yapıldı
- ICMP trafiği test edildi (ping), Windows Firewall ayarı hatırlandı

---

##  Ağ Topolojisi Diyagramı (Basit)
Ana Bilgisayar (192.168.111.2 - Statik)
         | 
[ VMnet1 - Host Only ]
         | 
+----------------------+
| pfSense (192.168.111.1) |
| DHCP + Gateway + GUI |
+----------------------+
          |
Ubuntu Server (192.168.111.100 - DHCP)