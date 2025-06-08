#  Günlük Lab Gelişim Günlüğü

Bu dosya, VMware üzerinde oluşturduğum sistem yöneticiliği ve ağ mühendisliği lab ortamının gün gün ilerleyişini belgelemektedir. Hedefim, pfSense, Zabbix, Ansible, Wazuh gibi araçlarla gerçek dünya deneyimi kazanmak ve bu süreci profesyonel olarak kayda geçirmektir.

---

##  Gün 1 – VMware + pfSense Kurulumu

- VMware Workstation Pro üzerinde pfSense sanal makinesi oluşturuldu
- Host-only ağı (VMnet1) yapılandırıldı: `192.168.111.0/24`
- pfSense ISO kurulumu tamamlandı
- Sanal makineye ikinci ağ adaptörü (WAN için NAT) eklendi
- pfSense LAN IP'si: `192.168.111.1` olarak ayarlandı
- Ana bilgisayara `192.168.111.2` IP'si verildi
- pfSense WebGUI’ye HTTP üzerinden bağlantı sağlandı

---

##  Gün 2 – WebGUI + WAN Ayarları

- pfSense WebGUI üzerinden ilk yapılandırmalar yapıldı
- Saat dilimi `Europe/Istanbul` olarak ayarlandı
- DNS sunucuları eklendi: `1.1.1.1`, `8.8.8.8`
- pfSense WAN arabirimi DHCP ile IP aldı
- `Diagnostics > Ping` ile dış dünyaya erişim test edildi
- Ana bilgisayardan pfSense’e ve tam tersi yönde ping sağlandı
- İlk temel firewall kuralları planlandı (henüz yazılmadı)

---

##  Notlar
- pfSense’e erişim için HTTP kullanıldı (HTTPS daha sonra etkinleştirilecek)
- Kurulum boyunca yaşanan ağ bağlantı sorunları başarıyla çözüldü
- GitHub reposuna günlük ilerlemeler yüklendi ve belgeler düzenli tutuldu

## Gün 3 - DHCP kurulumu + Ubuntu Server Client kurulumu ve otomatik IP alması 
- pfSense arayüzüne erişim için HTTP protokolü etkinleştirildi
- Ubuntu Server ilk etapta VMware DHCP’sinden IP aldı, sonra düzeltildi
- Windows’a ping atılamaması durumunun nedeni: ICMP bloklama (güvenlik duvarı)
- Her sanal makine doğru ağ (VMnet1) üzerinde konumlandırıldı


---

